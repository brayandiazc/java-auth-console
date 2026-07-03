# Stack Tecnológico

> Fuente de verdad de las tecnologías y versiones del proyecto.
> **Última actualización**: 2026-07-02

## Lenguaje y build

| Categoría        | Tecnología | Versión | Por qué                                             |
| ---------------- | ---------- | ------- | --------------------------------------------------- |
| Lenguaje/runtime | Java (JDK) | 17      | LTS ampliamente disponible; base del curso.         |
| Build & deps     | Maven      | 3.8+    | Estándar del ecosistema Java, ciclo de vida claro.  |

## Testing y calidad

| Categoría          | Tecnología                    | Versión | Por qué                                             |
| ------------------ | ----------------------------- | ------- | --------------------------------------------------- |
| Framework de tests | JUnit Jupiter                 | 5.10.0  | Estándar moderno para pruebas unitarias en Java.    |
| Mocks              | Mockito                       | 5.2.0   | Aísla dependencias en los tests de `Autenticador`.  |
| Reporte de tests   | maven-surefire-report-plugin  | 3.0.0   | Genera un HTML legible de los resultados.           |
| Cobertura          | JaCoCo (jacoco-maven-plugin)  | 0.8.11  | Mide qué porcentaje del código ejercitan los tests. |

## DevOps & Herramientas

| Categoría | Tecnología                    |
| --------- | ----------------------------- |
| CI/CD     | GitHub Actions (`ci.yml`)     |
| Dependencias | Dependabot (`dependabot.yml`) |
| VCS       | Git                           |

## Versiones mínimas soportadas

- Java (JDK) >= 17
- Maven >= 3.8

## Justificación de elecciones

| Tecnología elegida | Alternativa descartada | Razón                                                    |
| ------------------ | ---------------------- | -------------------------------------------------------- |
| Maven              | Gradle                 | Configuración declarativa más simple para enseñanza.     |
| JUnit 5 + Mockito  | JUnit 4                | API moderna y mejor soporte de mocks/inyección.          |
| Almacenamiento en memoria | Base de datos   | El objetivo del curso es testing y CI, no persistencia.  |
