# Tarea-Conflictos-Git

Creamos la rama "rama-feature" y la subimos

      git checkout -b rama-feature
      echo "Contenido del archivo" > archivo.txt
      git add archivo.txt
      git commit -m "Agrega archivo.txt en la rama-feature"
      git push origin rama-feature

Despues seleccionamos la principal y subimos otro cambio a la rama principal

      git checkout main
      echo "Nuevo contenido en archivo.txt en la rama principal" > archivo.txt
      git add archivo.txt
      git commit -m "Cambio en archivo.txt en la rama principal"
      git push origin main
      
Intentamos fucionalos peronos dara errror
Esto generará un conflicto en archivo.txt

      git merge rama-feature

Resolvemos el conflicto usando la estrategia "ours"

      git checkout --ours archivo.txt
      git add archivo.txt
      git commit -m "Resuelve conflicto usando nuestra versión en archivo.txt"

Volvemos a intentar fusionar la rama-feature y ahora no deberia dar error

      git merge rama-feature

Volvemos a generar el confilcto y ahora lo
resolvemos usando la estrategia "theirs"

      git checkout --theirs archivo.txt
      git add archivo.txt
      git commit -m "Resuelve conflicto usando su versión en archivo.txt"

Volvemos a intentar fusionar la rama-feature y ahora no deeria dar error

      git merge rama-feature

Generamos nuevamente el conflicto pero ahora 
resolveremos el conflicto manualmente editando el archivo.txt
Después de editar, añadimos el archivo y hacemos commit

      git add archivo.txt
      git commit -m "Resuelve conflicto manualmente en archivo.txt"
      git checkout -b rama-resolucion
      git merge main
      git merge rama-feature
      git push origin rama-resolucion

El hacer todo esto nos ayudo a saber como resolver los conflitos que se pueden
al momento de estar trabajando en equipo con conpañeros u otros casos.
