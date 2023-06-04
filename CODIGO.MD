# Instalar Node.js en WSL (Windows Subsystem for Linux)

Para utilizar Node.js en WSL (Windows Subsystem for Linux), sigue estos pasos:

1. Abre la terminal de WSL en tu sistema.

2. Actualiza los paquetes existentes ejecutando el siguiente comando:

   ```shell 
    sudo apt update   
    ```
3.Instala curl para poder descargar e instalar Node.js: 
   ```shell  
    sudo apt install curl
   ```
4.Descarga e instala Node.js utilizando curl y apt:    
  ```shell    
    curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash - && sudo apt install -y nodejs
  ```

