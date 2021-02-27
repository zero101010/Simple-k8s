- Criar máquina virtual
- Configurar ns do domínio, nesse caso usaremos cloudflare 
- Rodar docker com imagem do nginx
- Atrelar subdomínio ao ip da máquina virtual criada
- Após isso instalar certbot dentro da máquina virtual(curl -o- https://raw.githubusercontent.com/vinyll/certbot-install/master/install.sh | bash)
- Após instalar gerar o certificado com o seguinte comando `certbot certonly --webroot -w /var/www/example.com/html -d vm.devopstests.com`
- após isso enviar o path do certificado para o nginx 
```
        ssl_certificate /etc/letsencrypt/live/vm.devopstests.com/fullchain.pem;
        ssl_certificate_key /etc/letsencrypt/live/vm.devopstests.com/privkey.pem;
```