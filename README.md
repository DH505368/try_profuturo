# try_profuturo

Repositorio base para practicar Git y GitHub en un entorno seguro.

## Estructura

- `src/`: código fuente de las prácticas
- `tests/`: pruebas y verificaciones
- `ejercicios/`: ejercicios individuales
- `ejemplos/`: ejemplos de Git o de código
- `scripts/`: scripts auxiliares
- `docs/`: notas y documentación

## Comandos iniciales

```bash
git status
git add .
git commit -m "Crear estructura base del repositorio"
git log --oneline
git branch
```

Puedes crear una rama para una práctica y combinarla después:

```bash
git switch -c practica/nueva-funcion
git add .
git commit -m "Agregar práctica"
git switch main
git merge practica/nueva-funcion
```

## COMANDOS BASICOS

```bash
git clone
git branch
git branch -r
git status
git add .
git commit -m ""
git checkout -b Rama1  # La opción -b crea la rama
git checkout Rama1
git switch Rama1
git push origin
git fetch origin       # Actualizar los últimos cambios
git pull origin
git branch -d Rama1    # Eliminar una rama local
```
