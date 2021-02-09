# VSFTPD vs PROFTPD

## VSFTPD

## PROFTPD
Las características principales que tiene actualmente Proftpd son:

  - Tiene un archivo de configuración principal, que contiene directivas y grupos de directivas que son muy intuitivas si has utilizado el servidor web Apache, ya que se basaron en él para crear Proftpd.
  - Dispone de un directorio llamado «.Ftpaccess» que es similar a «.htaccess» de Apache.
  - Es muy fácil configurar múltiples servidores FTP virtuales y servicios FTP anónimos.
  - Diseñado para ejecutarse como un servidor independiente o desde inetd / xinetd, dependiendo de la carga del sistema.
  - Dispone de directorios raíz anónimos que no requieren ninguna estructura de directorio, archivos binarios del sistema u otros archivos del sistema.
  - No hay comando SITE EXEC,evitando así, los problemas que puede acarrear en seguridad.
  - Los directorios y archivos ocultos están basados en permisos de estilo Unix.
  - Dispone de modo autónomo que se ejecuta como un usuario sin privilegios para disminuir las posibilidades de ataques.
  - El registro es compatible con el estándar wu-ftpd, usando utmp / wtmp.
  - Dispone de un servicio para administrar contraseñas ocultas y soporte para cuentas caducadas.
  - Está diseñado de forma modular, eso quiere decir que permite ampliar fácilmente el servidor con módulos como por ejemplo módulos para bases de datos SQL, servidores LDAP, encriptación SSL / TLS, soporte RADIUS, etc.
  - Es compatible y tiene soporte de IPv6.
Para instalarlo solo deberéis abrir un terminal e introducir el comando «sudo apt install proftpd», ya que se encuentra en los principales repositorios de todas las distribuciones Linux.
