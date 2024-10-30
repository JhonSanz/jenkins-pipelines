Para este ejercicio utilizaré microservicios hechos con fastAPi (lo cual no es realmente importante) entonces:

### Microservice repo

1. Supongamos que tengo un microservicio con su respectivo dockerfile
2. Agregaremos un jenkinsfile dentro del proyecto, ya que queremos que todo sea declarativo


### JenkinsFile
1. Para que esto funcione necesitamos instalar el plugin para las credenciales de AWS
2. Entonces vamos a la sección de plugins y buscamos **AWS Credentials**
3. Luego vamos a manage/credentials/ y creamos una nueva global de tipo AWS Credentials, en donde pondremos en access y secret key de algun usuario IAM que tengamos en nuestra cuenta
4. Instalar también el plugin Docker Pipeline 

> También podemos agregar variables de entorno que necesitemos en manage/credentials/


### Pipeline

1. Vamos crear nuevo
2. Nuevo pipeline
3. Al final en el selector de "pipeline definition" seleccionar "Pipeline script from SCM"
4. Si elegimos un repositorio privado debemos generar un token para que jenkins pueda loguearse en github y todas esas cosas... ASí que vamos a nuestra cuenta de github, click al botón con nuestra foto de perfil, setings, personal access tokens y Tokens (classic) https://github.com/settings/tokens
5. Le damos click a agregar credencial y en la opción username and password, ponemos el username de nuestro github y el password el token que generamos
6. Ahora ponemos el nombre de la rama (ya sea master o main)
7. Y finalmente el path con el jenkinsfile
