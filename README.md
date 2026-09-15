# Sitio de contacto — Alcalde de Santiago

Página estática de una sola pieza (`index.html`), sin dependencias de build.
Las imágenes van embebidas en el propio HTML (base64), así que no hay carpeta
`assets` que subir aparte.

## Opción A — Arrastrar y soltar (sin instalar nada)

1. Entra a https://vercel.com/new
2. En la parte de abajo hay una zona "Deploy without Git" — arrastra ahí esta
   carpeta completa (o solo `index.html`).
3. Vercel lo publica y te da una URL tipo `tu-proyecto.vercel.app`.

## Opción B — Vercel CLI

```bash
npm install -g vercel
cd carpeta-del-proyecto
vercel        # sigue las preguntas (crea el proyecto)
vercel --prod # publica en producción
```

## Opción C — Desde GitHub

1. Sube esta carpeta a un repo de GitHub.
2. En https://vercel.com/new, elige "Import Git Repository" y selecciona el repo.
3. Framework preset: **Other** (no hace falta build command ni output directory,
   Vercel sirve `index.html` directamente).
4. Deploy.

## Dominio propio

Una vez desplegado, en el proyecto dentro del dashboard de Vercel ve a
**Settings → Domains** y agrega tu dominio (por ejemplo
`contacto.ayuntamientosantiago.gob.do`), siguiendo las instrucciones de DNS
que te da Vercel (normalmente un registro CNAME o A).

## Actualizar contenido más adelante

Todo el sitio vive en `index.html`: textos, estilos y JS están en ese único
archivo. Para cambiar una foto hay que volver a convertirla a base64 y
reemplazar el `data:image/...;base64,...` correspondiente — o, más simple,
pídele a Claude el cambio y te entrega el archivo ya actualizado.
