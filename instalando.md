<pre>
para instalar o cactoo é muito simples,vá na aba downloads<br>
baixe a versão mais nova do cactoo,descompacte o zip do<br>
mesmo na pasta local do seu web server,sete todos os arquivos<br>
para permissão 755 exceto o "code/auth.php" que precisa de<br>
permissões de escritá...<br>
<br>
Configurando<br>
--------------<br>
doc/dump.txt  <--- Execute os comandos deste arquivo no seu banco<br>
helper/class.crud.php  <--- Configure o cabeçalho de acordo com seu SGBD e banco usado<br>
code/rss.php <--- Configure o cabeçalho do arquivo de acordo com seu DNS<br>
<br>
configure o ".htaccess" para usar mod_rewrite para URLs amigaveis<br>
</pre>
```

RewriteEngine On
RewriteOptions inherit
RewriteBase /cactoo  #atenção caso mude nome da pasta mude aqui
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^inicio|index|index.html$ code/front.php
RewriteRule post=([/]*) code/front.php?view=$1
RewriteRule pag&list=([/]*) code/front.php?pag&list=$1
RewriteRule pages&list=([/]*) code/front.php?pages&list=$1
RewriteRule ^coment code/front.php?page=ComentAdd
RewriteRule ^busca code/front.php?page=buscar
RewriteRule aba=([/]*) code/front.php?aba=$1 [L]
RewriteRule categoria=([/]*) code/front.php?CategoriaView=$1 [L]
RewriteRule ^rss$ code/rss.php [L]
```
<pre>
visitante irá ver a página em http://localhost/cactoo/inicio<br>
<br>
<br>
Login<br>
-------<br>
para fazer login acesse "site.com/nome_pasta/template/login.html", logue-se como<br>
login "admin" e senha "1234", depois mude sua senha na Aba Users e "listar users"<br>
caso queira criar um usuário para apenas ser escritor de poderes de "user" e<br>
assim que logar irá entrar modo de escritor,não permitindo que edite usuários,<br>
categorias etc...<br>
<br>
<br>
Front "página inicial"<br>
------------------------<br>
página Inicial pode ser vista em "site.com/nome_pasta/code/front.php"<br>
ou em "cactoo/index" se tiver ativado mod_rewrite<br>
sua template fica em "view/front"<br>
<br>
Slider<br>
--------<br>
A opção de Slider como padrão não está ativada,caso queira ativar<br>
vá em opções na sessão de admin ,Config do sistema,ative o slider<br>
logo depois no próprio menu opções você verá opções para controlar<br>
o slider...<br>
<br>
Melhorias Futuras<br>
--------------------<br>
captcha nos forms de comentários e contato<br>
<br>
Thanks<br>
------------<br>
_mlk_,IAK,m0nad,d3lf0,jeferson da OrionMidia, ecl,voidpointer,otacon_x32,zepplin,muzgo,f0kerbug...<br>
<br>
Autor: Cooler_<br>
contato: c00f3r@gmail.com<br>
</pre>
