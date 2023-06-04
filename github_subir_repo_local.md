# Para subir tu repositorio local a GitHub, sigue estos pasos:
***

Crea un nuevo repositorio en GitHub. Puedes hacerlo siguiendo estos pasos:

Inicia sesión en tu cuenta de GitHub.
Haz clic en el botón "+" en la esquina superior derecha y selecciona "New repository".
Asigna un nombre al repositorio y, opcionalmente, proporciona una descripción.
Configura las opciones adicionales según tus preferencias (por ejemplo, público o privado).
Haz clic en el botón "Create repository" para crear el repositorio vacío en GitHub.
Copia la URL del repositorio remoto. 
En la página del repositorio en GitHub, encontrarás una sección que muestra la URL del repositorio, ya sea en formato HTTPS o SSH. 
Haz clic en el botón "Code" y copia la URL correspondiente al método que deseas utilizar para la conexión.

Vuelve a tu terminal o línea de comandos y asegúrate de estar ubicado dentro del directorio de tu repositorio local.

Agrega la URL remota a tu repositorio local ejecutando el siguiente comando:

```shell
git remote add origin URL-DEL-REPOSITORIO
```
Reemplaza "URL-DEL-REPOSITORIO" con la URL que copiaste en el paso anterior.

Realiza el primer commit en tu repositorio local:

```shell
git add .
git commit -m "Primer commit"
```
Esto agregará y confirmará los archivos existentes en tu repositorio local.

Finalmente, empuja los cambios al repositorio remoto en GitHub:

```shell
git push -u origin master
```
Dependiendo de tu configuración, es posible que se te solicite ingresar tus credenciales de GitHub.

Después de ejecutar estos pasos, tu repositorio local se habrá subido correctamente a GitHub y estará disponible en tu cuenta de GitHub en la URL proporcionada.
