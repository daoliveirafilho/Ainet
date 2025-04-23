<!-- ABOUT THE PROJECT -->

# Servidor de configura&ccedil;&atilde;o autom&aacute;tica como ferramenta para um sistema multiagente.

Ollama: Uma plataforma ou ferramenta focada em melhorar a experi&ecirc;ncia com modelos de linguagem.

![Image_0245](assets/images/itens/IMG_0245.jpg)

![Image_0246](assets/images/itens/IMG_0246.jpg)

_LangChain &eacute; uma biblioteca para criar aplica&ccedil;&otilde;es de linguagem natural, facilitando o desenvolvimento de sistemas que interagem com linguagem natural, neste modelo faremos uso do LangChain-Ollama como complemento ou extens&atilde;o da LangChain projetado para integrar com o Ollama._

# Pr&eacute;-requisitos do sistema

### Plataformas compat&iacute;veis

* FreeBSD 11.1 ou posterior
* GNU/Linux portando o kernel 5 ou posterior

### Requisitos de hardware

* 1-8 n&uacute;cleo(s) de CPU
* 1-16Gb de mem&oacute;ria RAM
* 128Gb de storage

### Nginx

O Nginx &eacute; um servidor web que pode funcionar como um proxy reverso, encaminhando solicita&ccedil;&otilde;es de clientes para o PHP-FPM e retornando as respostas processadas de volta para os clientes.

```sh
server {
#listen 80;
listen [::1]:80;
server_name dominio.exemplo.br computador.dominio.exemplo.br;
error_page 500 502 503 504 /50x.html;
location = /50x.html {
root /usr/local/www;
}
error_page 404 402 403 404 /40x.html;
location = /40x.html {
root /usr/local/www;
}
location / {
root /usr/local/www;
index index.html;
}
...
```

![Image_0209](assets/images/itens/IMG_0209.jpg)

### PHP-FPM

O “PHP FastCGI Process Manager,” &eacute; um gerenciador de processos FastCGI avan&ccedil;ado e de alto desempenho para PHP.

```sh
[www]
user = www
group = www
listen = [::1]:19999
listen.owner = www
listen.group = www
listen.mode = 0440
...
```

![Image_0210](assets/images/itens/IMG_0210.jpg)

```sh
location ^~ /phpPgAdmin {
alias /usr/local/www/phpPgAdmin;
index index.php;
location ~ \.php$ {
root /usr/local/www;
include fastcgi_params;
fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
fastcgi_pass [::1]:19999;
} }
```

_Utiliza comunica&ccedil;&atilde;o bidirecional com o uso de envelopes SOAP (Simple Object Access Protocol) que carregam estrutura XML (Extensive Markup Language). A api realiza a leitura e a configura&ccedil;&atilde;o dos par&acirc;metros das CPEs._
