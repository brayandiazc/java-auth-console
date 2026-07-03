# Política de Seguridad

Este documento describe cómo reportar vulnerabilidades en **Sistema de Autenticación por Consola en Java** y qué prácticas de seguridad seguimos en el repositorio.

> **Nota educativa**: este proyecto es un ejercicio didáctico de fundamentos de
> DevOps y testing. **No está pensado para producción**: las credenciales se
> guardan en memoria sin hashear y la recuperación de contraseña muestra la clave
> en texto plano por consola. Estas decisiones son deliberadas para simplificar el
> aprendizaje y **no deben replicarse en un sistema real**. Ver
> [`docs/architecture/auth.md`](docs/architecture/auth.md) y
> [`docs/conventions/authentication.md`](docs/conventions/authentication.md) para
> las reglas que sí aplican a un proyecto de verdad.

## Tabla de Contenidos

- [Reporte de Vulnerabilidades](#reporte-de-vulnerabilidades)
  - [Información a incluir](#información-a-incluir)
  - [Qué esperar](#qué-esperar)
- [Versiones Soportadas](#versiones-soportadas)
- [Alcance](#alcance)
- [Fuera de Alcance](#fuera-de-alcance)
- [Manejo de Secretos](#manejo-de-secretos)
- [Dependencias](#dependencias)
- [Prácticas de Desarrollo Seguro](#prácticas-de-desarrollo-seguro)
- [Contacto](#contacto)

## Reporte de Vulnerabilidades

Si descubres una vulnerabilidad de seguridad, **no abras un issue público**. Repórtala de forma privada a través de uno de estos canales:

- **Email**: <brayandiazc@gmail.com> (preferido — usa un asunto que empiece con `Security:` para priorizarlo).
- **GitHub Security Advisories**: pestaña _Security_ del repositorio → _Report a vulnerability_.

### Información a incluir

Para poder triagear y responder rápido, incluye:

1. Descripción clara de la vulnerabilidad.
2. Pasos para reproducirla (PoC si es posible).
3. Impacto estimado (qué se puede comprometer).
4. Versión / commit afectado.
5. Sugerencia de mitigación (opcional).

### Qué esperar

| Etapa                              | Tiempo objetivo             |
| ---------------------------------- | --------------------------- |
| Acuse de recibo                    | 48 horas hábiles            |
| Triage inicial y severidad         | 5 días hábiles              |
| Corrección de severidad alta       | próxima release planificada |
| Corrección de severidad media/baja | próxima release planificada |

## Versiones Soportadas

| Versión                 | Soporte de seguridad |
| ----------------------- | -------------------- |
| `main` (rama principal) | Sí                   |
| Releases / tags previos | Solo el último tag   |

## Alcance

Superficies **en alcance** para reportes de seguridad:

- Código fuente del repositorio (`auth-console/`).
- Pipeline de CI/CD del repositorio (`.github/workflows/`).

Ejemplos de hallazgos de interés (más allá de las limitaciones didácticas ya conocidas):

- Inyecciones (comandos, deserialización).
- Vulnerabilidades en dependencias con impacto demostrable.
- Configuraciones inseguras en el workflow de CI.

## Fuera de Alcance

Los siguientes hallazgos **no califican** como vulnerabilidades:

- Las limitaciones didácticas ya documentadas (contraseñas sin hashear en memoria,
  recuperación que muestra la clave). Son intencionales.
- Reportes de scanners automáticos sin impacto demostrado.
- Vulnerabilidades en dependencias sin vector de explotación en este proyecto.

## Manejo de Secretos

- **Nunca** commitear secretos en texto plano (claves de API, tokens, contraseñas, certificados privados, archivos `.env` con valores reales).
- En CI/CD, los secretos viven como **secrets cifrados** de GitHub Actions.
- Ver [`docs/conventions/secrets.md`](docs/conventions/secrets.md).

## Dependencias

- Las versiones de dependencias se fijan en `auth-console/pom.xml`.
- Las actualizaciones automáticas se gestionan con **Dependabot** (`.github/dependabot.yml`) — PRs revisados por humanos antes del merge.

## Prácticas de Desarrollo Seguro

Reglas que aplican a un proyecto real (aunque este ejercicio las simplifique):

- Hashear contraseñas con un algoritmo robusto (bcrypt, argon2…), nunca en texto plano.
- Validar y normalizar el input en todos los bordes del sistema.
- No loguear secretos, contraseñas ni PII innecesaria.
- Toda PR requiere revisión antes del merge (ver [CONTRIBUTING.md](CONTRIBUTING.md)).

## Contacto

- **Reportes de seguridad**: <brayandiazc@gmail.com> (asunto: `Security: …`)
- **Consultas generales**: <brayandiazc@gmail.com>

---

> Versión: 1.0 — Última actualización: 2026-07-02
