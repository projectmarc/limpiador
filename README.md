# Limpia y Separa

Herramienta client-side para limpiar y dividir archivos Markdown exportados desde Google Docs.

## Qué hace

Cuando exportás un documento de Google Docs como Markdown, terminás con dos problemas típicos:

- **Basura al principio**: contenido antes del primer `# Título` real
- **Bloques de imágenes en Base64 al final**: referencias enormes tipo `[ref]: <data:image/png;base64,...>` que inflan el archivo

La herramienta elimina ambas cosas y luego **divide el archivo limpio en archivos `.md` separados**, uno por cada `# Título H1`. Solo los encabezados de primer nivel (`#`) funcionan como punto de corte — `##` y más profundos se ignoran.

## Funcionalidades

- Drag & drop o pegado directo del texto Markdown
- Elimina el contenido previo al primer título y los bloques Base64 del final
- Divide únicamente por encabezados `# H1`
- Sanitiza los nombres de archivo (elimina caracteres especiales, reemplaza espacios con `_`)
- Selección individual de archivos para descargar solo los que necesitás
- Descarga todo junto como `.zip` usando JSZip

## Stack

| Capa | Tecnología |
|---|---|
| UI | HTML + JavaScript vanilla (sin build) |
| Estilos | Tailwind CSS v4 (CDN, build de navegador) |
| ZIP | JSZip 3.10 (CDN) |
| Hosting | GitHub Pages |

Sin backend. Sin framework. Sin bundler. Todo corre en el navegador.

## Uso

1. Abrí la app (URL de GitHub Pages o `index.html` localmente)
2. Arrastrá tu archivo `.md` o pegá el texto
3. Hacé clic en **Procesar y Separar Archivos**
4. Seleccioná los archivos que querés (o dejá todo sin marcar para bajar todos)
5. Descargá individualmente o como `.zip`

## Desarrollo local

```bash
# No hace falta instalar nada — abrí el archivo directamente
open index.html
```

O servilo con cualquier servidor estático:

```bash
npx serve .
```
