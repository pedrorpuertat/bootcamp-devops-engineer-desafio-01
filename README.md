# bootcamp-devops-engineer-desafio-01
Entrega 01 de Botocamp

# Importante para correr el pipeline se debe habilitar permisos de Sudo en Jenkins para que pueda correr los comandos Jenkins.
- Primero debemos entrar en la carpeta /etc/sudoers.d/ "Posiblemente necesitaremos permisos de root para hacerlo"
- Luego debemos crear un archivo de nombre jenkins (Esto es un Ejemplo, puede ser cualquier nombre).
- Abrir el archivo y escribir lo siguiente, esto le dara permisos a jenkins para escribir con permisos sudo y no pedir contraseña : jenkins ALL=(ALL) NOPASSWD: ALL  
- Luego de esto debemos guardar los cambios y correr el siguiente comando para asignar los permisos de solo lectura: sudo chmod 440 jenkins
- Y para finalizar debemos correr el siguiente comando:  sudo visudo --check  esto para comprobar que todo este ok, no debe dar un resultado como el siguiente:  /etc/sudoers.d/jenkins: parsed OK
- y para finalizar debemos agregar a Jenkins dentro del grupo sudo con el siguiente comando: sudo usermod -a -G sudo jenkins