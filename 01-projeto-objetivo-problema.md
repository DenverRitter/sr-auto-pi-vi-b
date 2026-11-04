# 1. Nome, objetivo e problema do projeto

## 1.1 Nome do projeto

**S&R Auto — Central Automotiva Digital**

Aplicativo móvel proposto para a empresa **Silveira & Ritter – Peças e Auto Center**, localizada em Nova Petrópolis – RS.

## 1.2 Contextualização

A presença digital tornou-se importante para empresas que desejam ampliar o relacionamento com seus clientes, divulgar seus serviços e compreender melhor as necessidades do público. No setor automotivo, os clientes precisam encontrar informações sobre serviços, cadastrar seus veículos, solicitar horários e consultar manutenções anteriores.

A empresa, por sua vez, precisa organizar os dados de clientes, veículos, agendamentos e serviços realizados. Essas informações também podem ser analisadas para identificar os serviços mais procurados, períodos de maior movimento e oportunidades comerciais.

## 1.3 Problema que o aplicativo pretende resolver

A ausência de um canal móvel centralizado pode dificultar o acesso dos clientes às informações da empresa e a organização dos registros de relacionamento e atendimento. Quando os dados ficam dispersos em diferentes meios, torna-se mais trabalhoso consultar o histórico de um veículo, acompanhar solicitações e produzir relatórios confiáveis para apoiar decisões.

## 1.4 Solução proposta

O S&R Auto reunirá em um aplicativo Android as principais funcionalidades de relacionamento com clientes e gestão administrativa. O cliente poderá consultar os serviços oferecidos, cadastrar seus veículos, solicitar agendamentos e consultar o histórico disponibilizado pela empresa.

Na área administrativa, usuários autorizados poderão gerenciar cadastros, serviços, agendamentos e atendimentos. Os registros armazenados poderão ser consolidados em indicadores e gráficos para apoiar decisões de negócio.

O aplicativo utilizará SQLite no próprio aparelho para armazenar e consultar dados localmente. Assim, as funcionalidades locais previstas poderão continuar operando sem internet. Quando a conexão estiver disponível, uma API será utilizada para sincronizar os dados entre os dispositivos.

## 1.5 Objetivo geral

Propor e desenvolver um aplicativo móvel para melhorar a presença digital da Silveira & Ritter, facilitar o relacionamento com clientes e utilizar os dados operacionais para apoiar a tomada de decisões de negócio.

## 1.6 Objetivos específicos

- Disponibilizar informações sobre os serviços da empresa.
- Permitir o cadastro e a consulta de veículos dos clientes.
- Permitir a solicitação e o acompanhamento de agendamentos.
- Organizar o histórico de atendimentos e serviços realizados.
- Disponibilizar recursos administrativos para gerenciar informações.
- Armazenar dados essenciais em banco SQLite local.
- Permitir operações locais essenciais mesmo sem conexão com a internet.
- Sincronizar dados com uma API quando houver conexão.
- Gerar indicadores descritivos sobre serviços, agendamentos e atendimentos.
