# 6. Ciência de Dados e indicadores

A primeira versão aplicará análise descritiva e exploratória sobre os dados operacionais registrados no sistema.

## Perguntas de negócio
- Quais serviços são mais solicitados e executados?
- Em quais períodos há maior volume de agendamentos?
- Qual é o faturamento registrado por mês?
- Quantos clientes retornam para novos atendimentos?
- Qual é o ticket médio dos atendimentos concluídos?

## Indicadores
- Quantidade de agendamentos por período e status.
- Serviços mais realizados por quantidade.
- Faturamento por mês, calculado com atendimentos concluídos.
- Ticket médio = faturamento registrado / quantidade de atendimentos concluídos.
- Clientes recorrentes = clientes com mais de um atendimento no intervalo analisado.

## Processo
1. Coletar dados por meio dos cadastros e registros operacionais.
2. Validar campos, datas, estados e valores.
3. Preparar os dados, removendo duplicidades e tratando registros incompletos.
4. Agregar os dados por período, serviço e cliente.
5. Exibir gráficos e tabelas no painel administrativo.
6. Interpretar os resultados para apoiar decisões, como divulgação de serviços ou planejamento de estoque.

## Limitações
Os indicadores dependem da qualidade e completude dos registros. Dados de demonstração deverão ser identificados como fictícios. A versão inicial não afirmará realizar previsão de demanda nem machine learning.
