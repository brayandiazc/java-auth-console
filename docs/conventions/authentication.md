# Convenciones de autenticación y autorización

> Reglas transversales de autenticación. Para cómo funciona la auth en **este**
> proyecto (y sus limitaciones didácticas) ver
> [`../architecture/auth.md`](../architecture/auth.md).
> **Última actualización**: 2026-07-02

## Reglas (cómo debería hacerse)

Aunque este ejercicio las simplifica a propósito, estas son las reglas que aplican
a un proyecto de verdad:

- Las contraseñas se almacenan **hasheadas** con un algoritmo robusto y salt (bcrypt, argon2), nunca en texto plano.
- La recuperación de contraseña usa un **token de un solo uso con expiración**, nunca revela la clave existente.
- La autorización se valida **siempre en el servidor**, en cada operación sensible.
- Los tokens/sesiones se rotan en cada login y tienen expiración.
- El input (email, contraseña) se valida y normaliza en el borde del sistema.

## Cómo se aplica hoy en el proyecto

- Validación de email (`^\S+@\S+\.\S+$`) y contraseña (≥ 6 caracteres) en `UsuarioService.registrar`.
- Sin duplicados de email.
- El resto de reglas (hashing, tokens) se documentan como referencia, pero **no** están implementadas por ser un ejercicio didáctico.

## Ejemplo (verificación conceptual)

```text
# Pseudocódigo de cómo debería verificarse una contraseña en producción
if not verify_hash(password_ingresada, usuario.password_hash):
    rechazar()
```

## Referencias

- [`../architecture/auth.md`](../architecture/auth.md)
- [SECURITY.md](../../SECURITY.md)
- [OWASP — Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
