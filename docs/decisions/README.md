# Decisiones de Arquitectura (ADRs)

Esta carpeta registra las **decisiones de arquitectura** del proyecto mediante
_Architecture Decision Records_ (ADRs): documentos cortos que capturan una
decisión relevante, su contexto y sus consecuencias.

## ¿Qué es un ADR y cuándo crear uno?

Crea un ADR cuando tomes una decisión que sea **difícil o costosa de revertir**,
afecte a varias partes del sistema, o que tu yo futuro (o un nuevo integrante)
agradecerá tener documentada.

No hace falta un ADR para decisiones triviales o fácilmente reversibles.

## Convención de numeración y nombres

- Archivos: `NNNN-titulo-en-kebab-case.md` (numeración secuencial empezando en `0001`).
- La plantilla base es [`0000-template.md`](0000-template.md) — cópiala para crear uno nuevo.

## Ciclo de estados

```
Propuesta → Aceptada → (eventualmente) Reemplazada por ADR-XXXX | Obsoleta
```

Los ADRs son **inmutables** una vez aceptados: en lugar de editarlos, se crea uno
nuevo que reemplace al anterior.

## Índice

| ADR                                           | Título                                        | Estado   |
| --------------------------------------------- | --------------------------------------------- | -------- |
| [0001](0001-record-architecture-decisions.md) | Registrar las decisiones de arquitectura      | Aceptada |
| [0002](0002-adopt-project-doc-structure.md)   | Adoptar la estructura de documentación base   | Aceptada |
