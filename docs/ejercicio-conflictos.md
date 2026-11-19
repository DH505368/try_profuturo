# Ejercicio: conflictos entre ramas hacia `develop`

Objetivo: provocar y resolver conflictos reales desde varias ramas mediante Pull Requests.

## Estructura

- Rama base: `develop`
- Archivo compartido: `ejercicios/conflicto-equipo.md`
- Una rama por participante
- Una sola línea modificada por persona

## 1. Preparación

Desde `develop`, actualiza el repositorio y crea una rama por participante:

```bash
git switch develop
git pull origin develop
git switch -c feature/conflicto-nombre
```

Usa nombres distintos, por ejemplo:

```text
feature/conflicto-diego
feature/conflicto-alexis
feature/conflicto-heidi
```

## 2. Archivo que se modificará

Todos trabajan sobre el mismo archivo:

```text
ejercicios/conflicto-equipo.md
```

Cada participante reemplaza únicamente la línea:

```text
Nombre del participante: SIN_ASIGNAR
```

Ejemplos:

```text
Nombre del participante: DIEGO
Nombre del participante: ALEXIS
Nombre del participante: HEIDI
```

No agregues texto después de editar solo esa línea hasta el final del ejercicio.

## 3. Commit y Push

Cada participante guarda su cambio:

```bash
git add ejercicios/conflicto-equipo.md
git commit -m "Ejercicio: agregar nombre del participante"
git push -u origin <nombre-de-tu-rama>
```

## 4. Pull Requests

Desde GitHub, crea un Pull Request por cada rama:

- **Base:** `develop`
- **Compare:** la rama del participante
- Mantén el primer PR sin fusionar hasta que todos estén abiertos.

## 5. Generación del conflicto

Integrando una rama se modificará la línea en `develop`. Las demás ramas seguirán teniendo la versión que crearon desde el estado anterior.

GitHub podría mostrar un conflicto en los PR restantes. Si no aparece inmediatamente:

1. Regresa a tu rama local.
2. Actualízala con los cambios de `develop`:

```bash
git switch develop
git pull origin develop
git switch <tu-rama>
git merge develop
```

3. Resuelve el conflicto en el editor.
4. Guarda el resultado combinado:

```bash
git add ejercicios/conflicto-equipo.md
git commit -m "Resolver conflicto de participantes"
git push origin <tu-rama>
```

Para preservar varios nombres, usa una lista:

```markdown
# Ejercicio de conflictos

## Participantes

- DIEGO
- ALEXIS
- HEIDI
```

No elijas una sola versión si el objetivo es conservar el trabajo de todos.

## 6. Resolver desde GitHub

Si GitHub permite resolver el conflicto en su interfaz:

1. Selecciona **Resolve conflicts**.
2. Elimina los marcadores:

```text
<<<<<<< rama
=======
>>>>>>> develop
```

3. Conserva los nombres de ambas ramas.
4. Selecciona **Mark as resolved**.
5. Confirma con **Commit merge**.
6. Completa el Pull Request.

## 7. Variación: archivo creado simultáneamente

Si varias ramas crean **el mismo archivo inexistente** con contenido distinto, también puede aparecer un conflicto **add/add**.

Para practicarlo:

1. En `develop`, no debe existir `ejercicios/archivo-simultaneo.md`.
2. Cada rama crea ese mismo archivo con su propio nombre.
3. Hace commit y Push.
4. Abre un PR hacia `develop` por cada rama.
5. Fusiona uno y observa la resolución necesaria para los demás.

Git no puede deducir cómo combinar archivos independientes. La resolución manual debe decidir qué contenido conservar.

## Resultado esperado

Al finalizar:

- El repositorio conserva el trabajo de todos los participantes.
- `develop` contiene una sola ruta válida para el ejercicio.
- Cada participante entiende la diferencia entre editar una base común y crear archivos independientes con la misma ruta.
