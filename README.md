# S&R Auto — Projeto Integrador VI-B

**Empresa:** Silveira & Ritter – Peças e Auto Center  
**Desenvolvedor:** Denver Ritter  
**Etapa:** Primeira etapa — documentação e proposta do aplicativo  
**Plataforma prevista:** Android

## 1. Apresentação

O **S&R Auto – Central Automotiva Digital** é uma proposta de aplicativo móvel para aproximar a Silveira & Ritter de seus clientes, organizar informações de veículos e serviços e apoiar a administração dos atendimentos.

O aplicativo prevê dois perfis de acesso: cliente e administrador. O cliente poderá consultar serviços, cadastrar veículos, solicitar agendamentos e acompanhar atendimentos. A administração poderá gerenciar clientes, veículos, serviços, agenda e registros de atendimento.

A proposta prevê banco de dados local SQLite e sincronização com uma API quando houver conexão com a internet.

## 2. Problema e solução

A dispersão de informações de clientes, veículos, agendamentos e serviços pode dificultar o acompanhamento do relacionamento e do histórico dos veículos. O S&R Auto propõe centralizar essas informações em um aplicativo Android, oferecendo recursos de consulta e gerenciamento adequados a cada perfil de usuário.

## 3. Público-alvo

- Clientes da Silveira & Ritter – Peças e Auto Center.
- Proprietários de automóveis e motocicletas.
- Administradores e responsáveis pelo atendimento da empresa.

## 4. Funcionalidades previstas

### Área do cliente
- Cadastro e autenticação.
- Cadastro e gerenciamento dos próprios veículos.
- Consulta ao catálogo de serviços.
- Solicitação e acompanhamento de agendamentos.
- Consulta ao histórico de atendimentos disponibilizado pela empresa.
- Visualização do perfil e do estado de sincronização.

### Área administrativa
- Gerenciamento de clientes e veículos.
- Cadastro e atualização do catálogo de serviços.
- Controle de agendamentos.
- Registro de atendimentos e serviços executados.
- Consulta de indicadores administrativos.

## 5. Documentação da primeira etapa

A documentação está organizada na pasta `docs/`:

1. [Nome, objetivo e problema](docs/01-projeto-objetivo-problema.md)
2. [Público-alvo e requisitos de usuário](docs/02-publico-alvo-requisitos.md)
3. [Características e funcionalidades](docs/03-caracteristicas-funcionalidades.md)
4. [Tecnologias, linguagens e bibliotecas](docs/04-tecnologias.md)
5. [Modelo entidade-relacionamento](docs/05-modelo-er.md)
6. [Construção e implementação do banco SQLite](docs/06-banco-local-sqlite.md)
7. [Design e wireframes das telas](docs/07-design-wireframes.md)
8. [Geração do arquivo APK](docs/08-geracao-apk.md)
9. [Avaliação por pares](docs/09-avaliacao-por-pares.md)

## 6. Banco de dados local

O banco de dados previsto é o SQLite, acessado no Flutter pelo pacote `sqflite`. A modelagem contém oito tabelas, com tipos de dados, chaves primárias, chaves estrangeiras, restrições e relacionamentos. A documentação detalhada está em [05-modelo-er.md](docs/05-modelo-er.md) e [06-banco-local-sqlite.md](docs/06-banco-local-sqlite.md).

## 7. Wireframes

Os wireframes em SVG estão disponíveis na pasta [`wireframes/`](wireframes/). O conjunto contém 17 telas planejadas, incluindo uma tela “Sobre o aplicativo” com a identificação do desenvolvedor **Denver Ritter**. A relação completa está em [07-design-wireframes.md](docs/07-design-wireframes.md).

## 8. Geração do APK

A documentação apresenta o procedimento previsto para gerar o APK Android com Flutter, incluindo o comando `flutter build apk --release`. A geração ocorrerá em etapa posterior, após a implementação e os testes. Consulte [08-geracao-apk.md](docs/08-geracao-apk.md).

## 9. Escopo desta entrega

Esta primeira etapa contempla a proposta do aplicativo, o problema e a solução, público-alvo, requisitos, funcionalidades, tecnologias, modelagem e plano de implementação do banco local, wireframes e procedimento previsto para geração do APK.

**Não fazem parte desta entrega:** aplicativo implementado, API operacional ou APK compilado. Esses itens serão desenvolvidos nas próximas etapas.

## 10. Identificação

**Projeto:** S&R Auto – Central Automotiva Digital  
**Desenvolvedor:** Denver Ritter  
**Empresa:** Silveira & Ritter – Peças e Auto Center  
**Disciplina:** Projeto Integrador VI-B

*Projeto desenvolvido individualmente por Denver Ritter.*
