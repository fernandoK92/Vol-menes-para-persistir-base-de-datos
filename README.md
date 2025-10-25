# Volúmenes para persistir base de datos

## 1. Título  
Volúmenes para persistir base de datos
## 2. Tiempo de duración  
30 minutos.  

## 3. Fundamentos  

Docker permite crear contenedores ligeros e independientes que ejecutan aplicaciones de forma aislada. Sin embargo, los datos generados dentro de un contenedor se pierden al eliminarlo.
Para evitar esto, Docker ofrece volúmenes, que son espacios de almacenamiento persistentes. Al asociar un volumen a un contenedor, los datos se mantienen incluso si el contenedor se detiene o se elimina.
En esta práctica se utilizó PostgreSQL, un sistema de gestión de bases de datos relacional, para demostrar la diferencia entre trabajar con y sin volúmenes.

## 4. Conocimientos previos  

Antes de realizar esta práctica, se debe tener conocimiento básico sobre:

Comandos básicos de Docker (run, ps, stop, rm, exec).

Conceptos de contenedores, imágenes y volúmenes.

Uso de un cliente para bases de datos (como pgAdmin, TablePlus o DataGrip).

Conceptos fundamentales de bases de datos relacionales y SQL (crear bases, tablas e insertar registros).

## 5. Objetivos a alcanzar  

Comprender cómo funcionan los contenedores de bases de datos en Docker.

Identificar la diferencia entre almacenar datos dentro del contenedor y en un volumen persistente.

Crear un contenedor PostgreSQL funcional y conectarse desde un cliente externo.

Comprobar la persistencia de datos al eliminar y recrear un contenedor usando volúmenes.
## 6. Equipo necesario  

Computador con Docker Desktop instalado y en ejecución.

Cliente de base de datos (por ejemplo, TablePlus, pgAdmin o DataGrip).

Acceso a internet para descargar la imagen oficial de PostgreSQL (postgres:15).

Editor de texto o IDE para redactar el informe (VS Code, Notepad++, etc.).

## 7. Material de apoyo  

- Documentacion de Docker
- Videos de youtube. 
- Tutoriales de Docker.
## 8. Procedimiento    
Parte 1: Base de datos sin volumen

Crear el contenedor PostgreSQL:


<img width="589" height="29" alt="image" src="https://github.com/user-attachments/assets/4f325309-3a88-40df-9b15-a1841669fc69" />


Conectarse con el cliente SQL (por ejemplo yo utilize TablePlus).


Host: localhost

Port: 5433

User: mi_user

Password: mi_pass



<img width="589" height="399" alt="image" src="https://github.com/user-attachments/assets/9378eabd-74ac-4179-8874-1c9c400128e4" />



Crear la base de datos test.

<img width="589" height="377" alt="image" src="https://github.com/user-attachments/assets/26f6ead2-613c-4f2e-8a96-252ad8f1e8de" />


Dentro de test, crear la tabla customer:

<img width="589" height="383" alt="image" src="https://github.com/user-attachments/assets/98eabfc4-d99b-4736-b152-b5aef47f0e4a" />

Insertar un registro:

<img width="589" height="396" alt="image" src="https://github.com/user-attachments/assets/a0e072d7-b138-494c-a5fa-22c20eb53b31" />

Verificar los datos:

<img width="589" height="386" alt="image" src="https://github.com/user-attachments/assets/5d1cbacd-e76c-4afc-b65e-0d211db7e054" />

luego
Detener y eliminar el contenedor:

<img width="490" height="62" alt="image" src="https://github.com/user-attachments/assets/a3ebe7ba-fd70-4f79-9a34-f5b1180ad2de" />



<img width="484" height="62" alt="image" src="https://github.com/user-attachments/assets/2d93ceed-24ce-4617-8c70-dfef1d8be996" />

y luego volvemoa crear 


<img width="589" height="29" alt="image" src="https://github.com/user-attachments/assets/d69c5769-82bc-4c06-b3cd-498dbffedbd8" />

y conectamos con table plus y verificamos que no exista la base de datos test 


<img width="589" height="388" alt="image" src="https://github.com/user-attachments/assets/09404226-f4c0-4f7d-b0ee-144bfb0daaa4" />


Parte 1 finalizada 



##Parte 2: Base de datos con volumen

Crear un volumen persistente:


<img width="927" height="223" alt="image" src="https://github.com/user-attachments/assets/1fe939bc-ebaf-4dd4-ad94-4b7c0a3dcdba" />


Crear el contenedor PostgreSQL asociado al volumen:


<img width="1440" height="72" alt="image" src="https://github.com/user-attachments/assets/ad2a952f-a13a-427a-a467-7d216976bed2" />


Conectarse con el cliente SQL (por ejemplo, TablePlus).

Host: localhost

Port: 5434

User: mi_user

Password: mi_pass


<img width="647" height="677" alt="image" src="https://github.com/user-attachments/assets/75b074b9-388d-4f49-b8ad-93c01969a52f" />

Crear la base de datos test.


<img width="712" height="450" alt="image" src="https://github.com/user-attachments/assets/8073f17f-ebf4-47b9-9594-aa3486b0e257" />

Dentro de test, crear la tabla customer:


<img width="589" height="401" alt="image" src="https://github.com/user-attachments/assets/55f5726e-cb81-4386-88af-c0760491febd" />

Insertar un registro y verificar datos :


<img width="1106" height="717" alt="image" src="https://github.com/user-attachments/assets/1cc21c66-68dd-4389-9773-e9e43cb610b4" />

Detener y eliminar el contenedor:


<img width="591" height="70" alt="image" src="https://github.com/user-attachments/assets/6b2be0a2-3613-4029-8d6a-b7cbd33248cb" />



<img width="573" height="72" alt="image" src="https://github.com/user-attachments/assets/bb2f4dde-14ed-44bc-b630-855c61331ed4" />


Volver a crear el contenedor con el mismo volumen: 


<img width="1443" height="71" alt="image" src="https://github.com/user-attachments/assets/e5dadff1-dada-4a6a-ae1b-879e9e717d8e" />


y verificamos que siga test en tableplus :

<img width="902" height="621" alt="image" src="https://github.com/user-attachments/assets/7f7d329c-7497-4cfd-968d-444377c79806" />


<img width="1090" height="720" alt="image" src="https://github.com/user-attachments/assets/7994741c-5d9c-4d2d-bfd2-abe830dbb58a" />


<img width="1092" height="687" alt="image" src="https://github.com/user-attachments/assets/439a4912-a7a9-4e82-8f20-e398390053d1" />


y listo acbariamos con la practica 


## 9. Resultados esperados:
Al crear y ejecutar el contenedor server_db1 sin un volumen, se puede acceder correctamente a la base de datos PostgreSQL y realizar operaciones básicas como crear tablas e insertar registros.

Luego de eliminar el contenedor server_db1, al volver a crear otro con el mismo nombre, se observa que la base de datos test y los datos insertados ya no existen, confirmando que la información no persiste si no se usa un volumen.

En la segunda parte, al crear el volumen pgdata y asociarlo al contenedor server_db2, los datos creados dentro de la base test permanecen almacenados incluso después de eliminar y volver a crear el contenedor.

Al reconectarse con el cliente SQL (TablePlus, DataGrip o pgAdmin) se verifica que la tabla customer y los registros insertados siguen disponibles.

Se demuestra exitosamente la persistencia de datos gracias al uso de volúmenes en Docker, validando la diferencia entre almacenamiento temporal y permanente dentro de contenedores.

## 10. Bibliografias:
Docker Inc. (2024). Docker Documentation. Recuperado de https://docs.docker.com

PostgreSQL Global Development Group. (2024). PostgreSQL 15 Documentation. Recuperado de https://www.postgresql.org/docs/15/

Turnbull, J. (2018). The Docker Book: Containerization is the New Virtualization (3rd ed.). Turnbull Press.

Mouat, A. (2015). Using Docker: Developing and Deploying Software with Containers. O’Reilly Media.

Merkel, D. (2014). Docker: Lightweight Linux Containers for Consistent Development and Deployment. Linux Journal, (239). Recuperado de https://www.linuxjournal.com/content/docker-lightweight-linux-containers-consistent-development-and-deployment
