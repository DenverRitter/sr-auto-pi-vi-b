# 8. API e sincronização

## Contrato inicial sugerido
A API REST deverá oferecer, no mínimo, os seguintes recursos:

| Método | Endpoint | Finalidade |
|---|---|---|
| POST | /auth/login | Autenticação |
| POST | /auth/refresh | Renovação de sessão |
| GET | /me | Perfil atual |
| GET/POST | /customers | Consultar/criar clientes |
| GET/POST | /vehicles | Consultar/criar veículos |
| GET | /services | Listar catálogo |
| GET/POST | /appointments | Consultar/solicitar agendamentos |
| PATCH | /appointments/{id} | Atualizar estado permitido |
| GET/POST | /work-orders | Consultar/criar atendimentos (admin) |
| GET | /analytics/summary | Indicadores agregados (admin) |
| POST | /sync/push | Enviar alterações locais pendentes |
| GET | /sync/pull?since={cursor} | Baixar alterações desde o último cursor |

## Regras de sincronização
- Cada operação deverá possuir UUID e chave de idempotência.
- A API deverá validar permissões, propriedade do registro e regras de negócio.
- A resposta deverá informar operações aceitas, rejeitadas e em conflito.
- O cliente só marcará um item como sincronizado após confirmação do servidor.
- Falhas temporárias deverão manter a operação na fila e incrementar tentativas.
- O cursor de sincronização deverá ser persistido localmente.

## Ambiente
A URL base da API será configurada por ambiente, sem credenciais ou segredos versionados no Git. A implementação do backend e a hospedagem deverão ser definidas antes do teste multiaparelho.
