FROM centos:centos7

MAINTAINER	"Anderson Deluiz <anderson.deluiz@gpnet.com.br>"

# Atualiza imagem com ultimos pacotes disponibilizados
RUN	yum -y update

# Instala servico HTTP e registra para inicio automatico
RUN	yum -y install httpd mod_ssl

# Desabilita pagina de boas vindas no servidor Apache HTTPD
RUN	sed '/^[^#]/s/^/#/'  /etc/httpd/conf.d/welcome.conf > /tmp/welcome.conf \
	&& mv -v /tmp/welcome.conf /etc/httpd/conf.d/welcome.conf

# Adiciona arquivo de configuracao do Apache HTTPD para acesso ao Sigadoc.
ADD	etc/httpd/conf.d/sigadoc.conf /etc/httpd/conf.d/sigadoc.conf

# Disponibiliza porta TCP 80 para conexoes com o mundo exterior
EXPOSE	80 443

# Inicia daemon HTTP automaticamente ao inciar o conteiner sem argumentos
ENTRYPOINT	["/usr/sbin/httpd","-D","FOREGROUND","-D","SSL"]
