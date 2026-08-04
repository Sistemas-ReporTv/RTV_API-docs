# Desarrollo y publicación del sitio

## Vista previa local

Requisitos: Ruby y Bundler.

```bash
bundle install
bundle exec jekyll serve --baseurl=""
```

El sitio queda disponible en `http://localhost:4000`.

## Publicación en GitHub Pages

1. Subir los cambios a la rama `main`.
2. En GitHub, abrir **Settings > Pages**.
3. En **Build and deployment > Source**, seleccionar **GitHub Actions**.
4. Ejecutar el flujo **Publicar documentación** o hacer un nuevo push a `main`.

La URL prevista es `https://sistemas-reportv.github.io/RTV_API-docs/`.
