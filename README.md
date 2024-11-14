# bootcamp-devops-engineer-desafio-01
Entrega 01 de Botocamp

# Importante para correr el pipeline se debe habilitar permisos de Sudo en Jenkins para que pueda correr los comandos Jenkins.
- Primero debemos entrar en la carpeta /etc/sudoers.d/ "Posiblemente necesitaremos permisos de root para hacerlo"
- Luego debemos crear un archivo de nombre jenkins (Esto es un Ejemplo, puede ser cualquier nombre).
- Abrir el archivo y escribir lo siguiente, esto le dara permisos a jenkins para escribir con permisos sudo y no pedir contraseña : jenkins ALL=(ALL) NOPASSWD: ALL  
- Luego de esto debemos guardar los cambios y correr el siguiente comando para asignar los permisos de solo lectura: sudo chmod 440 jenkins
- Luego debemos correr el siguiente comando:  sudo visudo --check  esto para comprobar que todo este ok, no debe dar un resultado como el siguiente:  /etc/sudoers.d/jenkins: parsed OK
- y para finalizar debemos agregar a Jenkins dentro del grupo sudo con el siguiente comando: sudo usermod -a -G sudo jenkins

# Explicación de Pipeline
- pipeline-crear-usuario-y-grupo: Job de pipeline para la creacion de usuario y grupo, se le pedira tres variables para poder crear el nuevo usuario, las variables son: Login, Nombre y Apellido y Departamento
- pipeline-eliminar-usuario-y-grupo: Job de pipeline para la eliminacion de usuario y grupo, se le pedira 2 variables para poder eliminar el usuario y grupo, las variables son: Login, Departamento.

# Explicacion de uso de Password Fijo:
- Se agrego en el pipeline:pipeline-crear-usuario-y-grupo una variable de entorno llamado password = "123456789*", en este caso se decidio colocar una clave sencilla, fija y no una que se genere de forma automatica, para evitar complicarle la vida al usuario a la hora de colocar su primera clave.