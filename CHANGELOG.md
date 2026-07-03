# Changelog

Todos los cambios notables de este proyecto se documentan en este archivo.

El formato se basa en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/)
y este proyecto adhiere a [Semantic Versioning](https://semver.org/lang/es/).

## [Unreleased]

## [1.0.0] - 2026-07-02

Primer release oficial. Reúne la aplicación de consola funcional y la estructura
de documentación y gobernanza del proyecto.

### Added

- Registro de usuarios por consola con validación de email y contraseña
  (`UsuarioService`).
- Autenticación (login) de usuarios (`Autenticador`) con inyección de dependencias
  para facilitar el testing con mocks.
- Recuperación de contraseña por email desde el menú de consola (`App`).
- Suite de pruebas unitarias con JUnit 5 y Mockito (`AutenticadorTest`,
  `UsuarioServiceTest`, `RecuperarContrasenaTest`, `AppTest`).
- Reporte HTML de pruebas (Surefire) y reporte de cobertura de código (JaCoCo).
- Integración continua con GitHub Actions (`.github/workflows/ci.yml`): build,
  tests y publicación de reportes en cada push/PR a `main`.
- Estructura de documentación y gobernanza basada en
  [project-starter-template-es](https://github.com/brayandiazc/project-starter-template-es):
  `README`, `CONTRIBUTING`, `CODE_OF_CONDUCT`, `SECURITY`, `LICENSE` (MIT),
  `docs/` (arquitectura, convenciones, decisiones/ADRs, roadmap y glosario) y
  plantillas de issues/PR, Dependabot y labels en `.github/`.

<!--
Enlaces de comparación entre versiones:
[Unreleased]: https://github.com/brayandiazc/java-auth-console/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/brayandiazc/java-auth-console/releases/tag/v1.0.0
-->

[Unreleased]: https://github.com/brayandiazc/java-auth-console/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/brayandiazc/java-auth-console/releases/tag/v1.0.0
