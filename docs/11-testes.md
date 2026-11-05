# 11. Plano de testes

## Testes funcionais
- Login válido e inválido.
- Separação de permissões cliente/administrador.
- Cadastro e edição de veículos.
- Consulta de catálogo.
- Criação, consulta e cancelamento permitido de agendamento.
- Registro de atendimento e itens.
- Cálculo de subtotais e total.
- Exibição de indicadores.

## Testes offline
- Abrir o aplicativo sem conexão.
- Consultar dados previamente armazenados.
- Criar operação offline.
- Verificar persistência após fechar e abrir o aplicativo.
- Restaurar conexão e verificar sincronização.
- Simular falha temporária e reenvio sem duplicação.

## Testes de segurança
- Cliente não pode acessar dados de outro cliente.
- Administrador deve ter autorização validada pela API.
- Senhas não devem aparecer em logs ou no banco local.
- Segredos e tokens não devem ser enviados ao GitHub.

## Evidências
Registrar capturas de tela, resultados esperados/obtidos e eventuais correções. Utilizar dados fictícios nas evidências públicas.
