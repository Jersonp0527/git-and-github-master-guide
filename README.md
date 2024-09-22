# Git&GitHub Master Guide
Esta es una guía paso a paso para aprender a usar *Git* y *GitHub*.

## 1. Configurar Git por primera vez
Lo primero que debes hacer es configurar tu nombre de usuario y correo electrónico global en Git. Este correo es el que se asociará con tus commits en cualquier proyecto.
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu-email@example.com"
```

Puedes verificar tu configuración con:
```bash
git config --global --list

```
> [!NOTE]
> Para ejecutar esta linea de código se requiere *less* cómo dependencia, si no lo tienes instalado ejecuta:
```bash
# Para una distribución Debian o derivados.
sudo apt-get install less
```

## 2. Inicializar un nuevo repositorio

Ahora que Git está configurado, puedes inicializar un repositorio:
1. Crea una carpeta o navega a la carpeta que quieras convertir en un repositorio:
```bash
mkdir nombre-del-proyecto
cd nombre-del-proyecto
```
2. Inicializa el repositorio Git en esa carpeta:
```bash
git init
```
*Esto crea un repositorio vacío*

## 3. Añadir archivos al repositorio
Una vez que tienes archivos en tu proyecto, puedes agregar archivos al área de preparación (staging area) antes de confirmarlos (commit):
1. Crea o añade archivos en tu directorio.
2. Verifica el estado de los archivos no rastrados
```bash
git status
```
3. Añade los archivos al área de preparación:
```bash
git add archivo.txt
```
O para añadir todos los archivos
```bash
git add .
```

## 4. Hacer un commit
Una vez que los archivos están en el área de preparación, haz un commit para guardar los cambios:
```bash
git commit -m "Mensaje del commit"
```

## 5. Conectar el repositorio local a GitHub
Ahora es el momento de conectar el repositorio local con GitHub. Para ello:
1. Crea un nuevo repositorio en GitHub desde la interfaz web, sin seleccionar ninguna opción como "README" ni archivos .gitignore (será completamente vacío).
2. Copia la URL del repositorio (será algo como https://github.com/usuario/nombre-repo.git).
3. Luego, desde la consola, enlaza tu repositorio local con GitHub:
```bash
git remote add origin https://github.com/usuario/nombre-repo.git
```

## 6. Autenticación con github
A partir de agosto de 2021, GitHub ya no permite la autenticación por contraseña. Ahora debes usar un token de acceso personal (PAT) o SSH. Aquí te muestro cómo usar ambas opciones.

Opción 1: Usar Token de Acceso Personal (PAT)
1. Genera un token desde tu configuración de GitHub, seleccionando los permisos adecuados (mínimo repo).
2. La primera vez que hagas git push, se te pedirá tu usuario y token:
    - Usuario: tu nombre de usuario de GitHub.
    - Contraseña: el token que generaste.
    Git te pedirá que lo ingreses, pero puedes configurarlo para que no te lo pida cada vez usando:
    ```bash
    git config --global credential.helper store
    ```
    Esto almacena el token para futuras interacciones.

