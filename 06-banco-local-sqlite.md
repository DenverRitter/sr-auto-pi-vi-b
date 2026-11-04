# 6. Construção e implementação do banco de dados local

## 6.1 Banco escolhido

O banco de dados local escolhido é o **SQLite**. Ele será executado no próprio dispositivo Android e armazenará os dados necessários para as funcionalidades offline do S&R Auto.

A integração com Flutter será realizada pelo pacote `sqflite`, com o pacote `path` para compor o caminho do arquivo do banco.

## 6.2 Arquivo e criação do banco

Na primeira execução, a aplicação verificará se o arquivo do banco existe. Caso não exista, o `sqflite` criará o arquivo no diretório privado de bancos de dados do aplicativo e executará a rotina de criação das tabelas.

Nome previsto do arquivo: `sr_auto.db`.

A versão inicial do banco será `1`. Alterações futuras na estrutura deverão utilizar migrações controladas, incrementando a versão e preservando os dados existentes.

## 6.3 Processo de construção

1. Inicializar o acesso ao Flutter e ao SQLite.
2. Obter o diretório de bancos de dados do aplicativo no Android.
3. Abrir ou criar o arquivo `sr_auto.db`.
4. Habilitar as chaves estrangeiras com `PRAGMA foreign_keys = ON`.
5. Criar as tabelas USUARIOS, CLIENTES, VEICULOS, SERVICOS, AGENDAMENTOS, ATENDIMENTOS, ITENS_ATENDIMENTO e FILA_SINCRONIZACAO.
6. Criar índices para campos utilizados em filtros e consultas frequentes.
7. Implementar operações de inserir, consultar, atualizar e excluir logicamente quando aplicável.
8. Utilizar transações para operações que alterem mais de uma tabela.
9. Registrar na fila de sincronização as alterações que precisam ser enviadas à API.
10. Implementar migrações para futuras versões do banco.

## 6.4 Utilização pelas funcionalidades

- Login: perfil e dados necessários à sessão poderão ser mantidos localmente; credenciais e senhas em texto puro não serão armazenadas no SQLite.
- Clientes e veículos: dados previamente carregados poderão ser consultados offline; cadastros locais permitidos poderão ser enfileirados para sincronização.
- Serviços: catálogo recebido da API ficará armazenado localmente para consulta offline.
- Agendamentos: solicitações poderão ser registradas localmente com estado pendente de sincronização. A confirmação definitiva do horário dependerá da validação central da API.
- Atendimentos: registros autorizados pela administração poderão ser gravados localmente e sincronizados posteriormente.
- Indicadores: relatórios poderão ser calculados a partir dos dados disponíveis localmente, identificando o período e a situação de sincronização dos dados.

## 6.5 Relacionamento entre as tabelas

As relações serão implementadas por chaves estrangeiras. Por exemplo, `VEICULOS.cliente_id` referencia `CLIENTES.id`, garantindo que cada veículo esteja associado a um cadastro de cliente existente.

`AGENDAMENTOS` relaciona clientes e veículos. `ATENDIMENTOS` também relaciona cliente e veículo. `ITENS_ATENDIMENTO` relaciona atendimentos e serviços, permitindo que um atendimento contenha vários serviços.

## 6.6 Integridade, transações e valores

As operações que incluírem atendimento e itens deverão ocorrer em uma transação. Se alguma etapa falhar, a transação será revertida, evitando registros incompletos.

Valores monetários serão armazenados em centavos usando `INTEGER`, evitando problemas de precisão de ponto flutuante. O subtotal será calculado por quantidade multiplicada pelo preço unitário histórico.

## 6.7 Funcionamento offline e sincronização

O SQLite será a fonte local para leitura e gravação das operações offline previstas. Cada alteração pendente será registrada na tabela `FILA_SINCRONIZACAO`, com identificador único, entidade, operação, conteúdo e quantidade de tentativas.

Quando a internet estiver disponível:
1. O aplicativo enviará operações pendentes à API.
2. A API validará autenticação, permissões e regras de negócio.
3. A API retornará o resultado de cada operação.
4. O aplicativo marcará como sincronizadas apenas as operações confirmadas.
5. Falhas temporárias permanecerão na fila para nova tentativa.

A sincronização deverá evitar duplicidades por meio de identificadores únicos e chaves de idempotência. Conflitos deverão ser sinalizados e tratados sem sobrescrever silenciosamente dados.

## 6.8 Segurança e privacidade

O banco será armazenado no espaço privado do aplicativo. Senhas não serão gravadas em texto puro. Tokens de autenticação deverão ser armazenados em mecanismo seguro do Android, e não em uma tabela comum do SQLite. O acesso a dados de clientes deverá respeitar as permissões do usuário e a legislação de proteção de dados.
