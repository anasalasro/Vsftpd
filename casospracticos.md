# CASOS PRACTICOS

## 1. - Version vsftpd instalada

  ` vsftpd -v`
  
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/versionvsftpd.png)


## 2. - Servicios asociados

   ` systemctl restart vsftpd.service `
   ` systemctl reload vsftpd.service `
   ` systemctl status vsftpd.service `
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/instalacionvsftpd.png)
    
## 3. - Fichero de configuración principal

 ` /etc/vsftpd.conf `
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/archivoconf.png)

## 4. - Usuarios creados en la instalación
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/a%C3%B1adeusuariosalcrear.png)
  
## 5. - Creamos un usuario con su directorio de trabajo y le cambiamos el propietario

 ` /etc/vsftpd.conf `
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/creardirectorioyusuarioana.png)
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/cambiamoselgrupo.png)
   
## 6. - Modificamos el archivo de configuración

 ` /etc/vsftpd.conf `
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/configuracion1.png)
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/configuracion1.1.png)
   
## 7. - Quitamos los permisos de escritura

` chmod a-w /home/ana `

  - Añadimos nuestro usuario al fichero /etc/vsftpd.chroot_list
  
` ana:x:1002:127:ana:/home/ana:/bin/sh `

## 8. - Comprobamos que podemos acceder desde Filezilla en el cliente
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/acceso1.png)
   
## 9. - Modificamos el fichero de configuración para que anonymous tenga permiso de lectura en su directorio

 ` /etc/vsftpd.conf `
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/anonymousactivo.png)
   
 `systemctl restart vsftpd.service`
 
 - Comprobamos que tenemos acceso y probamos que nos deja descargar
 
     ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/acessoanonymous.png)
  
 - comprobamos que no podemos subir nada
 
     ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/anonymousnodejasubir.png)

## 10. - Le damos a anónimo permiso de escritura en el directorio sugerencias, que es un subdirectorio de su directorio raíz.

  - Cambiamos l propietario de /ftp, añadimos el subdirectorio de sugerecncias, le cambiamos el propietario y le quitamos los permisos de escritura
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/sugerenciasypermisos.png)
  
  - Modificamos ` /etc/vsftpd.conf `
  
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/permisoescriturasugerencias.png)      
  - Comprobamos que nos deja descargar el archivo welcome del host pero no nos deja subir el archivo prueba1 desde anonymous
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/nosdejabajarwelcomeperonosubirprueba1.png) 
   
  ## 11. - Creación de usuarios virtuales
  -Instalamos
  
 ` apt install libpam-pwdfile `
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/anonymousactivo.png)
   
   -Modificamos 
   
   ` /etc/vsftpd.conf `
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/configuracionusuariosvirtuales.png)
   
   -Creamos el directorio vsftpd y generemos el archivo ftpd.passwd 
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/creamosusuario1ysucarpeta.png)
   
   -Buscamos el archivo /etc/pam.d y lo configuramos 
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/etcpamdvsftpd.png)

   -Creamos el usuario virtual
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/crearusuariovirtual.png)
   
   -Creamos el directorio para el usuario virtual
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/creamosdirectorioparausuario1.png)
   
   -Comprobamos
   
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/comprobacionusuariovirtual.png)
   
 ## 12. - Acceso seguro FTP
  - Instalamos
  
 ` apt install openssl `
 
  - Generamos la clave
  
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/generarclaveSSL.png)

 - Modificamos en /etc/vsftpd.conf
  
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/configuracionSSL.png)
   
  - Comprobamos
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/comprobarSSL.png)
  
