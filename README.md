# ⚖️ Veredicto

**Un consejo de 8 agentes de IA que evalúa tu idea antes de que gastes tiempo y dinero en ella.**
No te da la razón: investiga, ataca y defiende la idea por separado, y emite un veredicto con evidencias, stop-loss y alternativas.

[English](README.en.md) · Plugin para [Claude Code](https://claude.com/claude-code) · Licencia MIT

---

## Por qué

Los asistentes de IA tienden a darte la razón. Si les pides montar una web de recetas, la montan aunque el mercado esté saturado. Veredicto le da la vuelta a eso:

- **8 roles independientes** (mercado, finanzas, ejecución, legal, equipo rojo, equipo azul, auditor y juez), cada uno como subagente con su propio contexto y sin ver los informes de los demás.
- **Equipo azul contra equipo rojo:** uno construye la mejor versión de tu idea y el otro intenta demostrar que va a fracasar.
- **Evidencias, no votos.** Hay vetos legales, económicos y de seguridad que ninguna mayoría puede saltarse.
- **Incertidumbre honesta:** cada dato es Conocido, Probable, Posible o Desconocido. Si la confianza es baja, recibes rangos y no números falsos.
- **Stop-loss obligatorio:** todo GO trae presupuesto máximo, hitos y criterios de abandono. El coste hundido no cuenta.
- **Alternativas con freno:** si la idea no pasa, recibes como máximo 3 alternativas con fundamento.
- **Proporcional:** una calculadora no pasa por el Consejo. Un negocio nuevo sí.

## Niveles

| Nivel | Cuándo | Coste |
|---|---|---|
| N0 · Directo | Tareas pequeñas y reversibles | 0 |
| N1 · Chequeo | Cambios en un proyecto existente | 0 subagentes |
| N2 · Ligero | Ideas pequeñas (≤ 100 € y ≤ 40 h, configurable) | 4 subagentes |
| N3 · Completo | Negocios nuevos, inversiones, proyectos grandes | 8-12 subagentes |

Además: **Radar** de oportunidades, revisión de **Cartera** (qué ejecutar, aplazar o abandonar) y **Auditoría** del propio Consejo para medir si acierta.

## Instalación

En Claude Code:

```
/plugin marketplace add frvnmendez/veredicto
/plugin install veredicto@veredicto
```

O a mano: copia `skills/veredicto/` a `~/.claude/skills/` y `agents/` a `~/.claude/agents/`.

## Uso

1. La primera vez, Veredicto crea `veredicto/perfil.md` en tu proyecto. Rellénalo con tu objetivo, presupuesto, horas, tolerancia al riesgo y país.
2. Pídelo con naturalidad:
   - "Quiero montar una web de recetas españolas, **pásalo por el Consejo**."
   - "**Pasa el radar** de oportunidades para alguien con 5 h a la semana."
   - "**Revisa mi cartera** de proyectos."
3. Recibirás un veredicto en `veredicto/expedientes/` y una fila en `veredicto/registro.md`, que el Consejo consultará la próxima vez para no repetir investigaciones ni errores.

Ejemplo completo: [ejemplos/web-de-recetas.md](ejemplos/web-de-recetas.md).

## Estructura

```
.claude-plugin/       plugin.json y marketplace.json
skills/veredicto/     SKILL.md (protocolo) y plantillas
agents/               8 subagentes vd-*
ejemplos/             un expediente de muestra
```

## Límites (honestos)

- Todos los roles usan el mismo modelo, así que sus sesgos están correlacionados. Azul contra rojo y el auditor lo mitigan, pero no lo eliminan.
- Sin herramientas SEO o de mercado de pago, muchos datos serán Probable o Posible.
- Lo legal y fiscal es orientativo. **No sustituye a un profesional.**
- Veredicto recomienda; **la decisión y cualquier pago, contrato o publicación son siempre tuyos.**

## Contribuir

Se aceptan issues y pull requests, sobre todo expedientes reales anonimizados que ayuden a calibrar el Consejo.
