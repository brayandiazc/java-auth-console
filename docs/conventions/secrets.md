# Convenciones de secretos y credenciales

> Cómo gestionamos secretos en el proyecto.
> **Última actualización**: 2026-07-02

## Filosofía

- Los secretos **nunca** se commitean en texto plano.
- Separación clara entre **configuración** (no sensible) y **secretos** (sensible).

> Nota: este proyecto no requiere secretos en tiempo de ejecución (es una app de
> consola en memoria). Esta convención documenta la práctica para cuando el
> proyecto —o quien lo use como base— sí los necesite.

## Dónde vive cada cosa

| Tipo               | Dónde                                         |
| ------------------ | --------------------------------------------- |
| Secretos locales   | Archivo `.env` (ignorado por Git)             |
| Secretos de CI/CD  | Secrets del proveedor (GitHub Actions)        |

## Reglas

- `.env` está en `.gitignore`; solo se versionaría `.env.example` (sin valores) si existiera.
- Comparte secretos con nuevos colaboradores **fuera de banda** (nunca por git, email plano ni chat público).
- Si un secreto se commitea por error: **rota el secreto primero**, luego limpia la historia. Asume que ya está comprometido.

## Referencias

- [SECURITY.md](../../SECURITY.md) — política de seguridad.
- [GitHub Actions — Secrets cifrados](https://docs.github.com/actions/security-guides/encrypted-secrets)
