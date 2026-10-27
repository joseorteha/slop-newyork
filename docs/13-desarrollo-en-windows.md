# 13 — Desarrollo en Windows y Git

## Límite del entorno

Raíz autorizada: `C:\Users\joseo\Documents\PROYECTOS 2026\JUEGO`. Todas las escrituras del proyecto deben quedar dentro. No configurar Git global, instalar herramientas en el sistema ni crear carpetas vecinas como efecto lateral sin revisar el alcance.

Los cambios remotos del fork no se descargan solos. No afirmar que una operación GitHub modificó el disco local.

## Preparación de una carpeta existente

Abrir PowerShell o Codex local con JUEGO como carpeta. Estos comandos son instrucciones, no acciones realizadas por esta entrega:

```powershell
Set-Location -LiteralPath 'C:\Users\joseo\Documents\PROYECTOS 2026\JUEGO'
Get-Location
Get-ChildItem -Force
git --version
bun --version
```

Si faltan herramientas, documentar la instalación necesaria antes de ejecutar instaladores que escriben fuera de JUEGO. Si hay AGENTS.md u otras instrucciones locales, leerlas. No borrar archivos para hacer espacio al clon.

### Carpeta vacía

Solo después de comprobar que está vacía:

```powershell
git clone --branch docs/el-ultimo-taller https://github.com/joseorteha/slop-newyork.git .
git status --short
git remote -v
```

El punto clona en JUEGO directamente, sin anidar otra carpeta slop-newyork. Si la rama documental ya se integró en main, se puede clonar main en su lugar.

### Carpeta con repositorio

No clonar encima. Inspeccionar primero:

```powershell
git status --short
git remote -v
git branch --show-current
```

Si origin corresponde al fork y no hay cambios incompatibles, descargar y cambiar a la rama acordada. Conservar modificaciones locales; no hacer reset --hard ni clean para resolver diferencias.

## Remotos y ramas

origin: fork de joseorteha. upstream: mrdoob/slop-newyork. Añadir upstream solo si no existe; si existe, comprobarlo, no sobrescribirlo.

```powershell
git remote add upstream https://github.com/mrdoob/slop-newyork.git
```

Usar docs/el-ultimo-taller para esta entrega y ramas feat/ o fix/ para cambios posteriores. Revisar diferencias antes de commit. No integrar automáticamente cambios futuros de upstream: pueden afectar materiales, shaders y arranque.

## Herramientas futuras

La base aún no incluye package.json ni scripts propios de Bun. No asumir que bun run dev o bun run build funcionan ahora. F0 debe añadir y verificar manifiesto, lockfile y comandos dev, build, typecheck y test.

Para la aplicación heredada, las pruebas usan node:test; no prometer reemplazo transparente por bun test. Adaptar de forma acotada o documentar un ejecutor de compatibilidad. Node como herramienta de pruebas no equivale a un servidor Node en el juego.

Al instalar dependencias, evitar secretos en archivos versionados. Usar rutas entre comillas y scripts portables por los espacios y caracteres del directorio.

Ver [backlog](17-backlog.md).
