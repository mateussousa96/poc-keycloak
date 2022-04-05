# poc-keycloak
Um exemplo de usabilidade do Keycloak para gestão de contas.

## Para levantar o Keycloak localmente execute o comando abaixo
    docker run -p 8080:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:17.0.1 start-dev

## O dashboard é acessado atravez do link
    http://localhost:8080/admin/master/console/

## Utilize as credenciais que pôs no comando que levantou o Keycloak, neste caso:
    username: admin
    password: admin

## Importe o arquivo endpoints.json localizado na raiz do projeto no postman para poder utilizar as requisições.
### Fluxo indicado de uso dos endpoints

- Autenticação ADM

### Receberá o access token que sera passado como bearer token nas requisições seguintes.
#### PS: O access token expira com frequencia, sendo necessaria uma nova autenticação.

- Criar Realm
- Criar Usuário
- Autenticação de usuário criado
- Buscar Usuário
    Capturar o "id" do retorno da busca do usuário e colar no path da proxima requisição substituindo "id"
- Editar Senha
- Autenticação de usuário criado após alteração de senha
