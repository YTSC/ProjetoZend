## Instalação

Instale o PHP caso nao tenha instalado:
https://www.php.net/downloads.php
Selecione o seu sistema operacional e faça o download do arquivo.

Após o download extraia os arquivos em uma pasta de sua escolha, então vá em 
"Meu computador", clique com o botão direito e selecione "Propriedades".
Em "variáveis do sistema" dê 2 cliques em "Path", clique "Novo" e adicione o 
diretório do PHP que você instalou.

Feito isso será necessário instalar o Composer:
https://getcomposer.org/download/
Execute o instalador e siga os passos.

Após ambos estiverem instalados, vá até o local onde você instalou o PHP e abra 
o arquivo php.ini e localize as seguintes linhas:

;extension=mysqli <br />
;extension=odbc <br /> 
;extension=openssl <br />
;extension=pdo_mysql <br />
;extension=pdo_oci <br />
;extension=pdo_odbc <br />
;extension=pdo_pgsql <br /> 
;extension=pdo_sqlite <br /> 
;extension=pgsql <br />

Remova os ";" delas e adicione a seguinte linha caso não tenha:

extension=php_intl.dll

Agora você pode extrair o projeto para uma pasta de sua preferência.

Crie uma database e coloque os seus parâmetros (nome da db, login, senha) no final do arquivo 
(CAMINHO DO SEU PROJETO)\module\Pessoa\config\module.config.php

Na database criada crie uma tabela desse modo:

create table pessoa (
	id integer primary key auto_increment,
	nome varchar(95),
	sobrenome varchar(45),
	email varchar(45),
	situacao varchar(15)
	);

Após isso abra um Console de sua preferência e caminhe até a pasta 
onde você extraiu o seu projeto. Execute o comando 

```bash
$ composer update
```

Após o termino da atualização execute o comando

```bash
$ php -S 0.0.0.0:8080 -t public/ public/index.php
```
então você será capaz de acessar o projeto no link http://localhost:8080/pessoa
