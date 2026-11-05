# 7. Arquitetura offline-first

## Visão geral
A solução será dividida em:
- Interface Flutter: telas de cliente e administração.
- Camada de serviços/repositórios: regras de aplicação e acesso a dados.
- SQLite local: persistência e leitura offline.
- Cliente HTTP: comunicação REST com a API.
- Serviço de sincronização: envio e recebimento de alterações pendentes.

## Fluxo de gravação
1. O usuário realiza uma operação.
2. A aplicação valida os dados.
3. Grava a alteração no SQLite dentro de uma transação.
4. Registra a operação em `sync_queue`.
5. A interface confirma a gravação local.
6. Se houver conexão, o sincronizador envia a operação à API.
7. Após confirmação do servidor, marca a operação como sincronizada e atualiza os dados locais.

## Funcionamento sem internet
Cadastros e consultas definidos como offline-first deverão funcionar localmente. Funcionalidades que exigem confirmação central — por exemplo, disponibilidade final de um horário — deverão ser apresentadas como solicitação pendente até a API confirmar.

## Conflitos e identificadores
Cada registro criado localmente deverá utilizar UUID. A API deverá aceitar chaves de idempotência para evitar duplicação em reenvios. Atualizações conflitantes deverão retornar estado de conflito para resolução explícita.

## Segurança
- HTTPS em produção.
- Tokens de acesso de curta duração e renovação segura.
- Armazenamento de tokens em armazenamento seguro do dispositivo.
- Autorização por perfil e por registro validada no servidor.
- Coleta mínima de dados pessoais.
