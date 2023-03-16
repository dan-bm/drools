## Information
[![Sonar Status]
(http://10.100.79.142:9000/api/project_badges/measure?project=com.indeval.mos%3Amos&metric=alert_status)](http://10.100.79.142:9000/dashboard?id=com.indeval.mos%3Amos)

## Coverage
[![Coverage](http://10.100.79.142:9000/api/project_badges/measure?project=com.indeval.mos%3Amos&metric=coverage)](http://10.100.79.142:9000/dashboard?id=com.indeval.mos%3Amos)
## Overview
[![Bugs](http://10.100.79.142:9000/api/project_badges/measure?project=com.indeval.mos%3Amos&metric=bugs)](http://10.100.79.142:9000/dashboard?id=com.indeval.mos%3Amos)
[![Code Smells](http://10.100.79.142:9000/api/project_badges/measure?project=com.indeval.mos%3Amos&metric=code_smells)](http://10.100.79.142:9000/dashboard?id=com.indeval.mos%3Amos)
[![Duplicated Lines (%)](http://10.100.79.142:9000/api/project_badges/measure?project=com.indeval.mos%3Amos&metric=duplicated_lines_density)](http://10.100.79.142:9000/dashboard?id=com.indeval.mos%3Amos)
[![Vulnerabilities](http://10.100.79.142:9000/api/project_badges/measure?project=com.indeval.mos%3Amos&metric=vulnerabilities)](http://10.100.79.142:9000/dashboard?id=com.indeval.mos%3Amos)

# Guía de Instalación

## Contenido

1.	[Nombre de la Aplicación](#1-nombre-de-la-aplicación)

2.	[Objetivo y Descripción del Cambio](#2-objetivo-y-descripción-del-cambio)

3.	[Requisitos de Instalación](#3-requisitos-de-instalación)

4.	[Tareas de Pre-Instalación](#4-tareas-de-pre-instalación)

	4.1	[Configuración del Dominio JBoss](#41-configuración-del-dominio-jboss)

	4.2	[Configuración de Grupos](#42-configuración-de-grupos)

	4.3	[Configuración de Recursos JNDI](#43-configuración-de-recursos-jndi)

	4.4 [Configuración del balanceador](#44-configuración-del-balanceador)

5. [Instalación de la Aplicación](#5-instalación-de-la-aplicación)
	
	5.1	[Descarga del Proyecto](#51-descarga-del-proyecto)
	
	5.2	[Compilación](#52-compilación)
	
	5.3	[Despliegue](#53-despliegue)
	
	5.4	[Productos que se despliegan](#54-productos-que-se-despliegan)
	
	5.5	[Validación de la Instalación](#55-validación-de-la-instalación)

6.	[Especificaciones y acciones necesarias en caso de roll-back](#6-especificaciones-y-acciones-necesarias-en-caso-de-roll-back)



## 1.	Nombre de la Aplicación

- Módulo de Operación en Efectivo (MOS)

## 2.	Objetivo y Descripción del Cambio 

El objetivo de esta versión es atender los siguientes requerimientos:

-	Realizar la migración tecnológica del módulo a la plataforma JBoss EAP 6.



## 3.	Requisitos de Instalación 

Esta instalación está conformada por los siguientes pasos:

1.	Verificar pre-requisitos de instalación.
2.	Ejecución de Script de BD.
3.	Apagar componentes en Weblogic.
4.	Descargar y compilar el proyecto fuente.
5.	Desplegar aplicaciones.

## 4. Tareas de Pre-Instalación 

| **Proyecto** | **Ruta** | **Tag** | **Revisión** |
| -------- | ---- | --- | -------- |
| Manual de configuración JBoss | [Manual Instalación Jboss](http://10.100.236.102/indeval/Manual_Instalacion_JBoss) | N/A |1f627240a093a84ed4b1bb78aa8edaeedd659e3d |

### 4.1	Configuración del Dominio JBoss

Verificar Manual de Instalación JBoss (**2. Condiciones en ambientes controlados**)

| **Proyecto** | **Ruta** | **Tag** | **Revisión** |
| -------- | ---- | --- | -------- |
| Manual de configuración JBoss | [Manual Instalación Jboss/Condiciones en ambientes controlados](http://10.100.236.102/indeval/Manual_Instalacion_JBoss#2-condiciones-en-ambientes-controlados) | N/A | 1f627240a093a84ed4b1bb78aa8edaeedd659e3d |

### 4.2	Configuración de Grupos

Verificar Manual de Instalación JBoss (**2.2 Servidores**)
 
| **Proyecto** | **Ruta** | **Tag** | **Revisión** |
| -------- | ---- | --- | -------- |
| Manual de configuración JBoss | [Manual de Instalación Jboss/Servidores](http://10.100.236.102/indeval/Manual_Instalacion_JBoss#22-servidores) | N/A | 1f627240a093a84ed4b1bb78aa8edaeedd659e3d |

- Validar o en su caso ajustar en cada servidor la opción Auto Start en true / false, según corresponda.
- Reiniciar los grupos para que tome el cambio.


### 4.3	Configuración de Recursos JNDI 

Verificar Manual de Instalación JBoss (**2.3 Configuración de Recursos**)
 
| **Proyecto** | **Ruta** | **Tag** | **Revisión** |
| -------- | ---- | --- | -------- |
| Manual de configuración JBoss | [Manual de Instalación Jboss/Configuración de Recursos](http://10.100.236.102/indeval/Manual_Instalacion_JBoss#23-configuraci%C3%B3n-de-recursos-de-jboss) | N/A | 1f627240a093a84ed4b1bb78aa8edaeedd659e3d |


- Verificar en el POM principal que los siguientes parámetros sean correctos y modificarlos en caso necesario:

	- _config.jdbc.mos.user_
	- _config.jdbc.mos.pass_
	- _config.jdbc.mos.url_
	- _logging.mos.name_
	- _logging.mos.loglevel_



### 4.4 Configuración del balanceador 

N/A



## 5	Instalación de la Aplicación 

### 5.1	Script de Base de Datos. 

| **Ambiente** | **Script** |
| --- | --- |
| Producción | MOS_Script_Instalacion_Produccion.sql |
| Quality | MOS_Script_ Instalacion_Quality.sql |
| Pre-producción | MOS_Script_ Instalacion_Preprod.sql |

### 5.2	Descarga del Proyecto 

| **Proyecto** | **Ruta** | **Tag** | **Revisión** |
| --- | --- | --- | --- |
| MOS | [MOS-GIT](http://10.100.236.102/indeval/mos.git) | mos-2.5.8 | <!-- 12bb9ae1bdf9ef63f686b8bb9cc87d8bb8e15bab | -->

### 5.3	Compilación

- Verificar en el POM principal que los siguientes parámetros sean correctos y modificarlos en caso necesario
	- *jboss.version*

- Compilar el proyecto con Maven 3.3 o superior y Java 7 con el siguiente comando: 
	  
			mvn clean install –Dmaven.test.skip=true -U



### 5.4	Despliegue 

-	Detener los componentes correspondientes en WEBLOGIC: **moduloOperacionEfectivo-ear-2.5.ear** 
 
-	Copiar los siguientes archivos a la carpeta destinada para los scripts de CLI:

		/mos-config/target/mos-EAP-{jboss.version}-2.5.5.cli

-	Abrir la consola CLI de Jboss y conectarse al Domain Controller

Instalación inicial:

		•	Ejecutar el script:
			deploy mos-EAP-{jboss.version}-2.5.5.cli --script=deploy.scr

Instalaciones posteriores (actualizaciones):

		•	Ejecutar el script:
			deploy mos-EAP-{jboss.version}-2.5.5.cli --script=redeploy.scr


### 5.5	Productos que se despliegan 

| **Orden** | **Aplicación** | **Producto** |
| --- | --- | --- |
| 1 | MOS EAR | mos-ear.ear |

### 5.6	Validación de la Instalación 

Que los aplicativos levanten sin arrojar excepciones en el LOG del servidor y del APPENDER correspondiente.


## 6. Especificaciones y acciones necesarias en caso de roll-back 
	
| **Proyecto** | **Ruta** | **Tag** | **Revisión** |
| ------------ | -------- | ------- | ------------ |
| Manual de configuración JBoss | http://10.100.236.102/indeval/Manual_Instalacion_JBoss (5. Especificaciones en Caso de Roll-Back) | N/A | 1f627240a093a84ed4b1bb78aa8edaeedd659e3d |



Tiempo estimado de instalación: **20 minutos**

Tiempo estimado de regreso: **30 minutos**

***

Para desinstalar las aplicaciones:

		•	Ejecutar el script:
			deploy mos-EAP-{jboss.version}-2.5.5.cli --script=undeploy.scr

Tiempo estimado de instalación: ***15 minutos***

Tiempo estimado de regreso: **35 minutos**




Script en Base de Datos 

| Ambiente | Script |
| --- | --- |
| Producción | MOS_Script_Rollback_Produccion.sql |
| Quality | MOS_Script_Rollback_Quality.sql |
| Pre-producción | MOS_Script_Rollback_Preprod.sql |


Tiempo estimado de instalación: **15 minutos**

Tiempo estimado de regreso: **10 minutos**

