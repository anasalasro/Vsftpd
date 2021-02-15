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

## 6. - Le damos a anónimo permiso de escritura en el directorio sugerencias, que es un subdirectorio de su directorio raíz.

  - Cambiamos l propietario de /ftp, añadimos el subdirectorio de sugerecncias, le cambiamos el propietario y le quitamos los permisos de escritura
 
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/sugerenciasypermisos.png)
  
  - Modificamos ` /etc/vsftpd.conf `
  
   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/permisoescriturasugerencias.png)      

   ![](https://github.com/anasalasro/Vsftpd/blob/main/Vsftpd/modificarescriturasugerencias.png) 
