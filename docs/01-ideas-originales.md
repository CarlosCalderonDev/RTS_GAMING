---
parte: 01 — Ideas originales
fecha: 2026-11-20
origen: Dictado por voz de Carlos transcrito a texto
tratamiento: Ordenado por tema y limpiado de ruido del dictado; sin añadir ni quitar ideas
---

# Ideas originales de Carlos — 2026-11-20

> **Nota de procedencia.** Carlos dictó este contenido con un traductor de voz a texto y lo pegó en la conversación. Aquí se reordena por tema y se corrigen errores evidentes de transcripción para que sea legible, pero **no se añade ninguna idea nueva**. Las sugerencias del agente están únicamente en [02-diseno-y-coherencia.md](02-diseno-y-coherencia.md).

## 0. Encargo y reglas de colaboración

- Carlos está pensando en realizar y avanzar en una **serie de proyectos**. Quiere que el agente organice y retenga estas ideas para retomarlas en el futuro. Esta es la **primera idea** de la serie.
- Para todas y cada una de sus ideas, el agente **puede aportar consejos, recomendaciones y sugerencias**, incluidas sugerencias de quitar o agregar características. Debe **sugerirlo, no hacerlo**. A Carlos no le molesta que se le diga que una idea o una característica es mala.
- Por ahora **no desea avanzar en código ni en gráficos**. Su intención es clarificar la idea, darle diseño y coherencia y lograr algo estable, porque reconoce que dijo muchas cosas y tal vez no todas combinan o están bien coordinadas.
- Tiene **más ideas relacionadas con este juego** que prefiere agregar después.

## 1. Concepto general

- Un **videojuego para celulares** (aplicación móvil).
- Del **estilo** de los juegos de construcción de aldea y estrategia: desplegar tropas, colocar edificaciones, ir avanzando, gastar recursos para subir de nivel tropas y edificaciones. Un **sistema de crecimiento**.
- Carlos **no desea copiar** ningún juego existente ni hacer algo que implique problemas de derechos de autor; «del estilo» se refiere solo a la mecánica genérica del género.

## 2. Estadísticas de unidades y edificaciones

Carlos nombró dos clases de estadísticas:

1. **Estadística base:** la que tiene por defecto una unidad o una edificación.
2. **Estadística de nivel:** la que incrementa según el nivel de la tropa o de la edificación.

## 3. La característica diferenciadora: crecimiento sin límite anclado al ayuntamiento

Carlos considera que esto es **lo más importante** y lo que lo diferenciará de los demás.

### 3.1 Regla del ayuntamiento (tope relativo)

- Existe una edificación central: el **ayuntamiento**.
- Todos los demás edificios y **también las tropas** pueden subir **hasta el mismo nivel del ayuntamiento, pero no más**.
  - Si el ayuntamiento es nivel 2, todo lo demás puede ser como máximo nivel 2.
  - Si el ayuntamiento es nivel 50, todo lo demás puede ser como máximo nivel 50.
- La intención es que, de manera intuitiva, se pueda percibir y detectar que si alguien tiene ayuntamiento nivel 40 y defensas nivel 20, está **20 niveles por debajo** en sus defensas y, por lo tanto, será más fácil de atacar.

### 3.2 Sin límite de nivel

- Carlos **no quiere que exista un límite de nivel**, ni hoy ni a futuro. Hipotéticamente se podría llegar a nivel 1 000 o a 3 millones.
- Consecuencia deseada: se puede subir el ayuntamiento, pero si no se suben las defensas o las tropas, la aldea será un **lastre** y no podrá competir correctamente, porque no está balanceada lo suficiente.

## 4. Apariencia, estilo y temática

- Como hay una cantidad indefinida de niveles, Carlos ha pensado en cómo se verán edificaciones y tropas. Las apariencias implican un estilo, y el estilo implica una temática.
- Ejemplo: al empezar, una aldea con estilo medieval o prehistórico insinúa una era atrasada, es decir, que se está apenas empezando.
- Pero eso implicaría diseñar la apariencia de cada edificación y cada tropa **para cada temática** a medida que se avanza. Como Carlos es **una sola persona**, considera que eso sería difícil o imposible.
- Observación de Carlos: en cualquier caso, si hay *n* edificios y *n* tropas, tendría que existir **como mínimo un diseño para cada uno**, porque todos existen desde el nivel 1 hasta *n* niveles.

Se le ocurren dos alternativas y pide al agente que proponga otras si las conoce.

### Alternativa A — Un único estilo; solo varía el nivel

- No desgastarse diseñando todos los estilos. Hacer **un único estilo** donde lo único que varía es el nivel de la edificación o de la tropa.
- Esto permitiría, en el futuro, la **personalización de las aldeas**: si un jugador quiere una temática futurista, adquiere (compra) esa temática y Carlos solo implementa esa apariencia. La apariencia se queda para siempre, sin importar el nivel del jugador o de su aldea.
- Implicación: Carlos ya no tendría que producir temáticas para cada nivel o grupo de niveles.

### Alternativa B — Diseños abiertos a la comunidad

- Dejar los diseños abiertos y, mediante **eventos**, que la comunidad diseñe las temáticas. Por ejemplo, un evento para decidir la temática del nivel 1, competiciones de mejores diseños, la gente sube sus diseños y se van implementando.
- **Ventajas:** no tendría que preocuparse por los diseños.
- **Desventajas y temores:**
  - Implicaciones legales: alguien podría insertar un diseño con derechos de autor ajenos o con mensajes ocultos de tipo sexual o ilícito, y eso podría afectarlo legalmente.
  - Para evitarlo tendría que añadir **una capa extra de vigilancia y administración** de los diseños.
  - Como apenas está empezando y no tiene comunidad, tendría **cero diseños**.

## 5. Ataques entre aldeas

- Carlos quiere que **una aldea pueda atacar a otra**.
- Por lo tanto, debe existir **un sistema de equivalencia** para decidir quién puede atacar a quién y quién no.

## 6. Cálculo de estadísticas y progresión por nivel

- Observación de Carlos: en los videojuegos una tropa tiene cierta vida, cierto daño, cierta velocidad de movimiento, cierta velocidad de ataque, etc.; lo mismo las edificaciones. A veces esos valores se calculan en función del nivel.
- Observación adicional: en juegos como los de estrategia histórica, ciertas unidades causan **daño adicional** a ciertos tipos (piqueros o lanceros contra caballería, arqueros contra infantería, por ejemplo ×1.5 de daño).
- **Propuesta de Carlos:** como el juego se basa en una cantidad indefinida de niveles, cada tropa o edificación tendría:
  - una **estadística base** (por defecto), y
  - una **estadística que aumenta según el nivel**.
- **Fórmula propuesta: el nivel multiplica la estadística base.** Ejemplo con 1 000 de vida base: nivel 1 → 1 000; nivel 2 → 2 000; nivel 3 → 3 000.
- Con el tope del ayuntamiento: si el ayuntamiento es nivel 3, esa unidad puede subir como máximo a nivel 3.
- Interpretación de Carlos sobre las ventajas de este sistema:
  - Resuelve la progresión por nivel: ya quedaría determinado el valor de una edificación o unidad tanto en nivel 1 como en nivel 1 000 o 1 millón.
  - Implica tener un diseño ya establecido para el futuro y le ahorra calcular valores nivel por nivel.
  - Para **balancear**, solo tendría que incrementar o disminuir las **estadísticas base** (vida, daño, velocidad de movimiento, velocidad de ataque), no los valores de cada nivel.
- Riesgo que el propio Carlos reconoce: tendría que estar **probando que el juego está nivelado**, qué es justo y qué no.

## 7. Lo que Carlos espera del agente

- Ayudarle a entender **cómo coordinar estas ideas** para que tengan coherencia, se ayuden entre sí y no haya algo que lo afecte.
- Proponer alternativas adicionales a las dos de apariencia si existen.
- Señalar características que convendría quitar o agregar, como sugerencia.
