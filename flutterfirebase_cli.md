Configurar Firebase en Flutter requiere una base sólida con Node.js para habilitar las herramientas de línea de comandos (CLI). Aquí tienes la guía técnica para preparar tu entorno de desarrollo.

---

## 1. Requisitos Previos: Node.js y npm

Para usar la Firebase CLI, necesitas **Node.js** y su gestor de paquetes **npm**.

### Cómo verificar si están instalados
Antes de instalar nada, abre tu terminal (PowerShell, CMD o Terminal de macOS/Linux) y ejecuta:

* **Para Node.js:** `node -v`
* **Para npm:** `npm -v`

> Si el sistema devuelve un número de versión (ej. `v20.10.0`), ya los tienes. Si aparece un error de "comando no reconocido", procede con la instalación.

### Instalación paso a paso (Oficial)
1.  **Descarga:** Ve al sitio oficial [nodejs.org](https://nodejs.org/).
2.  **Versión Recomendada:** Elige la versión **LTS** (Long Term Support), que es la más estable para desarrollo.
3.  **Ejecución:** Abre el instalador descargado (`.msi` en Windows o `.pkg` en macOS).
4.  **Asistente:** Sigue las instrucciones. **Importante:** Asegúrate de que la casilla "Add to PATH" esté marcada para que los comandos funcionen globalmente.
5.  **Reinicio:** Al finalizar, cierra y vuelve a abrir tu terminal para que reconozca los cambios.

### Instalación de manera global
En Node.js, "global" significa que la herramienta estará disponible en cualquier carpeta de tu computadora. Por defecto, el instalador de Node.js configura npm de forma global. Para instalar paquetes nuevos globalmente más adelante, siempre usaremos el flag `-g`.

---

## 2. Instalación de Firebase CLI (`firebase-tools`)

Una vez que npm funciona, instalaremos las herramientas de Firebase.

### El comando de instalación
Ejecuta el siguiente comando en tu terminal:

```bash
npm install -g firebase-tools
```

* **`npm install`**: Indica que queremos descargar un paquete.
* **`-g`**: Instala el paquete de forma **global**.
* **`firebase-tools`**: Es el nombre oficial de la CLI de Firebase.

---

## 3. Uso y Configuración de Firebase

Con la herramienta instalada, ahora debemos vincularla a tu cuenta de Google y a tu proyecto de Flutter.

### Acceder con tu cuenta de Google
Para "loguearte" y que la terminal tenga permiso de modificar tus proyectos de Firebase, usa:

```bash
firebase login
```
1.  La terminal te preguntará si quieres permitir que Firebase recopile información de error (puedes decir `Y` o `n`).
2.  Se abrirá automáticamente una pestaña en tu **navegador web**.
3.  Selecciona tu cuenta de Google y haz clic en **"Permitir"**.
4.  Al ver el mensaje "Success! Logged in as...", puedes cerrar el navegador.

### Inicializar un proyecto de Firebase
Navega en la terminal hasta la carpeta raíz de tu proyecto de Flutter y ejecuta:

```bash
firebase init
```



**Pasos dentro de la inicialización:**
1.  **Selección de funciones:** Usa las flechas y la barra espaciadora para elegir qué servicios usarás (ej. Firestore, Hosting, Functions).
2.  **Proyecto:** Selecciona "Use an existing project" si ya lo creaste en la consola web, o "Create a new project".
3.  **Configuración de archivos:** La CLI creará archivos como `firebase.json` y `.firebaserc` en tu carpeta.

---

## 4. Integración Específica con Flutter (FlutterFire)

Para aplicaciones Flutter modernas, el método recomendado después de instalar la CLI es usar el **FlutterFire CLI**, que automatiza la configuración nativa (Android/iOS):

1.  **Instalar FlutterFire CLI:** `dart pub global activate flutterfire_cli`
2.  **Vincular:** `flutterfire configure`

Esto generará un archivo llamado `firebase_options.dart` que contiene todas las llaves necesarias para que tu app se comunique con Firebase sin configuraciones manuales tediosas.
