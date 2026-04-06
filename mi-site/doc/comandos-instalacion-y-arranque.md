# Comandos para instalar y correr mi-site en Windows

## Problema observado

En PowerShell aparecio este error:

```powershell
pnpm : El termino 'pnpm' no se reconoce como nombre de un cmdlet
```

Eso significa que `pnpm` no esta disponible como comando global en la terminal.

La forma correcta de trabajar en esta maquina es usar `Corepack`.

## Requisitos

- Node.js instalado
- PowerShell abierto en Windows

## Paso 1. Verificar Node y Corepack

Desde cualquier terminal, ejecutar:

```powershell
node -v
corepack --version
```

Si ambos responden con una version, puedes seguir.

## Paso 2. Habilitar Corepack

```powershell
corepack enable
```

Opcionalmente puedes comprobar que `pnpm` ya esta disponible a traves de Corepack:

```powershell
corepack pnpm -v
```

## Paso 3. Entrar al proyecto

```powershell
cd "D:\miguel angel\Documents\Estadias\emdash\emdash\mi-site"
```

## Paso 4. Instalar dependencias

```powershell
corepack pnpm install
```

Este es el reemplazo correcto de:

```powershell
pnpm install
```

cuando `pnpm` no existe como comando global.

## Paso 5. Inicializar el proyecto y cargar datos

```powershell
corepack pnpm bootstrap
```

Este comando ejecuta:

- la inicializacion de EmDash
- la configuracion necesaria del proyecto
- la carga del seed de ejemplo

## Paso 6. Correr el proyecto en desarrollo

```powershell
corepack pnpm dev
```

Normalmente el proyecto quedara disponible en una URL local como:

```text
http://localhost:4321/
```

## Paso 7. Compilar para produccion

```powershell
corepack pnpm build
```

## Paso 8. Previsualizar la build

```powershell
corepack pnpm preview
```

## Secuencia corta recomendada

Si vas a empezar desde cero en esta carpeta, esta es la secuencia minima:

```powershell
corepack enable
cd "D:\miguel angel\Documents\Estadias\emdash\emdash\mi-site"
corepack pnpm install
corepack pnpm bootstrap
corepack pnpm dev
```

Si lo que quieres es compilar:

```powershell
corepack enable
cd "D:\miguel angel\Documents\Estadias\emdash\emdash\mi-site"
corepack pnpm install
corepack pnpm build
```

## Comandos utiles

### Ver version de pnpm usando Corepack

```powershell
corepack pnpm -v
```

### Volver a instalar dependencias

```powershell
corepack pnpm install
```

### Volver a sembrar datos

```powershell
corepack pnpm seed
```

### Revisar tipos

```powershell
corepack pnpm typecheck
```

## Si vuelve a salir el error de pnpm

Si vuelve a aparecer algo como:

```powershell
pnpm : El termino 'pnpm' no se reconoce
```

no uses `pnpm` solo.

Usa siempre esta forma:

```powershell
corepack pnpm <comando>
```

Ejemplos:

```powershell
corepack pnpm install
corepack pnpm bootstrap
corepack pnpm dev
corepack pnpm build
```

## Resumen final

La forma correcta de trabajar este proyecto en tu entorno actual es:

```powershell
corepack enable
cd "D:\miguel angel\Documents\Estadias\emdash\emdash\mi-site"
corepack pnpm install
corepack pnpm bootstrap
corepack pnpm dev
```

Y para compilar:

```powershell
corepack pnpm build
```