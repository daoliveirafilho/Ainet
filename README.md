<!-- ABOUT THE PROJECT -->

# Servidor de configura&ccedil;&atilde;o autom&aacute;tica (ACS) como ferramenta para um sistema multiagentes (MAS).

## Pr&eacute;-requisitos do sistema

### Plataformas compat&iacute;veis

* FreeBSD 11.1 ou posterior
* GNU/Linux portando o kernel 5 ou posterior

### Nginx

O Nginx &eacute; um servidor web que pode funcionar como um proxy reverso, encaminhando solicita&ccedil;&otilde;es de clientes para o PHP-FPM e retornando as respostas processadas de volta para os clientes.

![Image_0209](assets/images/itens/IMG_0209.jpg)

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

_A api realiza a leitura e a configura&ccedil;&atilde;o dos par&acirc;metros das CPEs com o uso de envelopes SOAP (Simple Object Access Protocol) e uma estrutura XML (Extensive Markup Language)._

```sh
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/"
               xmlns:cwmp="urn:dslforum-org:cwmp-1-0"
               soap:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
<soap:Header>
<cwmp:ID mustUnderstand="1">$ID</cwmp:ID>    
</soap:Header>
<soap:Body>
<cwmp:GetRPCMethods></cwmp:GetRPCMethods>
</soap:Body>
</soap:Envelope>
```

## Monitorar, detectar e previnir atividades maliciosas relacionadas ao abuso de privil&eacute;gios, com o objetivo de reduzir a superf&iacute;cie de ataque.

# ...em desenvolvimento

### Ollama

O Ollama &eacute; uma ferramenta de c&oacute;digo aberto que executa large language models (LLMs) diretamente em um computador.

_Requisitos de hardware_

* 1-8 n&uacute;cleo(s) de CPU
* 1-16Gb de mem&oacute;ria RAM
* 128Gb de storage

### Ollama via api

```sh
# ollama run mistral-small3.1
```

![Image_0245](assets/images/itens/IMG_0245.jpg)

```sh
# ollama run llama3:8b
```

![Image_0246](assets/images/itens/IMG_0246.jpg)

# ...em desenvolvimento
