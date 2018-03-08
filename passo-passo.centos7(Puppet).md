Cen�rio
==================================================================================

Puppet Server\
Puppet Agent

Pr�-requisitos
==================================================================================

#### Puppet Server

	RAM: 2GB

CentOS 7 - Puppet-Server
==================================================================================

## Instal��o

1- Instalar o reposit�rio do Puppet

	rpm -ivh https://yum.puppetlabs.com/puppetlabs-release-pc1-el-7.noarch.rpm

2- Instalar Puppet-Server

	yum install puppetserver

3- Por padr�o o Puppet vem com o JVM(java) configurado para subir utilizando 2GB 
RAM, que � o m�nimo recomendado, por�m se o seu servidor n�hihio dispor desta mem�ria, 
altere a configura��o da JVM conforme a sua necessidade.

	vi /etc/sysconfig/puppetserver

		JAVA_ARGS="-Xms2g -Xms2g --XX:MaxPermiSize=256m"

4- Iniciar o Puppet Server e habiltar o startup autom�tico

	systemctl start puppetserver.service
	systemctl enable puppetserver.service

	