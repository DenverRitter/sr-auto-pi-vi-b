# 2. Público-alvo e requisitos de usuário

## 2.1 Público-alvo

O aplicativo será destinado a dois grupos principais:

### Clientes da Silveira & Ritter

Pessoas que possuem ou utilizam veículos e desejam consultar os serviços da empresa, cadastrar seus veículos, solicitar agendamentos e acompanhar informações sobre atendimentos.

### Administração da empresa

Responsáveis e colaboradores autorizados da Silveira & Ritter que necessitam organizar cadastros, administrar serviços e agendamentos, registrar atendimentos e consultar indicadores de desempenho.

## 2.2 Requisitos de usuário — cliente

- RU01 — Como cliente, quero criar uma conta e entrar no aplicativo para acessar minhas informações.
- RU02 — Como cliente, quero consultar os serviços oferecidos para conhecer as opções disponíveis.
- RU03 — Como cliente, quero cadastrar meus veículos para manter seus dados organizados.
- RU04 — Como cliente, quero solicitar um agendamento para pedir atendimento à empresa.
- RU05 — Como cliente, quero consultar o estado dos meus agendamentos para acompanhar minhas solicitações.
- RU06 — Como cliente, quero consultar o histórico de serviços dos meus veículos para acompanhar as manutenções registradas.
- RU07 — Como cliente, quero consultar os dados de contato e localização da empresa para facilitar a comunicação.

## 2.3 Requisitos de usuário — administração

- RU08 — Como administrador, quero entrar em uma área restrita para acessar as funções de gestão.
- RU09 — Como administrador, quero consultar e gerenciar clientes e veículos para manter os cadastros organizados.
- RU10 — Como administrador, quero cadastrar e atualizar serviços para manter o catálogo da empresa atualizado.
- RU11 — Como administrador, quero visualizar e atualizar agendamentos para organizar a agenda de atendimento.
- RU12 — Como administrador, quero registrar atendimentos e os serviços executados para manter o histórico atualizado.
- RU13 — Como administrador, quero consultar indicadores e relatórios para apoiar decisões comerciais.
- RU14 — Como administrador, quero identificar dados pendentes de sincronização para acompanhar a atualização das informações.

## 2.4 Requisitos não funcionais

- RNF01 — O aplicativo será desenvolvido para dispositivos Android.
- RNF02 — O aplicativo utilizará SQLite como banco de dados local.
- RNF03 — As operações locais previstas deverão funcionar sem conexão com a internet.
- RNF04 — A sincronização com o servidor ocorrerá por API quando houver conexão.
- RNF05 — A interface deverá ser simples, consistente e adequada a dispositivos móveis.
- RNF06 — O acesso administrativo deverá exigir autenticação e autorização.
- RNF07 — Senhas não poderão ser armazenadas em texto puro.
- RNF08 — Dados pessoais deverão ser tratados com cuidado e conforme a LGPD.
- RNF09 — O aplicativo deverá informar quando houver dados pendentes de sincronização.
- RNF10 — O projeto deverá permitir geração de APK para instalação em dispositivos Android.
