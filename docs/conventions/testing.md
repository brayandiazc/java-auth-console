# Convenciones de testing

> Cómo escribimos y ejecutamos tests en el proyecto.
> **Última actualización**: 2026-07-02

## Stack

- **Framework de tests**: JUnit 5 (Jupiter).
- **Mocks**: Mockito.
- **Cobertura**: JaCoCo.
- **Reporte de resultados**: maven-surefire-report-plugin.

## Tipos de test

| Tipo      | Qué cubre                      | Carpeta                                        |
| --------- | ------------------------------ | ---------------------------------------------- |
| Unitarios | Clases y métodos aislados      | `auth-console/src/test/java/com/ejemplo/auth/` |

## Reglas

- Todo cambio funcional se acompaña de tests.
- Estructura **Arrange-Act-Assert** (AAA): preparar, ejecutar, verificar.
- Un test verifica **una** cosa; el nombre describe el comportamiento esperado.
- Los tests deben ser deterministas (sin dependencia de red, reloj u orden).
- La lógica de dominio se testea sin consola; las dependencias se mockean con Mockito.

## Ejemplo

```java
@Test
void autenticaUsuarioCorrecto() {
    // Arrange
    UsuarioService service = mock(UsuarioService.class);
    when(service.buscarPorEmail("test@mail.com"))
        .thenReturn(new Usuario("test@mail.com", "clave123"));
    Autenticador auth = new Autenticador(service);

    // Act
    boolean resultado = auth.autenticar("test@mail.com", "clave123");

    // Assert
    assertTrue(resultado);
}
```

## Comandos útiles

```bash
mvn test                                        # Ejecutar todos los tests
mvn -Dtest=AutenticadorTest test                # Una clase
mvn -Dtest=AutenticadorTest#autenticaUsuarioCorrecto test  # Un método
mvn surefire-report:report                      # Reporte HTML (Surefire)
# Cobertura JaCoCo: target/site/jacoco/index.html tras `mvn test`
```

## Referencias

- [JUnit 5](https://junit.org/junit5/docs/current/user-guide/)
- [Mockito](https://site.mockito.org/)
- [JaCoCo](https://www.jacoco.org/jacoco/trunk/doc/)
