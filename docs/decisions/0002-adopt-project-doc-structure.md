# 0002. Adoptar la estructura de documentación base

- **Estado**: Aceptada
- **Fecha**: 2026-07-02
- **Decisores**: Brayan Diaz C

## Contexto y problema

El repositorio nació como un ejercicio didáctico con solo un `README` y el código.
Faltaban archivos de gobernanza (licencia, seguridad, contribución, changelog) y
una documentación estructurada que sirviera también como ejemplo de buenas
prácticas para quien estudia el proyecto.

## Opciones consideradas

- **Dejar solo el README** — mínimo esfuerzo, pero sin gobernanza ni ejemplo de estructura.
- **Escribir cada archivo a mano** — flexible pero lento e inconsistente.
- **Adoptar [`project-starter-template-es`](https://github.com/brayandiazc/project-starter-template-es)** — estructura probada y coherente, adaptándola al proyecto.

## Decisión

Adoptamos la estructura de la plantilla **project-starter-template-es**, copiando
solo lo aplicable y **borrando lo que no corresponde** a una app de consola sin
base de datos, API ni deployment (p. ej. `docs/architecture/api.md`,
`database.md`, convenciones web y `product/business-model.md`). Se conservó todo
el código y el contenido técnico del `README` original, reorganizado según la
plantilla.

## Consecuencias

**Positivas:**

- Gobernanza completa (LICENSE, SECURITY, CONTRIBUTING, CODE_OF_CONDUCT, CHANGELOG).
- Documentación navegable en `docs/` y plantillas de issues/PR en `.github/`.
- El repo sirve además como ejemplo de estructura para estudiantes.

**Negativas / costos:**

- Hay que mantener la documentación viva (fechas de "Última actualización", índice).

**Neutras / a vigilar:**

- Si el proyecto crece (persistencia, API), habrá que reincorporar documentos que hoy se omitieron.

## Referencias

- [project-starter-template-es](https://github.com/brayandiazc/project-starter-template-es)
- [ADR 0001](0001-record-architecture-decisions.md)
