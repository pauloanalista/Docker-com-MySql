## Como criar uma instância MySQL no Docker

Como as imagens do MySQL já estão presentes no repositório oficial do Docker, podemos acessá-las utilizando o comando: mysql/mysql-server.

Para criar um novo container com o MySQL basta digitar o código abaixo no prompt de comando:
```
docker run --name nome-do-container -p 3306:3306 -p 33060:33060  -e MYSQL_ROOT_HOST='%' -e MYSQL_ROOT_PASSWORD='sua-senha' -d mysql/mysql-server:latest
```

Neste código acima já embutimos algumas configurações essenciais para a criação do container. No lugar de nome-do-container você deve colocar o nome que você quer dar para esse container e no lugar de sua-senha a senha para acessar o mysql com usuário root. O :latest do final serve para instalar a versão mais recente, assim como o -p para configurar as portas que serão utilizadas.

Caso queira acessar o MySQL por meio do prompt utilize o código abaixo:
```
docker exec -it nome-do-container mysql -uroot -psua-senha
```

Não esqueça de substituir nome-do-container e sua-senha pelas mesmas que foram inseridas na hora da instalação.

## Como rodar e parar o MySQL com o Docker
Sempre que precisar iniciar o MySQL que você acabou de instalar use o comando:

```
docker start nome-do-container
```

E para parar:
```
docker stop nome-do-container
```

Caso queira confirmar se o MySQL está rodando, basta digitar o seguinte código:

docker ps
Esse comando acima listará todos os containers que estão rodando em seu Docker, se o nome-do-container aparecer significa que está ativo e pronto para ser usado.

Conexão com o banco MySQL
Para se conectar com o MySQL que você acabou de configurar é só utilizar:

```
Host: localhost
Port: 3306
User: root
Password: sua-senha
```
