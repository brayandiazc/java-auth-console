# Convenciones

Esta carpeta documenta **cómo trabajamos** en el proyecto: reglas y estándares
transversales que aplican al día a día, independientes de cualquier feature
concreta.

> Diferencia con `docs/architecture/`: aquí van las **reglas** ("cómo autenticamos");
> en `architecture/` va **este** proyecto en concreto ("cómo funciona la auth aquí").

## Convenciones incluidas

| Convención                                 | Tema                               |
| ------------------------------------------ | ---------------------------------- |
| [authentication.md](authentication.md)     | Autenticación y autorización       |
| [quality-tooling.md](quality-tooling.md)   | Formato, calidad y git hooks       |
| [secrets.md](secrets.md)                   | Manejo de secretos y credenciales  |
| [testing.md](testing.md)                   | Estrategia y estándares de testing |

## Agregar una convención

Copia [`_template.md`](_template.md), renómbralo en `kebab-case` y documenta el
nuevo tema. Añádelo a la tabla de arriba.
