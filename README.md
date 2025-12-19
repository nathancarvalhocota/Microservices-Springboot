## Implementação de arquitetura microservice (Java + SpringBoot)

Um serviço de usuário e um serviço de email conversam entre si através da mensageria com RabbitMQ e CloudAQMP. O serviço de Usuário faz um cadastro no PostgreSQL e envia uma mensagem consumida no CloudAMQP pelo serviço de Email, que ao receber a mensagem da fila, envia um email para o novo usuário cadastrado, utilizando Java Mail Sender, e cadastra o email enviado no banco de dados.


### Preparação do ambiente

- JDK 17  
- Maven  
- Postman  
- PgAdmin (Postgres)  
- IDE IntelliJ IDEA  


### Instruções

- Para utilizar o código, é necessário definir as configurações para realizar a conexão com o PostgreSQL, CloudAQMP e Gmail.  
- Os arquivos estão localizados em `src/main/resources`.  
- Para conectar o postgreSQL basta criar as bases `ms-user` e `ms-email` em seu ambiente.  
- Para conectar com o serviço de mensageria acesse [https://www.cloudamqp.com/](https://www.cloudamqp.com/) e crie uma nova instância gratuita, você irá receber uma URL que deve ser inserida em `spring.rabbitmq.addresses` e o nome da fila escolhido deve ser definido em `broker.queue.email.name`.  
- Para se conectar com o serviço do Gmail é necessário criar uma senha de aplicativo, diferente da senha da conta, para mais detalhes acesse [https://support.google.com/accounts/answer/185833](https://support.google.com/accounts/answer/185833).  
- As configurações referente ao email devem ser definidas na seção EMAIL do arquivo de propriedades do serviço de email.
