# 1. Introdução e problema

## Contextualização
A Silveira & Ritter – Peças e Auto Center atua no segmento automotivo e oferece serviços como peças e acessórios, troca de óleo, freios, suspensão, diagnóstico eletrônico e retífica de discos de freio e volante do motor.

A digitalização do relacionamento com clientes pode facilitar a consulta de serviços, o registro de veículos, a solicitação de horários e o acompanhamento do histórico de manutenção.

## Problema
Informações de clientes, veículos, solicitações e serviços podem ficar dispersas em diferentes canais e registros. Isso dificulta a consulta do histórico, o acompanhamento de agendamentos e a geração de indicadores comerciais consistentes.

## Solução proposta
O S&R Auto será um aplicativo Android com dois perfis de acesso:
- Cliente: cadastro, veículos, catálogo de serviços, solicitação de agendamento e consulta de histórico.
- Administrador: gestão de clientes, veículos, serviços, agendamentos e atendimentos, além de painel de indicadores.

O aplicativo utilizará SQLite no próprio aparelho para permitir operações essenciais sem conexão. Quando houver internet, os dados pendentes serão sincronizados com uma API.
