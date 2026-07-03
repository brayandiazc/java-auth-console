# Convenciones de calidad y tooling

> Formato, calidad y git hooks del proyecto.
> **Última actualización**: 2026-07-02

## Stack

- **Estilo de código**: definido por [`.editorconfig`](../../.editorconfig) (4 espacios en `.java`/`.xml`).
- **Formato de Markdown**: Prettier vía `.github/scripts/format-markdown.sh`.
- **CI**: GitHub Actions ejecuta build y tests en cada push/PR a `main`.
- **Auditoría de dependencias**: Dependabot (`.github/dependabot.yml`).

## Git hooks

Los hooks **no** se comparten por Git; cada persona los instala en su máquina.
Estrategia sugerida: correr los tests antes de cada commit.

### pre-commit (en cada commit)

Crea `.git/hooks/pre-commit` con:

```bash
#!/bin/bash
cd auth-console
echo "Ejecutando tests antes del commit..."
mvn -q test
if [ $? -ne 0 ]; then
    echo "❌ Los tests fallaron. Commit cancelado."
    exit 1
fi
echo "✅ Todos los tests pasaron."
```

Dale permisos: `chmod +x .git/hooks/pre-commit`.

## Reglas

- El código debe compilar y los tests deben pasar antes del merge.
- El check de CI es **bloqueante** para integrar a `main`.

## Comandos útiles

```bash
mvn clean test                              # Compilar y testear
bash .github/scripts/format-markdown.sh     # Formatear Markdown con Prettier
bash .github/scripts/format-markdown.sh --check   # Solo verificar
```

## Referencias

- [EditorConfig](https://editorconfig.org)
- [Prettier](https://prettier.io/)
