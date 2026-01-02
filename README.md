# IA Avanzada NavMeshes
### Cambios en el proyecto

- Modificación sobre Escena 2.
- He creado un nuevo NPC "Monster" al cual le he añadido el **AIController** script y he puesto su tag a "AI". Descargué el asset desde Unity Store. En el script puse el **Target** como "CombatJane" para que siguiera al jugador.
- A este NPC le adjunté el componente **Nav Mesh Agent** y he creado un **Agent Type** "Monster" en **Navigation**. Le puse una altura de 4 metros y radio de 1, con el step height a 1.
- En el Nav Mesh Agent le puse la velocidad a 8 y el stopping distance a 2 metros. Para el **Obstacle Avoidance** puse 1 en el **Radius** y 4 en el **Height**. En el **Area Mask** puse "Walkable, Rock" para limitarle a esas zonas.
- Configuré unas animaciones muy básicas para simluar el caminar del monstruo.
- En el panel de **Navigation** añadí un area nuevo, "MonsterProhibited".
- A los demás NPS (chompers) les añadí en la **Area Mask** "MonsterProhibited" para que puedan entrar en esa zona.
- En el objeto "Environment" añadí otro **NavMesh Surface** con el Agent Type "Monster".
- Creé una nueva superficie usando un cube (podría haber sido un plano), y a este le añadí un **NavMesh Modifier**, y habilitando las casillas **Apply to children** y **Override Area**. En el **Area Type** puse "MonsterProhibited".
- Volví al objeto Environment y en los dos NavMesh Surface les hice un **Bake** para que aplicara los cálculos para incluir esta nueva zona para todos los tipos de agentes.
- El resutlado es que todos los NPCs salvo el monstruo pueden entrar en la zona nueva.

[Vínculo al repositorio en Github](https://github.com/jnomada/IANavMeshes)