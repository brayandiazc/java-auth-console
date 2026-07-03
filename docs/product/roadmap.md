# Roadmap — Sistema de Autenticación por Consola en Java

> Estado y dirección del proyecto. Documento vivo.
> **Última actualización**: 2026-07-02

## Leyenda

- ✅ Hecho
- 🚧 En curso
- 📋 Planificado
- ⏸️ Diferido

## Visión

Ser un proyecto de referencia, claro y comentado, para aprender fundamentos de
DevOps y testing en Java: pruebas unitarias, cobertura, integración continua y
buenas prácticas de repositorio.

## Estado actual

- ✅ Registro, login y recuperación de contraseña por consola.
- ✅ Suite de tests con JUnit 5 y Mockito.
- ✅ Reportes de Surefire y cobertura con JaCoCo.
- ✅ CI con GitHub Actions.
- ✅ Documentación y gobernanza basadas en la plantilla base.

## Próximos pasos

### Calidad y didáctica

- [ ] Añadir umbral mínimo de cobertura en JaCoCo (build falla si baja).
- [ ] Publicar el reporte de cobertura como artefacto en CI.
- [ ] Añadir badge de cobertura al README.

### Producto (ejercicios sugeridos)

- [ ] Hashear contraseñas (bcrypt/argon2) como ejercicio de seguridad.
- [ ] Reemplazar la recuperación por un flujo con token de un solo uso.
- [ ] Persistir usuarios (archivo o base de datos) como ejercicio avanzado.

## Fuera de alcance

- Interfaz gráfica o API HTTP: el foco es la consola y las prácticas de testing/DevOps.

## Cómo se actualiza este documento

- Revisar al cerrar cada versión/fase.
- Las decisiones que cambian el rumbo se registran como ADRs en [`../decisions/`](../decisions/README.md).
