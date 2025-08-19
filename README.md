# Consigna: Trabajo colaborativo con Git y GitHub

En este ejercicio, trabajarán en equipo (de 2 a 4 personas) utilizando **Git** y **GitHub Classroom**. El objetivo es que cada integrante clone un repositorio, agregue información y maneje los conflictos de fusión (**merge**) en la terminal.

## Pasos a seguir

### 1. Clonar el repositorio
Cada integrante debe clonar el repositorio de GitHub Classroom en su computadora utilizando el siguiente comando:
```bash
 git clone <URL_DEL_REPO>
```

> **Tip:** La URL del repositorio se encuentra en GitHub en el botón verde "Code".

### 2. Crear una nueva rama
Es recomendable que cada persona cree su propia rama antes de hacer cambios:
```bash
 git checkout -b nombre_de_mi_rama
```

### 3. Modificar el archivo
Cada integrante deberá:
- Agregar el objeto con nombre de una **provincia** en una línea nueva dentro del archivo `example.wlk`.
- Modificar la línea que contiene la palabra **"color"**, cambiando su contenido.

Ejemplo de archivo antes de las modificaciones: (no literal)
```

Buenos Aires
Córdoba
color: rojo
```

Ejemplo después de que varias personas hagan cambios:

```
Buenos Aires
Córdoba
Mendoza  # agregado por usuario 1
Santa Fe  # agregado por usuario 2
Tucumán  # agregado por usuario 3
```
~~color: azul  # modificado por usuario 1~~

~~color: verde  # modificado por usuario 2~~
```
color: amarillo  # modificado por usuario 3
```


### 4. Guardar los cambios y hacer commit
Cada integrante debe agregar y confirmar sus cambios:
```bash
 git add example.wlk
 git commit -m "Agregada provincia y modificado color"
```

### 5. Subir los cambios al repositorio
```bash
 git push origin nombre_de_mi_rama
```

### 6. Resolver conflictos al hacer merge
Cada integrante debe fusionar su rama con la rama principal (**main** o **master**) utilizando merge en la terminal:
```bash
 git checkout main  # Ir a la rama principal
 git pull origin main  # Obtener la versión más reciente
 git merge nombre_de_mi_rama  # Intentar fusionar los cambios
```
Si **no hay conflictos**, 
```bash
 git push origin main 
```
o solo git push por que ya estamos parados en main

Si hay **conflictos**, Git marcará el archivo con secciones como esta:
```
color: <<<<<<< HEAD
azul
=======
verde
>>>>>>> rama_de_otro_usuario
```
En VS Code podemos resolverlos a travez de Merge Editor

A la derecha esta lo que vemos en el archivo actual (en este caso el main)
A la izquierda la rama con la que queremos hacer el merge
Abajo como va a quedar.

Para resolverlo, editen el archivo manualmente **(abajo)**,  aca van a tener que decidir como queda el código final
Guardar los cambios

```bash
 git add example.wlk
 git commit -m "Merge branch nombre_de_rama se suele usar"
 git push origin main
```

### 7. Verificar que todo esté correcto
Cada integrante debe actualizar su repositorio local con los cambios finales:
```bash
 git pull origin main
```

## Entrega
Una vez resueltos los conflictos y fusionados los cambios en `main`, confirmen en GitHub que el archivo `example.wlk` tiene todas las modificaciones esperadas.
Fijense que tienen que quedar la misma cantidad de provincias + 1 que integrantes y un solo color. O lo que hayan consensuado.
