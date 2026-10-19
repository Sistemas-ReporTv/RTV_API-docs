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

Las versiones publicadas quedan disponibles en:

- Español: `https://sistemas-reportv.github.io/RTV_API-docs/`
- Inglés: `https://sistemas-reportv.github.io/RTV_API-docs/en/`
- Portugués: `https://sistemas-reportv.github.io/RTV_API-docs/pt/`

## Configuración de rendimiento

Para quienes administran la API, la sección `Rtv` permite ajustar la
concurrencia sin recompilar:

```json
{
  "ResourceParallelism": 2,
  "WorkerParallelism": 4,
  "CompressionLevel": "Optimal"
}
```

- `ResourceParallelism` limita los recursos proyectados y publicados en paralelo por generación.
- `WorkerParallelism` limita las generaciones simultáneas. Las generaciones del mismo proceso se ejecutan en orden; procesos distintos pueden ejecutarse en paralelo.
- El producto de ambos valores no puede superar 8. Los valores predeterminados son 2 y 4.
