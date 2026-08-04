# RTV API

API independiente para consultar la última actualización disponible de los datos
RTV en formato JSON comprimido.

La documentación funcional para integradores está disponible en
[docs/API_CLIENTES.md](docs/API_CLIENTES.md).

## Configuración de rendimiento

La sección `Rtv` permite ajustar la concurrencia sin recompilar:

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