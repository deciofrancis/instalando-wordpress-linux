# Instalando Wordpress no Linux

Tutorial de como instalar o Wordpress no Ubuntu 18.04 usando LAMP.

<b>LAMP</b> é o acrônimo que refere-se as primeiras letras de:

- Linux;
- Apache (servidor web);
- MySQL (software de banco de dados);
- PHP (linguagens de programação).

Os comando usados para instalar o LAMP estão em https://help.ubuntu.com/community/ApacheMySQLPHP

Atualizar pacotes de software do Ubuntu:
```
sudo apt-get update
```
depois intalar o LAMP:
```
sudo apt-get install lamp-server^
```

Fazer o download do Wordpress em https://wordpress.org/

Fazendo o download direto na pasta html do Apache
```
cd /var/www/html
sudo wget https://br.wordpress.org/latest-pt_BR.tar.gz
```
Extarir os arquivos baixados
```
sudo tar xvfz latest-pt_BR.tar.gz
```
...
```
sudo chown www-data.www-data wordpress
```

Criar banco de dados no MySQL

A instalação não pediu senha para o root do MySQL porque usa um plugin de auth_socket, que facilita a administração de vários ambientes diferente. Caso queria usar senha acesse esse tutorial:

https://leandro.blog.br/2018/senha-root-do-mysql-no-ubuntu-18-10/

Acessar o mysql com a senha definida:
```
mysql -u root -p
create database 'nome do banco'
```
Comando para ver os bancos existentes:
```
show databases;
```
Comando para sair do MySQL:
```
exit
```

Após a criação do banco de dados acessar o localhost e nome da em que foi extraido os arquivos do wordpress:

http://localhost/wordpress

Preencher os campos:
- nome do banco que foi criado
- usuário, normalmente é root 
- senha do banco
- sevidor do banco, normalmente localhost
- prefixo da tabela, se tiver mais de uma instalação do worpress mude para um prefixo que indetifique o banco para não da conflito e facilitar a organização.

Enviar e intalar.

Se tudo ocorrer bem você vai chegar na tela de Bem-vindo (a) do wordpress, aí é só preencher os campos com o que pede e Instalar Wordpress.

Após a intalação vai aparecer a tela de Sucesso! Acesse com o usuário e senha criado na tela de Bem-vindo, pronto instalação feita e aproveite toda a magia do Wordpress.