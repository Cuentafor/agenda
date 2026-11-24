# Agenda semanal · Guía de puesta en marcha

Son unos 15 minutos. Necesitas una cuenta de Google (para Firebase) y tu cuenta de GitHub.

## 1. Crear el proyecto en Firebase
1. Entra en https://console.firebase.google.com y pulsa **Crear un proyecto**. Ponle un nombre (por ejemplo `agenda-familia`). Google Analytics no hace falta.
2. **Acceso anónimo:** menú *Compilación → Authentication → Comenzar → Sign-in method* → activa **Anónimo** y guarda.
3. **Base de datos:** menú *Compilación → Realtime Database → Crear base de datos*. Elige la ubicación **Europa (europe-west1)** y empieza en **modo bloqueado**.
4. **Reglas:** en Realtime Database, pestaña **Reglas**. Borra lo que hay y pega el contenido de `reglas-firebase.json`.
   - Cambia las **dos** apariciones de `CAMBIA-ESTE-CODIGO` por tu código (mejor de 6 o más caracteres, mezclando letras y números).
   - Pulsa **Publicar**.
5. **Registrar la app web:** *Configuración del proyecto (rueda dentada) → General → Tus apps →* icono **</>** (Web). Ponle un nombre y **no** marques Firebase Hosting.
6. Copia el bloque `firebaseConfig` que te muestra. Si no trae `databaseURL`, cópiala de la parte de arriba de Realtime Database (empieza por `https://` y termina en `firebasedatabase.app`).

## 2. Poner la configuración
Abre `config.js` y sustituye los `PEGA_AQUI` por tus valores (o pásale a Claude el bloque y te devuelve el archivo listo).

## 3. Publicar en GitHub Pages
1. En GitHub, **New repository** → nombre, por ejemplo `agenda` → **Public** → *Create repository*.
2. **Add file → Upload files** y sube todos los archivos de esta carpeta (menos esta guía si quieres). *Commit changes*.
3. *Settings → Pages →* en **Branch** elige `main` y carpeta `/ (root)` → **Save**.
4. En un par de minutos estará en `https://TU-USUARIO.github.io/agenda/`.

## 4. Autorizar el dominio (para el acceso anónimo)
En Firebase: *Authentication → Settings → Dominios autorizados → Añadir dominio* → `TU-USUARIO.github.io`.

## 5. Usarla
- **Ver:** cualquiera con el enlace, sin cuentas.
- **Editar:** botón **🔒 Editar** → escribe el código. Queda recordado en ese móvil. Se puede salir desde el menú **⋯**.
- **Instalar en iPhone:** abre el enlace en **Safari → Compartir → Añadir a pantalla de inicio**. La app instalada pedirá el código una vez más.
- **Instalar en Android:** en Chrome, menú **⋮ → Instalar aplicación** (o *Añadir a pantalla de inicio*).
- **Tipos:** menú **⋯ → Tipos de actividad** (o «⚙️ Gestionar tipos» al crear una actividad). Son comunes a todas las agendas.

## Cambiar el código más adelante
Edita las reglas en Firebase con el código nuevo (las dos apariciones) y publica. Los móviles que tenían el antiguo dejarán de poder editar y pedirán el nuevo.

## Notas
- El punto junto al nombre indica la conexión: verde = conectado.
- La primera vez que alguien con código guarde un cambio, se crea la agenda en Firebase con el horario de Aldara como punto de partida.
- El plan gratuito de Firebase (Spark) sobra para este uso.
