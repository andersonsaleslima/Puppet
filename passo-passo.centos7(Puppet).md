Cenário
==================================================================================

Puppet Server\
Puppet Agent

Pré-requisitos
==================================================================================

#### Puppet Server

	RAM: 2GB

CentOS 7 - Puppet-Server
==================================================================================

## Instalção

1- Instalar o repositório do Puppet

	rpm -ivh https://yum.puppetlabs.com/puppetlabs-release-pc1-el-7.noarch.rpm

2- Instalar Puppet-Server

	yum install puppetserver

3- Por padrão o Puppet vem com o JVM(java) configurado para subir utilizando 2GB 
RAM, que é o mínimo recomendado, porém se o seu servidor nãhihio dispor desta memória, 
altere a configuração da JVM conforme a sua necessidade.

	vi /etc/sysconfig/puppetserver

		JAVA_ARGS="-Xms2g -Xms2g --XX:MaxPermiSize=256m"

4- Iniciar o Puppet Server e habiltar o startup automático

	systemctl start puppetserver.service
	systemctl enable puppetserver.service

	