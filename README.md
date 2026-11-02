# Curso Claude Code Essential

Material del curso **Claude Code Essential** (DoIT Consulting, octubre 2026): manual del estudiante, presentaciones y videos. El curso consta de **4 sesiones de 4 horas**; este repositorio contiene el material de las **sesiones 1 a 3** y dos videos complementarios (Skills y MCP). La Sesión 4 (Plan Mode, modelos y costos, y el mini-proyecto final con Pull Request) todavía no está incluida.

Los laboratorios se practican sobre un proyecto de ejemplo llamado **`api-tareas`** (una API de tareas con pruebas en Vitest).

## Estructura

```
curso-claude-code/
├── documentos/
│   └── Manual del Estudiante — Claude Code Essential.pdf
├── presentaciones/
│   ├── Claude Code Essential — Sesión 1.pptx
│   ├── Claude Code Essential — Sesión 2.pptx
│   └── Claude Code Essential — Sesión 3.pptx
└── videos/
    ├── sesion1-claude-code.mp4
    ├── sesion2-claude-code.mp4
    ├── sesion3-claude-code.mp4
    ├── skills-claude-code.mp4
    └── mcp-claude-code.mp4
```

## Resumen por sesión

| Sesión | Tema | Módulos | Presentación | Video |
|---|---|---|---|---|
| 1 | Fundamentos, contexto y seguridad | 1 y 2 | `Sesión 1.pptx` | `sesion1-claude-code.mp4` |
| 2 | Integraciones y extensibilidad | 3 | `Sesión 2.pptx` | `sesion2-claude-code.mp4` |
| 3 | Flujo de desarrollo asistido | 4 | `Sesión 3.pptx` | `sesion3-claude-code.mp4` |

### Sesión 1 · Fundamentos, contexto y seguridad

**Objetivo:** pasar de la instalación a trabajar con seguridad. Al terminar tendrás Claude Code instalado (`claude doctor` sin errores), tu propio `CLAUDE.md`, reglas que protegen `.env` y piden confirmación al hacer push, y un cambio revertido con rewind.

- **Módulo 1 · Fundamentos**
  - Claude Code es un *agente* (lee el repo, ejecuta comandos y pruebas, edita varios archivos), no un autocompletado.
  - Modelos y alias: `fable`, `opus`, `sonnet`, `haiku` y `opusplan` (Opus planea, Sonnet ejecuta). Se cambian con `/model` o `claude --model`.
  - Esfuerzo de razonamiento con `/effort` (`low` … `max`, `auto`) y `/fast`.
  - Superficies: terminal, VS Code, JetBrains, app de escritorio, navegador y control remoto desde el móvil.
- **Módulo 2 · Contexto y seguridad**
  - `CLAUDE.md`: memoria del proyecto (global, de proyecto y local); `/init`, `/memory` e importaciones con `@`.
  - Gestión del contexto: `/context`, `/compact`, `/clear`, `/resume`, `/recap`.
  - Permisos: modos manual, `acceptEdits`, `plan` y `auto` (se alternan con `Shift+Tab`); reglas `allow` / `ask` / `deny` en `.claude/settings.json`; `/sandbox`.
  - Checkpoints: `Esc Esc` o `/rewind` deshacen lo editado por Claude (no sustituyen a Git).
- **Laboratorios:** 1.1 Instalación y verificación · 1.2 Tu primer `CLAUDE.md` · 1.3 Permisos y rewind.

### Sesión 2 · Integraciones y extensibilidad

**Objetivo:** adaptar Claude Code a tu equipo con cuatro piezas: MCP, hooks, skills y plugins.

- **MCP:** conecta herramientas y datos externos (`claude mcp add`, servidores HTTP y stdio). Alcances `local`, `project` (`.mcp.json`, versionado) y `user`. Se revisa con `claude mcp list` o `/mcp`.
- **Hooks:** comandos que corren en eventos fijos (`PreToolUse`, `PostToolUse`, `UserPromptSubmit`, `Stop`, `SessionStart`), configurados con `/hooks`. Un `PreToolUse` que termina con `exit 2` bloquea la acción.
- **Skills:** procedimientos en `.claude/skills/<nombre>/SKILL.md`; el campo `description` decide cuándo se activan y también se invocan con `/nombre`.
- **Plugins:** paquetes que agrupan todo lo anterior; se instalan desde un marketplace con `/plugin`.
- **Laboratorios:** 2.1 Conectar Context7 y Playwright · 2.2 Hooks de formateo y bloqueo · 2.3 Tu skill y un plugin (`commit-commands`).

### Sesión 3 · Flujo de desarrollo asistido

**Objetivo:** ir del proyecto nuevo al commit revisado, siempre en una rama.

- **Flujo seguro de seis pasos:** rama nueva → prueba que falla → cambio → pruebas en verde → revisión → commit. La prueba que falla primero es la forma de verificar al agente.
- **Proyecto nuevo:** comparar dos stacks, decidir tú, generar el esqueleto con pruebas y README, y registrar la decisión en `CLAUDE.md`.
- **Git y pruebas:** demo del bug de fechas (`!git switch -c`, `/diff`, commit convencional).
- **Revisión de código:** `/code-review` (niveles, `--fix`, `--comment`) y `/security-review`; cada hallazgo repetido es una regla que falta en `CLAUDE.md`.
- **Output styles:** `/output-style` con Default, Concise, Explanatory, Learning y Proactive.
- **Laboratorios:** 3.1 Proyecto nuevo desde cero · 3.2 Corrige un bug con pruebas · 3.3 Revisión y mejora de `CLAUDE.md`.

## Contenido de las carpetas

### 📄 `documentos/`
| Archivo | Descripción |
|---|---|
| `Manual del Estudiante — Claude Code Essential.pdf` | Manual de referencia del curso para el estudiante. |

### 📊 `presentaciones/`
Diapositivas de cada sesión, con agenda, explicación de módulos, laboratorios guiados y un quiz de cierre de tres preguntas.

### 🎬 `videos/`
| Archivo | Tema |
|---|---|
| `sesion1-claude-code.mp4` | Grabación de la Sesión 1 |
| `sesion2-claude-code.mp4` | Grabación de la Sesión 2 |
| `sesion3-claude-code.mp4` | Grabación de la Sesión 3 |
| `skills-claude-code.mp4` | Video complementario: Skills en Claude Code |
| `mcp-claude-code.mp4` | Video complementario: MCP (Model Context Protocol) en Claude Code |

## Ruta de estudio sugerida

1. Leer el **Manual del Estudiante** para tener el panorama general.
2. Por cada sesión (1 → 3): revisar la **presentación**, ver el **video** y repetir los **laboratorios** sobre `api-tareas`.
3. Reforzar con los videos complementarios de **Skills** y **MCP** después de la Sesión 2.
4. Responder el quiz de cierre de cada presentación para autoevaluarte.
