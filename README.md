# Estimador de baños DELDIM

Aplicación web para valorar en minutos la reforma de un baño y enviar al cliente un PDF con el desglose por partidas, el IVA, las condiciones de pago, las inclusiones y las exclusiones.

No tiene servidor ni base de datos: todo se calcula en el móvil o en el ordenador. Los datos del cliente y los ajustes se guardan solo en el dispositivo donde se usa.

## Qué contiene esta carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La aplicación completa (es el único archivo imprescindible). |
| `manifest.webmanifest` | Permite instalarla como app en el móvil. |
| `sw.js` | Permite abrirla sin conexión después de la primera vez. |
| `icons/` | Iconos de la app. |

## Publicarla en GitHub Pages

1. En GitHub, crea un repositorio nuevo, por ejemplo `deldim-estimador-banos`.
2. Pulsa **Add file → Upload files** y arrastra el contenido de esta carpeta: `index.html`, `manifest.webmanifest`, `sw.js` y la carpeta `icons`. Pulsa **Commit changes**.
3. Ve a **Settings → Pages**. En *Build and deployment* elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guarda.
4. Espera uno o dos minutos. La dirección será `https://TU-USUARIO.github.io/deldim-estimador-banos/`.

Para una prueba rápida basta con subir solo `index.html`. Sin el resto funciona igual, pero no se puede instalar ni usar sin conexión.

## Instalarla en el móvil

- **iPhone (Safari):** botón Compartir → *Añadir a pantalla de inicio*.
- **Android (Chrome):** menú ⋮ → *Instalar aplicación* o *Añadir a pantalla de inicio*.

Al generar el PDF desde el móvil se abre el menú de compartir, para enviarlo por WhatsApp, correo o guardarlo en Archivos. Desde un ordenador se descarga.

## Datos que hay que completar

Faltan el CIF y el domicilio de la empresa. Hay dos formas de añadirlos:

- **Para todos los dispositivos:** edita el bloque `EMPRESA` al principio del `<script>` de `index.html` (busca `CONFIGURACIÓN DE LA EMPRESA`) y vuelve a subir el archivo.
- **Solo en un dispositivo:** botón **Ajustes** de la aplicación.

## Precios

Los precios unitarios son orientativos de mercado y deben validarse antes de usar la aplicación con clientes. Se cambian en **Ajustes → Precios unitarios**, partida a partida. Esos cambios solo afectan al dispositivo donde se hacen. Para fijar precios nuevos para todos, hay que cambiarlos en el código (`ITEMS` en `index.html`).

## Cómo actualizar la aplicación

1. Sube el nuevo `index.html` al repositorio (**Add file → Upload files**, sobrescribe el anterior).
2. Si has cambiado también otros archivos, cambia `deldim-estimador-v1` por `deldim-estimador-v2` en `sw.js`, para que los móviles descarguen la versión nueva.

## Privacidad

El repositorio contiene los precios de venta. Si el repositorio es público, cualquiera con el enlace puede ver la aplicación y esos precios. No contiene datos de clientes. Si no queréis que los precios sean públicos, usad un repositorio privado (GitHub Pages en repositorios privados exige un plan de pago de GitHub) o pedid otra forma de alojarla.

## Aviso legal de la aplicación

Las estimaciones son orientativas, no sustituyen a la visita técnica ni a un presupuesto cerrado. Los tipos de IVA, plazos y condiciones que salen en el PDF deben ser validados por la gestoría y por la dirección de DELDIM.
