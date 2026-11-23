# Web de Datos Alisios · guía rápida

Esta carpeta es la web completa. No hay que instalar nada: son archivos de texto.

| Archivo | Para qué sirve |
|---|---|
| `index.html` | Todos los textos de la web. Es el que se edita. |
| `styles.css` | El diseño (colores, tipos de letra, adaptación a móvil). Normalmente no se toca. |
| `aviso-legal.html`, `privacidad.html` | Páginas legales, en borrador, con datos por completar. |
| `CNAME` | Indica a GitHub que la web es datosalisios.com. No se toca. |

## 1. Publicar la web (una sola vez)

**a) Cuenta y repositorio en GitHub (gratis)**
1. Cree una cuenta en github.com. Conviene usar equipo@datosalisios.com y un nombre de usuario como `datosalisios`.
2. Pulse **New repository**. Nombre: `web`. Márquelo como **Public** (con el plan gratuito, GitHub Pages solo funciona con repositorios públicos). Cree el repositorio.
3. Pulse **uploading an existing file**, arrastre todos los archivos de esta carpeta (no la carpeta, sino su contenido) y pulse **Commit changes**.

**b) Activar la web**
1. En el repositorio: **Settings → Pages**.
2. En **Source** elija **Deploy from a branch**, rama `main` y carpeta `/ (root)`. Guarde.
3. En **Custom domain** escriba `datosalisios.com` y guarde.

**c) Apuntar el dominio desde OVH**
En OVH: **Dominios → datosalisios.com → Zona DNS**.
1. Elimine los registros `A` y `AAAA` del dominio principal y del `www` que OVH haya puesto por defecto (los de la página de aparcamiento).
2. **No toque** los registros `MX`, `TXT` ni los de nombre `_domainkey` o similares: son los del correo.
3. Añada cuatro registros de tipo `A` para el dominio principal (campo subdominio vacío), uno por cada IP:
   `185.199.108.153` · `185.199.109.153` · `185.199.110.153` · `185.199.111.153`
4. Añada un registro `CNAME` para `www` que apunte a `SU-USUARIO.github.io.` (sustituya por el usuario de GitHub, por ejemplo `datosalisios.github.io.`).
5. Espere. Los cambios de DNS pueden tardar hasta 24 horas.
6. Cuando GitHub reconozca el dominio, en **Settings → Pages** marque **Enforce HTTPS**.

**d) Que el formulario llegue a su correo**
1. Entre en web3forms.com, escriba equipo@datosalisios.com y pida una clave (le llega por correo).
2. En `index.html` busque `TU_CLAVE_DE_WEB3FORMS` y sustitúyalo por la clave.
3. Envíe un mensaje de prueba desde la web.

## 2. Cambiar los textos (cada vez)

1. Entre en el repositorio en GitHub y abra `index.html`.
2. Pulse el **lápiz** (Edit this file).
3. Use Ctrl+F para encontrar el texto. Cada sección empieza con un comentario `EDITAR AQUÍ`.
4. Cambie solo lo que está entre etiquetas, por ejemplo entre `<h3>` y `</h3>`. No borre los signos `<` y `>`.
5. Pulse **Commit changes**. En uno o dos minutos la web está actualizada.

Para **añadir** un servicio, proyecto o persona, copie un bloque completo y péguelo debajo. Para **deshacer** un error, abra el archivo, pulse **History** y restaure la versión anterior.

## 3. Cambiar la identidad visual

En la primera etiqueta de `index.html` (`<html lang="es" data-tema="A">`) cambie `A` por `B` o `C`. Haga lo mismo en `aviso-legal.html` y `privacidad.html`.

## 4. Antes de dar la web por terminada

- Confirmar con cada cliente qué proyectos se pueden mostrar y con qué nombre.
- Rellenar los datos entre corchetes del aviso legal y de la política de privacidad, y pedir a una gestoría que los revise.
- Añadir las fotos (instrucciones en el comentario de la sección Nosotros).
- Cuando se elija identidad, quitar de la línea de Google Fonts las familias que sobren, para que cargue más rápido.
