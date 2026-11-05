# 5. Banco de dados local — SQLite

O SQLite será executado no próprio dispositivo Android. A camada de persistência será implementada com o pacote `sqflite`. O banco local armazenará dados necessários às telas offline, cache de dados recebidos da API e uma fila de sincronização.

## Tabelas

| Tabela | Campos principais | Finalidade |
|---|---|---|
| users | id, name, email, role, updated_at | Perfil local/cache do usuário; sem senha em texto puro |
| customers | id, user_id, phone, created_at | Dados de clientes |
| vehicles | id, customer_id, plate, make, model, year | Veículos |
| services | id, name, description, price_cents, active | Catálogo de serviços |
| appointments | id, customer_id, vehicle_id, scheduled_at, status, sync_status | Agendamentos |
| work_orders | id, customer_id, vehicle_id, started_at, total_cents, status | Atendimentos |
| work_order_items | id, work_order_id, service_id, quantity, unit_price_cents, subtotal_cents | Serviços de cada atendimento |
| sync_queue | id, entity, entity_id, operation, payload_json, created_at, attempts | Fila de sincronização |

## Relacionamentos
- `users` 1:0..1 `customers`.
- `customers` 1:N `vehicles`.
- `customers` 1:N `appointments`.
- `vehicles` 1:N `appointments`.
- `customers` 1:N `work_orders`.
- `vehicles` 1:N `work_orders`.
- `work_orders` 1:N `work_order_items`.
- `services` 1:N `work_order_items`.

## Tipos e restrições
- Identificadores: `TEXT` com UUID.
- Textos: `TEXT`.
- Datas: `TEXT` em ISO-8601 UTC.
- Valores monetários: `INTEGER` em centavos para evitar imprecisão de ponto flutuante.
- Quantidades: `INTEGER`.
- Ativo: `INTEGER` com valores 0 ou 1.
- Chaves primárias e estrangeiras; `NOT NULL` nos campos obrigatórios; `CHECK` para valores e quantidades; índices em campos de busca.
- A aplicação deverá habilitar `PRAGMA foreign_keys = ON`.

O script completo está em `database/schema.sql`.

## Segurança e privacidade
O banco local não armazenará senhas em texto puro. Tokens de sessão, quando necessários, deverão ser guardados em armazenamento seguro do sistema operacional, não em tabela SQLite sem proteção. Dados reais de clientes não devem ser usados em exemplos ou commits públicos.
