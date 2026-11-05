# 4. Regras de negócio

- RN01: cada conta de cliente deverá possuir identificação única.
- RN02: um cliente poderá cadastrar vários veículos.
- RN03: um veículo deverá estar vinculado a um único cliente responsável.
- RN04: a placa deverá ser normalizada e única no escopo definido pela empresa; a validação definitiva será feita no servidor.
- RN05: somente serviços ativos poderão ser selecionados em novos agendamentos.
- RN06: um agendamento deverá estar associado a um cliente e a um veículo pertencente a esse cliente.
- RN07: os estados iniciais do agendamento serão `pendente`, `confirmado`, `recusado`, `cancelado` e `concluido`.
- RN08: o cliente poderá cancelar apenas solicitações permitidas pela política definida pela empresa.
- RN09: um atendimento poderá conter um ou mais itens de serviço.
- RN10: o subtotal de um item será calculado por quantidade × valor unitário; o total do atendimento será a soma dos subtotais e ajustes registrados.
- RN11: valores e preços históricos dos itens serão preservados no atendimento, mesmo que o preço do catálogo seja alterado posteriormente.
- RN12: registros criados offline deverão receber identificador local único e estado de sincronização pendente.
- RN13: conflitos de atualização deverão ser tratados pela API, preservando histórico e evitando sobrescrita silenciosa.
- RN14: indicadores financeiros serão calculados a partir de atendimentos/vendas efetivamente registrados, não de simples solicitações de agendamento.
