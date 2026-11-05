# 3. Requisitos e funcionalidades

## Requisitos funcionais
- RF01: permitir autenticação de usuários por meio de API.
- RF02: identificar o perfil autenticado como cliente ou administrador.
- RF03: permitir ao cliente consultar e atualizar seus dados cadastrais.
- RF04: permitir cadastrar e consultar veículos do cliente.
- RF05: exibir catálogo de serviços ativos.
- RF06: permitir solicitar, consultar e cancelar agendamentos conforme regras.
- RF07: permitir ao cliente consultar seu histórico de atendimentos sincronizado.
- RF08: permitir ao administrador consultar clientes e veículos.
- RF09: permitir ao administrador criar e atualizar serviços.
- RF10: permitir ao administrador confirmar, recusar ou concluir agendamentos.
- RF11: permitir registrar atendimento e seus itens/serviços.
- RF12: apresentar indicadores descritivos no painel administrativo.
- RF13: armazenar operações essenciais localmente no SQLite.
- RF14: registrar alterações pendentes e sincronizá-las com a API quando houver internet.

## Requisitos não funcionais
- RNF01: o aplicativo será desenvolvido para Android usando Flutter/Dart.
- RNF02: operações locais essenciais devem funcionar sem internet.
- RNF03: senhas não serão armazenadas em texto puro no dispositivo ou no banco local.
- RNF04: a comunicação com a API deverá utilizar HTTPS em produção.
- RNF05: dados pessoais deverão ser tratados conforme a LGPD.
- RNF06: consultas e gravações locais deverão utilizar transações quando envolverem múltiplas tabelas.
- RNF07: erros de sincronização deverão ser registrados para nova tentativa.
- RNF08: a interface deverá diferenciar claramente dados sincronizados e pendentes.

## Perfis e permissões
- Cliente: acessa apenas seus próprios dados, veículos, agendamentos e histórico.
- Administrador: acessa as funções de gestão autorizadas pela API.
- A autorização deve ser validada no servidor; ocultar telas no aplicativo não é controle de segurança suficiente.
