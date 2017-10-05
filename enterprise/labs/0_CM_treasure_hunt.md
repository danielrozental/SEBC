# What is ubertask optimization?

Procesos suficientemente pequeños para ser corridos secuencialmente en una misma JVM.

# Where in CM is the Kerberos Security Realm value displayed?

security_ream
Administration>Settings>Kerberos>Kerberos Security Realm

# Which CDH service(s) host a property for enabling Kerberos authentication?

ZooKeeper, YARN y HDFS

ZooKeeper (Service-Wide)>Main>Enable Kerberos Authentication
enableSecurity

YARN>YARN (MR2 Included) (Service-Wide)>Security>Enable Kerberos Authentication for HTTP Web-Consoles

HDFS>HDFS (Service-Wide)>Security>Enable Kerberos Authentication for HTTP Web-Consoles

# How do you upgrade the CM agents?

Usando el upgrade wizard del CM.

# Give the tsquery statement used to chart Hue's CPU utilization?

select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME

con $SERVICENAME = hue

# Name all the roles that make up the Hive service

Hive Metastore Server
WebHCat Server
HiveServer2
Gateway

# What steps must be completed before integrating Cloudera Manager with Kerberos?

Seguir la guía que figura acá
https://www.cloudera.com/documentation/enterprise/5-9-x/topics/cm_sg_intro_kerb.html

En resumen
- Instalar las librerías que correspondan en los hosts
- Crear un principal para Cloudera Manager
- Habilitar kerberos usando el wizard
- Crear el superuser de HDFS
- Crear una cuenta de kerberos principal para cada cuenta de usuario
- Preparar el cluster para cada cuenta de usuario, crear la cuenta linux y kerberos si no se usa AD. Crear el directorio home en /user.
- Verificar que funciona.


