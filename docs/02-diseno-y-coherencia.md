---
parte: 02 — Diseño y coherencia
fecha: 2026-11-20
actualizado: 2026-11-21
version: 2
autor: Agente, a partir de las ideas de Carlos
estado: Borrador vivo; se actualiza a medida que Carlos agrega ideas o decide
---

# Documento de diseño — «Proyecto Aldea» (nombre provisional)

> **Cómo leer este documento.** Cada afirmación está etiquetada:
>
> - **[Decisión de Carlos]** — algo que Carlos dijo que quiere. No se modifica sin su indicación.
> - **[Observación]** — consecuencia técnica o matemática que se deriva de las decisiones; verificable.
> - **[Sugerencia]** — propuesta del agente. Carlos decide si la adopta, la cambia o la descarta.
> - **[Pregunta]** — dato que falta y que solo Carlos puede responder.
>
> Las palabras de Carlos están en [01-ideas-originales.md](01-ideas-originales.md) y [03-ideas-de-carlos-en-el-debate.md](03-ideas-de-carlos-en-el-debate.md). Los números de este documento (puntos, precios, multiplicadores) son **valores de ejemplo para razonar**, no valores finales.

## 1. Propósito y alcance actual

- **[Decisión de Carlos]** Juego móvil de construcción de aldea y estrategia con crecimiento, de mecánica genérica del género y sin copiar ningún juego existente.
- **[Decisión de Carlos]** Fase actual: **solo diseño conceptual**, debatido en conversación y guardado como documentación. Nada de código ni de gráficos hasta que la idea sea coherente y estable. El proyecto vive en este repositorio desde el 2026-11-21.
- **[Decisión de Carlos]** Carlos es un **solo desarrollador**. Toda decisión de diseño debe respetar esa restricción de capacidad.

## 2. Vocabulario

| Término | Significado |
|---|---|
| **Identidad mecánica** | Lo que una unidad *hace*: sus números y comportamientos. No tiene temática. |
| **Identidad temática** | Cómo se *llama* y cómo se *ve* la unidad. Un «arquero» y un «francotirador» pueden ser la misma identidad mecánica. |
| **Diseño** | La receta de una unidad: el reparto de puntos más las insignias elegidas. |
| **Presupuesto** | Los puntos disponibles para un diseño. |
| **Insignia** | Pieza que da un comportamiento a la unidad (palabra de Carlos: «cuadrito, insignia»). Cuesta puntos. |
| **Casilla** | El hueco de la unidad donde va una insignia. Cada casilla admite una sola. Es la palabra que usó Carlos. |
| **Mesa de diseño** | Espacio del Laboratorio que guarda un diseño y tiene nivel. |
| **Clase** | Etiqueta de una unidad o edificio que usan las contras (por ejemplo, Grande o Edificio). |
| **Contra** | Multiplicador de daño de un atacante especializado contra una clase de objetivo. |

## 3. Reglas acordadas

| Regla | Enunciado | Estado |
|---|---|---|
| **R1. Componentes de estadística** | Cada unidad y edificación tiene una estadística **base** y una componente que crece con el **nivel**. | Decidido 2026-11-20 |
| **R2. Fórmula lineal** | Valor efectivo = `base × nivel` (solo para las cantidades; ver R8). | Decidido 2026-11-20 |
| **R3. Tope del ayuntamiento** | Ningún edificio ni tropa puede superar el nivel del ayuntamiento. | Decidido 2026-11-20 |
| **R4. Sin límite de nivel** | No existe nivel máximo, ni ahora ni a futuro. | Decidido 2026-11-20 (firme) |
| **R5. Legibilidad del desbalance** | Debe percibirse de forma intuitiva que una aldea con ayuntamiento 40 y defensas 20 está «20 niveles atrás». | Decidido 2026-11-20 |
| **R6. Ataques entre aldeas** | Una aldea puede atacar a otra; habrá un sistema de equivalencia para emparejar. | Decidido 2026-11-20; sistema por definir |
| **R7. Balance por variables base** | Para balancear se ajustan variables base, nunca valores nivel por nivel. | Decidido 2026-11-20 |
| **R8. Tiempo y espacio no escalan** | Velocidad de movimiento, cadencia de ataque, alcance y tamaño **no** se multiplican por el nivel. Solo escalan las cantidades (vida, daño, producción, almacenamiento). | Decidido 2026-11-20 |
| **R9. Contra** | Tercera estadística: un multiplicador según la categoría del objetivo. En el MVP multiplica **solo el daño**; el sistema debe permitir multiplicar otras estadísticas más adelante. Pocas categorías. Multiplicadores entre 1,5 y 3, con tope. | Decidido 2026-11-21 |
| **R10. Laboratorio** | Existirá un edificio, el Laboratorio, donde el jugador crea y personaliza sus unidades **en lo mecánico**, repartiendo puntos de un presupuesto, con mínimos por característica. | Decidido 2026-11-21; detalle en debate (§7) |
| **R11. Catálogo base** | Habrá un catálogo de unidades diseñadas por «nosotros» para que el jugador pueda empezar, atacar, defenderse y aprender; como mínimo una unidad por cada identidad mecánica. | Decidido 2026-11-21 |
| **R12. Dos identidades** | Se distingue la identidad mecánica de la identidad temática de cada unidad. | Adoptado por Carlos 2026-11-21 |
| **R13. Solo vida y daño** | Las unidades empiezan con dos únicas estadísticas de cantidad, vida y daño, que el jugador compra con puntos en el Laboratorio. Sin defensa, tipos de daño ni resistencias por ahora. Un tema puede renombrarlas (por ejemplo, «chakra» en un tema de ninjas). | Decidido 2026-11-21 |
| **R14. La compensación la elige el jugador** | Una mecánica no trae una consecuencia fija: el juego da las opciones y el jugador decide con qué compensa. | Decidido 2026-11-21 |
| **R15. Precios distintos** | No todas las características valen lo mismo. Vida y daño pueden intercambiarse punto por punto; velocidad de movimiento, velocidad de ataque y similares cuestan más. | Decidido 2026-11-21 |
| **R16. Presupuesto único** | La personalización usa un solo presupuesto de puntos, sin estadísticas negativas: al gastar puntos en una cosa ya no se tienen para otra, y esa es la compensación. | Decidido 2026-11-21 |
| **R17. Velocidad por paquetes** | La velocidad de movimiento se vende en tres paquetes con precio (lento, normal, rápido), no punto por punto. | Decidido 2026-11-21 |

**Dirección preferida por Carlos, con el modelo por cerrar:** un **sistema de mecánicas** (posible «cuarta estadística») en el que cada mecánica es una insignia que se asigna a una tropa, da una ventaja y trae una consecuencia. Una tropa tendría varias mecánicas posibles (distancia, movimiento, tamaño, costo de producción). Carlos dijo que esta idea le gusta mucho y reconoce que es más difícil de diseñar y de balancear.

## 4. El modelo completo en una página

**[Sugerencia]** Todo lo decidido cabe en una sola estructura: cuatro capas que actúan en tres momentos distintos.

| Capa (en el orden en que Carlos las planteó) | Qué define | Momento | Efecto |
|---|---|---|---|
| **1. Base** | Cuántos puntos van a vida y cuántos a daño | Diseño, en el Laboratorio | `base = puntos × valor del punto` |
| **2. Nivel** | Cuánto ha progresado ese diseño | Progreso, con recursos | Multiplica vida y daño |
| **3. Contra** | Ventaja contra una clase de objetivo | Combate | Multiplica el daño según el objetivo |
| **4. Insignias** | Tamaño, movimiento, alcance, especialidad | Diseño, en el Laboratorio | Fijan comportamientos y cuestan puntos |

```text
En el Laboratorio   vida_base = puntos_vida × V          daño_base = puntos_daño × D
                    (las insignias descuentan puntos y fijan tamaño, velocidad, alcance y ritmo)

Al subir de nivel   vida = vida_base × nivel              daño = daño_base × nivel
                    (velocidad, alcance y ritmo no cambian: R8)

En el combate       daño_real = daño × contra[especialidad del atacante → clase del objetivo]
                    (vale 1 cuando no hay ventaja: R9)
```

**[Observación]** Cada capa actúa en un solo momento: el jugador diseña, el progreso multiplica, el combate aplica la contra. Ninguna capa necesita conocer los detalles de las otras; por eso cualquiera se puede ajustar o apagar sin rehacer el resto. Es la intuición de Carlos del «multiplicar por uno», generalizada.

## 5. Base y nivel (R1, R2, R7, R8)

### 5.1 Invariancia a escala

- **[Observación]** Si todas las cantidades de combate de todas las unidades y defensas se multiplican por el nivel, un combate entre dos bandos del mismo nivel es **matemáticamente idéntico** a ese mismo combate en nivel 1. Por eso, **si el juego está balanceado en nivel 1, lo está en el nivel 1 000**. Es la mayor fortaleza del diseño y lo que hace posible R7.
- **[Observación]** Con R3 y R5, «20 niveles por debajo» tiene un significado real: una defensa de nivel 20 frente a tropas de nivel 40 tiene la mitad de vida y la mitad de daño.

### 5.2 Qué escala y qué no (R8)

| Escala con el nivel (`base × nivel`) | **No** escala con el nivel (constante) |
|---|---|
| Vida / puntos de estructura | Velocidad de movimiento |
| Daño | Cadencia de ataque |
| Capacidad de almacenamiento | Alcance |
| Producción de recursos por hora | Tamaño en el mapa, radio de área |
| Capacidad de campamento (opcional) | Tiempo de despliegue, duración del combate |

- **[Decisión de Carlos]** Aceptada el 2026-11-20. Motivo registrado: el mapa no crece con el nivel; si la velocidad se multiplicara, en niveles altos las tropas cruzarían el mapa en un instante.

### 5.3 Sensación de progreso

- **[Observación]** Con `base × nivel`, pasar de nivel 1 a 2 **duplica** el poder (+100 %); pasar de 100 a 101 lo aumenta solo un 1 %. El juego temprano es brusco y el tardío es plano.
- **[Sugerencia]** Mantener la fórmula lineal por simplicidad y vigilar este efecto al decidir costos y tiempos (§9). Válvula de ajuste si en pruebas el inicio se siente demasiado brusco: `base × (1 + g × (nivel − 1))` con `g` entre 0,25 y 0,5, que conserva la invariancia. No se recomienda adoptarla ahora.

### 5.4 Números grandes

- **[Observación]** Los valores son enteros exactos. Incluso en niveles absurdos (3 millones × 1 000 de base = 3 × 10⁹) caben en números de 64 bits. R4 no es un obstáculo numérico si desde el primer día se usa ese tipo de dato y se muestran cantidades abreviadas (1,2 K; 3,4 M; 5,6 B).

### 5.5 Qué significa «balancear por la base» cuando existe el Laboratorio

- **[Observación]** Con el Laboratorio, las «variables base» de R7 pasan a ser tres grupos: el **valor del punto** (cuánta vida o cuánto daño da cada punto), el **precio de cada insignia** y el **valor de cada escalón** (qué velocidad es «Rápido», qué alcance es «Medio»). Siguen siendo pocas variables y ninguna depende del nivel, así que R7 se conserva.

## 6. Contra (R9)

### 6.1 Qué es

- **[Observación]** Las estadísticas base ya pueden expresar «ligero frente a pesado», porque eso es una propiedad de una sola unidad. Lo que no pueden expresar es «esta unidad es especialmente buena contra aquella», porque eso es una propiedad de **un encuentro entre dos**. Por eso la contra no es una estadística de la unidad sino una tabla: atacante especializado → clase del objetivo → multiplicador.

### 6.2 Lo decidido

- **[Decisión de Carlos]** En el MVP la contra multiplica solo el daño. Pocas categorías. Multiplicadores entre 1,5 y 3, con un tope.
- **[Decisión de Carlos]** El sistema no debe cerrar la posibilidad de multiplicar otras estadísticas más adelante.

### 6.3 Forma general

- **[Sugerencia]** Definir la contra como una lista de **modificadores** con tres partes: *estadística afectada*, *multiplicador* y *condición*. En el MVP solo existe un tipo: «daño × M si el objetivo es de la clase C». Para todo lo demás el multiplicador vale 1.
- **[Observación]** El valor neutro de un multiplicador es **1**. Un 0 anularía la estadística. El 0 solo es neutro para bonificaciones que se suman, y este diseño usa multiplicaciones.

### 6.4 Límites

- **[Sugerencia]** Tope duro de ×3; valor habitual ×2.
- **[Sugerencia]** **Una sola especialidad por unidad.** Así nunca hay dos contras que se acumulen y el tope se cumple solo. Si en el futuro se permitieran varias, el producto de todas se recorta al tope.
- **[Observación]** Como el juego es invariante a escala, una contra no se diluye nunca: vale lo mismo en nivel 1 que en nivel 1 000. Con contras muy altas, el combate se decide al elegir el ejército y no al jugar.

### 6.5 Lo que cambia con unidades personalizadas

- **[Observación]** En un catálogo fijo, el diseñador reparte las contras a mano. Con unidades creadas por el jugador aparecen dos problemas: si la contra fuera gratis, todos la tomarían; y si la clase de una unidad dependiera de un umbral (por ejemplo, «es pesada si tiene más de X de vida»), los jugadores se quedarían un punto por debajo del umbral para esquivarla.
- **[Sugerencia]** La contra **se compra** como una insignia (casilla Especialidad, §7.5). La clase de cada unidad sale de una **elección explícita** (casilla Tamaño), nunca de un umbral. Los edificios tienen sus propias clases (por ejemplo, Edificio y Muro).

## 7. Laboratorio e insignias (R10, R11)

### 7.1 Lo que pidió Carlos

- **[Decisión de Carlos]** Un edificio, el Laboratorio, donde el jugador crea y personaliza unidades en lo mecánico, con asignación de puntos y mínimos por característica.
- **[Decisión de Carlos]** Un catálogo base diseñado por «nosotros», con al menos una unidad por identidad mecánica, para empezar y aprender.
- **[Decisión de Carlos]** Quiere gran variabilidad de combinaciones, incluidas las ideas extremas (su ejemplo: una unidad inmóvil que otra unidad jala).
- **[Decisión de Carlos — preferencia]** Le gusta mucho un sistema de mecánicas en forma de insignias con ventaja y consecuencia.
- Carlos planteó dos alternativas: (1) el jugador crea también la identidad mecánica; (2) la identidad mecánica la define Carlos y el jugador solo reparte puntos.

### 7.2 Las dos alternativas son etapas del mismo sistema

- **[Sugerencia]** No hace falta elegir. Si las unidades del catálogo se construyen **con las mismas reglas** que usará el jugador (mismo presupuesto, mismas insignias), las dos alternativas son dos profundidades de un mismo Laboratorio, que se desbloquean en orden:

| Etapa | Lo que puede hacer el jugador | Equivale a |
|---|---|---|
| **1. Catálogo** | Usar y subir de nivel los diseños base | El catálogo base (R11) |
| **2. Ajuste** | Mover el reparto de puntos de un diseño | La alternativa 2 de Carlos |
| **3. Insignias** | Cambiar insignias o crear un diseño desde cero | La alternativa 1 de Carlos |

- **[Observación]** Así el catálogo es también el tutorial: el jugador abre el diseño del «Tirador» y ve cómo está hecho antes de tocarlo. Y ninguna unidad es un caso especial: las del catálogo y las del jugador valen exactamente lo mismo.
- **[Sugerencia]** Desbloquear las etapas (y luego casillas e insignias) con los primeros niveles del ayuntamiento. Da novedad al inicio del juego sin tocar la fórmula de niveles.
- **[Observación]** Las etapas sirven además como orden de construcción cuando llegue el momento de programar: la etapa 1 ya es un juego completo, y lo construido para ella no se desecha en las siguientes.

### 7.3 Principio propuesto: los puntos compran cantidades; las insignias definen comportamientos

- **[Decisión de Carlos, R13]** Con **puntos** se compran las **cantidades**: vida y daño. Son justamente las estadísticas que se multiplican por el nivel (R8).
- **[Sugerencia]** Con **insignias** se elige el **cómo**: tamaño, movimiento, alcance y especialidad. Son justamente las propiedades de tiempo y espacio que no escalan con el nivel (R8). Vienen por **escalones** (por ejemplo, Lento / Normal / Rápido), no como una barra continua. **[Decisión de Carlos, R17]** Aceptado para la velocidad el 2026-11-21; para alcance y ritmo de ataque sigue siendo una propuesta (S1).
- **[Observación]** Es un cambio respecto a lo que Carlos describió (asignar puntos directamente a velocidad de movimiento y velocidad de ataque). No se pierde la personalización: esas propiedades se siguen pagando con puntos del mismo presupuesto, pero por escalones. Razones:
  1. **Sin casos extremos accidentales.** Una barra continua permite velocidad 0 o un alcance mayor que el de todas las defensas (una unidad que destruye sin que nada pueda responderle). Con escalones, esos extremos no existen salvo que se añadan a propósito.
  2. **Las ideas extremas se vuelven contenido.** El ejemplo de Carlos (unidad inmóvil que otra jala) sigue siendo posible, pero como una pareja de insignias nuevas («Inmóvil» y «Transporte») que se añaden deliberadamente, con precio y reglas, cuando el juego esté listo para ellas.
  3. **Menos variables que balancear.** El balance se reduce a una quincena de precios en lugar de un espacio continuo de cinco dimensiones.
  4. **Cada insignia puede tener una pieza visual** (§8.2).
- **[Sugerencia]** Los puntos de daño compran **daño por segundo**. La cadencia (cuántos golpes por segundo) la fija una insignia de ritmo y el daño por golpe se calcula solo. Comprar por separado «daño por golpe» y «velocidad de ataque» sería comprar dos veces la misma cosa.
- **[Decisión de Carlos, R13]** Quedan fuera por ahora la defensa (armadura), los tipos de daño (mágico, espiritual) y sus resistencias: al final todo se traduce en vida y daño.
- **[Observación]** En otros juegos, los tipos de daño y las resistencias sirven para que unas unidades sean buenas contra otras. Ese papel ya lo cumple la contra (R9); tener las dos cosas sería duplicar el sistema. Pueden volver más adelante como insignias (por ejemplo, «Blindaje»).

### 7.4 Cómo se pagan las insignias

- **[Decisión de Carlos, R14 y R15]** Una mecánica no trae una consecuencia fija: el juego da las opciones y el jugador decide con qué compensa. Y no todo vale lo mismo: velocidad y alcance cuestan más que vida y daño.
- **[Sugerencia]** La forma más simple de cumplirlo: las insignias **cuestan puntos del mismo presupuesto**. Compensar es, sencillamente, tener menos puntos para lo demás, y el jugador decide de dónde los quita. La «lista de opciones para compensar» que pidió Carlos no hay que escribirla aparte: es todo lo demás que el jugador podría haber comprado. Coincide con sus dos ejemplos:
  - «Que pegue de lejos pero que sea débil»: la insignia de alcance cuesta puntos y el jugador los quita de la vida.
  - «Que pegue de lejos y fuerte, pero que tarde más en pegar»: alcance más una insignia de golpe pesado.
- **[Observación]** Los precios deben expresarse como **porcentaje del presupuesto**, no como puntos fijos. Si el alcance costara 30 puntos fijos, a una unidad Grande (200 puntos) le saldría proporcionalmente mucho más barato que a una Pequeña (50 puntos).
- **[Observación]** Las insignias que **devuelven** puntos (por ejemplo, «Lento») son el punto débil clásico de los sistemas de compra por puntos: los jugadores eligen la desventaja que no les afecta. Por eso solo deben existir dentro de casillas obligatorias, donde siempre hay que elegir una opción, y con devoluciones pequeñas.
- **[Observación]** Este tipo de sistema ya existe y se conoce como **compra por puntos** (*point-buy*). Lo usan, entre otros, los juegos de rol de mesa para crear personajes. Tiene tres variantes conocidas:
  1. **Parejas fijas:** cada ventaja viene atada a una desventaja concreta. Fácil de entender y de balancear, pero quita la decisión al jugador. Fue la primera idea de Carlos y él mismo la descartó por ese motivo.
  2. **Ventajas y defectos:** el jugador toma defectos que le devuelven puntos. Da mucha libertad, pero los jugadores eligen el defecto que no les afecta y obtienen puntos gratis.
  3. **Presupuesto único:** todo tiene precio y los puntos no alcanzan para todo. Es la propuesta de este documento, con muy pocos defectos (solo «Lento»). **Elegida por Carlos el 2026-11-21 (R16).**
- **[Observación]** Para ser coherentes con R16, los paquetes pueden expresarse sin devoluciones: en lugar de «Lento devuelve 10, Normal 0, Rápido cuesta 20», decir «Lento 0, Normal 10, Rápido 30». Es el mismo sistema con el punto de partida desplazado, y así ninguna opción es una estadística negativa.
- **[Observación]** El costo de dejar la compensación libre: es más difícil de balancear que las parejas fijas, porque los jugadores buscan la compensación más barata. Se corrige ajustando precios (§7.9).

### 7.5 Borrador de casillas e insignias (para debatir)

Presupuesto de ejemplo: 100 puntos para el tamaño Mediano.

| Casilla | Insignia | Precio de ejemplo | Efecto |
|---|---|---|---|
| **Tamaño** (obligatoria) | Pequeño | Presupuesto de 50 | Ocupa 1 espacio de ejército. Clase Pequeño. |
| | Mediano | Presupuesto de 100 | Ocupa 2 espacios. Clase Mediano. |
| | Grande | Presupuesto de 200 | Ocupa 4 espacios. Clase Grande. |
| **Movimiento** (obligatoria) | Lento | Devuelve 10 % | Velocidad baja. |
| | Normal | 0 | Velocidad media. |
| | Rápido | Cuesta 20 % | Velocidad alta. |
| **Alcance** (obligatoria) | Cuerpo a cuerpo | 0 | Ataca pegado al objetivo. |
| | Alcance medio | Cuesta 30 % | Ataca a distancia media. |
| | Alcance largo | Cuesta 40 % | Ataca a distancia larga, siempre menor que la de las defensas de mayor alcance. |
| **Especialidad** (opcional, máximo una) | Ninguna | 0 | Más puntos libres para vida y daño. |
| | Perforante | Cuesta 20 % | Daño ×2 contra la clase Grande. |
| | Demoledor | Cuesta 20 % | Daño ×2 contra edificios. |
| | Área | Cuesta 30 % | Daña a todos los objetivos de una zona pequeña. Contra natural de los Pequeños. |
| | Golpe pesado | 0 | El mismo daño por segundo en golpes más lentos y más fuertes. Bueno contra objetivos grandes, malo contra muchos pequeños. |

- **[Observación]** La «mecánica de tamaño» y la «mecánica de costo de producción» que imaginó Carlos son **la misma perilla**: en un sistema de presupuesto, el costo de producir una unidad es consecuencia de cuántos puntos vale. Por eso el borrador las une en la casilla Tamaño, que fija a la vez presupuesto, espacio en el ejército, costo de producción y clase.
- **[Sugerencia]** Los puntos que quedan después de las insignias se reparten entre **vida y daño** con una sola barra, con un mínimo en cada una (por ejemplo, el 10 % de los puntos libres).
- **[Pregunta]** ¿Qué casillas o insignias sobran, cuáles faltan y cuáles deberían llamarse de otra forma? Es el listado de identidades mecánicas que Carlos anticipó.

### 7.6 Ejemplos con el borrador

| Diseño | Insignias | Puntos libres | Vida / daño | Lectura |
|---|---|---|---|---|
| **Asalto** (catálogo) | Mediano, Normal, Cuerpo a cuerpo | 100 | 50 / 50 | Unidad equilibrada de referencia. |
| **Tirador** (catálogo) | Mediano, Normal, Alcance medio | 100 − 30 = 70 | 30 / 40 | Pega de lejos; es más frágil porque el alcance costó puntos. |
| **Francotirador** (jugador) | Mediano, Lento, Alcance largo, Golpe pesado | 100 − 40 + 10 = 70 | 15 / 55 | Pega de muy lejos y muy fuerte, pero tarda en pegar, camina lento y es frágil. |
| **Coloso** (catálogo) | Grande, Lento, Cuerpo a cuerpo | 200 + 20 = 220 | 160 / 60 | Absorbe daño para que otras unidades ataquen. |
| **Enjambre** (catálogo) | Pequeño, Rápido, Cuerpo a cuerpo | 50 − 10 = 40 | 20 / 20 | Barato y numeroso; sufre contra daño de área. |

### 7.7 Mesas de diseño, nivel y rediseño

- **[Sugerencia]** Cada diseño vive en una **mesa del Laboratorio**, y **el nivel pertenece a la mesa, no al diseño**. Cambiar el diseño de una mesa no reinicia su nivel.
- **[Observación]** Con niveles sin límite (R4), si rediseñar reiniciara el nivel, nadie en nivel 500 volvería a experimentar, y se perdería la variabilidad que Carlos busca.
- **[Observación]** Si rediseñar fuera instantáneo y gratuito, el atacante miraría una aldea, rediseñaría sus unidades a la medida y atacaría. El defensor no tendría respuesta posible.
- **[Sugerencia]** Que el rediseño tarde un tiempo fijo (no recursos, para que no dependa del nivel) y que una mesa no pueda rediseñarse mientras existan tropas entrenadas de ese diseño.
- **[Pregunta]** ¿Cuántas mesas tendrá un jugador al empezar y cómo se desbloquean más?
- **[Pregunta]** ¿Qué da el nivel del propio Laboratorio, además de vida como edificio? Una opción coherente con R3 y R4: que el nivel del Laboratorio sea el nivel máximo al que pueden subir las mesas, de modo que su nivel siempre signifique algo.

### 7.8 El catálogo base

- **[Sugerencia]** Criterio para decidir cuántas unidades tiene el catálogo: **cada insignia debe aparecer al menos una vez** en algún diseño base, para que el jugador las vea todas en acción antes de usarlas. Es la versión precisa del «una unidad por identidad mecánica» de Carlos.
- **[Observación]** Con el borrador de §7.5 eso da unos siete diseños: Asalto, Tirador, Coloso, Enjambre, Demoledor (especialidad Demoledor), Artillero (Lento, Alcance medio, Área) y Cazador (Alcance largo, Perforante). Los nombres son provisionales y sin temática; cada tema visual los rebautiza.

### 7.9 Balance por precios

- **[Sugerencia]** Tratar el precio de cada insignia como la perilla principal de balance. Regla práctica: si casi todos los jugadores usan una insignia, está barata y se le sube el precio; si nadie la usa, se le baja.
- **[Observación]** Como el juego es invariante a escala, los datos de uso de todos los niveles sirven juntos: un solo desarrollador puede balancear con una sola tabla.
- **[Sugerencia]** Cuando cambie un precio, dar un rediseño gratuito e inmediato de los diseños afectados. Un diseño que quede por encima del presupuesto no puede entrenarse hasta ajustarlo.
- **[Observación]** El balance de un juego con unidades personalizadas es trabajo continuo, no una tarea que se termina. Un diseño dominante se copia en pocos días.

### 7.10 Herramientas del Laboratorio

- **[Sugerencia] Campo de pruebas:** permitir probar un diseño contra la propia aldea o contra blancos de práctica sin gastar recursos. Sin esto, experimentar sale caro y los jugadores se limitan a copiar.
- **[Sugerencia] Compartir diseños:** un diseño es solo una lista de números e insignias, así que se puede compartir como un código. Esto le da a la comunidad un papel creativo **sin riesgo legal**, a diferencia de los diseños visuales hechos por usuarios que preocupaban a Carlos.
- **[Sugerencia] Nombres:** generar el nombre a partir de las insignias o elegirlo de una lista. Un nombre de texto libre visible para otros jugadores obligaría a moderar contenido.

### 7.11 Lo que conviene dejar fuera del primer diseño

- Armadura como estadística separada.
- Unidades voladoras (obligan a dividir las defensas en antiaéreas y terrestres).
- Inmóvil más Transporte (el ejemplo de Carlos).
- Curación y unidades de apoyo.
- Defensas personalizables por el jugador (ver S9 en §13).
- Barras continuas para velocidad y alcance.

Todas pueden entrar más adelante como insignias nuevas sin cambiar el modelo.

### 7.12 Riesgos

1. **[Observación] La variedad no sale sola.** En un duelo directo gana quien tenga mayor producto vida × daño, y con precios lineales el mejor duelista es el reparto mitad y mitad. Un presupuesto hace que las unidades sean justas en el papel, pero solo hay variedad real si **situaciones distintas premian diseños distintos**: defensas de un solo objetivo frente a defensas de área, muros, tiempo límite, contras, y el reparto de papeles entre unidades que absorben daño y unidades que lo hacen. **[Sugerencia]** Diseñar las defensas junto con las insignias: cada tipo de defensa es una pregunta y cada diseño de unidad es una respuesta.
2. **[Observación] Diseños dominantes y copia.** Ver §7.9.
3. **[Observación] Rediseño a la medida del objetivo.** Ver §7.7.
4. **[Observación] Ventaja de la concentración.** Con las mismas estadísticas totales, una unidad grande vence a dos unidades con la mitad de vida y la mitad de daño cada una: termina el combate con una cuarta parte de su vida, porque conserva todo su daño hasta morir. Los tamaños grandes necesitan un pequeño recargo o contras claras (Perforante, y el desperdicio de los golpes fuertes contra enjambres).
5. **[Observación] Complejidad para el jugador nuevo.** La resuelven las etapas de §7.2.
6. **[Observación] Alcance del proyecto.** El juego tiene ahora dos innovaciones grandes: niveles sin límite y Laboratorio. Diseñarlas en papel es barato; construirlas a la vez es el mayor riesgo del proyecto para una sola persona. Las etapas de §7.2 lo reducen.

## 8. Apariencia y temática

### 8.1 Las dos alternativas iniciales de Carlos

| | **A. Un solo estilo; cambia el nivel** | **B. Diseños de la comunidad** |
|---|---|---|
| Carga de arte inicial | Un diseño por elemento (mínimo indispensable) | Igual: hay que lanzar con algo propio |
| Carga de arte continua | Cero obligatoria; opcional vender temáticas | Baja en producción, **alta en moderación y gestión** |
| Riesgo legal | Bajo (todo es propio o licenciado) | Alto: derechos de autor ajenos, contenido oculto inapropiado, cesión de derechos, revisión manual |
| Depende de tener comunidad | No | Sí; con cero comunidad produce cero diseños |
| Coherencia con R4 | Total: la apariencia no depende del nivel | Parcial: reintroduce la pregunta de cada cuántos niveles cambia la temática |
| Monetización | Natural: temáticas cosméticas que no afectan el balance | Posible, pero complica la propiedad del contenido |

- **[Sugerencia]** Adoptar **A como base** y dejar **B como posibilidad futura**. Si algún día se hace B, que sea como concurso de conceptos: la comunidad propone bocetos y el recurso final lo produce alguien de confianza, con cesión de derechos en las bases.
- **[Observación]** El deseo de participación de la comunidad queda cubierto, sin riesgo legal, por los diseños mecánicos compartidos (§7.10).

### 8.2 El problema que detectó Carlos: cómo se ve una unidad personalizada

- Carlos señaló que, si una unidad es en apariencia un cubo y recibe la mecánica de disparar a distancia, cada tema tendría que incluir un arma de distancia para ella (un arco en un tema prehistórico, un láser en uno futurista). El 2026-11-21 aclaró que «cubo» era su forma de nombrar una unidad sin apariencia propia: si el jugador diseña sus unidades, hay que darles una identidad temática acorde con su identidad mecánica, igual que una arquera hace pensar en un arco.
- **[Observación]** Esa observación describe la solución: **arte modular**. Cada insignia tiene **una pieza visual**, y la unidad se dibuja componiendo las piezas de sus insignias. Un tema visual es un **kit de piezas**, no una colección de unidades.
- **[Observación]** La cuenta con el borrador de §7.5: 3 cuerpos (Tamaño) + 3 piezas de Movimiento + 3 armas (Alcance) + 4 marcas de Especialidad = **13 piezas por tema**, que componen 3 × 3 × 3 × 5 = **135 unidades distintas**. El arte crece sumando; la variedad crece multiplicando.
- **[Observación]** No es solo un ahorro. En un juego donde cada jugador inventa sus unidades, el rival **solo puede entender una unidad desconocida por su aspecto**. Si cada insignia tiene siempre su pieza, cualquier diseño se lee de un vistazo: arma larga, es de alcance; cuerpo grande, es clase Grande.
- **[Sugerencia]** Regla para los temas: en todos, la pieza de una misma insignia debe ser reconocible como la misma mecánica. El reparto de puntos entre vida y daño no necesita pieza visual.
- **[Pregunta abierta — Carlos indeciso]** A Carlos le atrae que sean los usuarios quienes diseñen y creen sus propios modelos, pero teme que eso permita imágenes o modelos inapropiados o ilegales. El 2026-11-21 pidió la opinión del agente; ver §8.5. *(Corrección: una versión anterior de este documento registró esto por error como decisión tomada.)*
- **[Observación]** «El cubo» es una analogía de Carlos para una entidad que todavía no tiene figura, pensada para diseñar desde cero. No quiere que las unidades se vean como cubos. Un cubo que pega de lejos tiene la misma identidad mecánica que un arquero y ninguna identidad temática. Su pregunta es cómo se decide la identidad temática de una unidad cuando el jugador personaliza su mecánica. Respuesta propuesta: nadie la decide unidad por unidad; **la apariencia se arma sola a partir de las insignias**, con piezas dibujadas por «nosotros».
- **[Sugerencia — opcional, solo como prototipo] Tema neutro.** Carlos aclaró que no es lo que buscaba con su analogía. Aun así, la primera apariencia de una versión de prueba puede ser literalmente el cubo: figuras geométricas simples con una marca visible por cada insignia (por ejemplo, una flecha para «pegar de lejos»). No tiene temática y aun así deja leer la mecánica. Los temas posteriores sustituyen la figura y las marcas por dibujos (arco, láser).
- **[Observación]** Este sistema ya existe: se conoce como apariencia modular o «muñeca de papel» (*paper doll*), por las muñecas a las que se les cambia la ropa pieza por pieza. Trampas conocidas: (1) todas las piezas deben encajar entre sí en cualquier combinación, lo que obliga a dibujarlas con un mismo patrón; (2) en la pantalla de un celular las piezas pequeñas no se distinguen, así que cada insignia debe notarse por silueta o color y no por detalle; (3) cada insignia nueva cuesta una pieza por cada tema existente, lo que aconseja tener pocas insignias y pocos temas.
- **[Observación]** No hace falta resolver los dibujos ahora. Lo que conviene fijar desde el diseño es la regla: toda insignia que se invente debe poder mostrarse con una pieza.

### 8.3 Otras alternativas de apariencia

- **[Sugerencia — C. Variación barata por tramos]** Cambios de paleta o pequeños añadidos cada cierto tramo de niveles (un color de estandarte distinto cada 10 niveles, por ejemplo). Da sensación visual de progreso a una fracción del costo de una temática.
- **[Sugerencia — D. Estilo deliberadamente simple]** Formas planas, íconos y siluetas que un solo desarrollador pueda producir y mantener. El «cubo con un arma» encaja aquí y abarata cada kit.
- **[Sugerencia — E. Paquetes de recursos con licencia permisiva]** Para una primera versión jugable, y sustituirlos después.
- **[Sugerencia — F. El nivel como elemento visual principal]** Mostrar el nivel grande y claro sobre cada edificio y tropa. Con R5, el nivel es la información importante.

### 8.4 Una ficción que haría natural el Laboratorio

- **[Sugerencia — opcional]** Si las unidades son **construcciones ensambladas** (autómatas, gólems, máquinas), que se vean hechas de piezas es natural en cualquier época: piedra y madera en un tema antiguo, hierro en uno medieval, energía en uno futurista. El jugador sería un inventor y el Laboratorio su taller. Es solo una idea para que la mecánica, el arte modular y la temática apunten en la misma dirección.

### 8.5 ¿Quién crea la apariencia de una unidad?

- **[Pregunta de Carlos, 2026-11-21]** ¿Es correcto no permitir que los usuarios diseñen y creen sus propios modelos?
- **[Observación]** Lo mecánico ya está decidido y no depende de esta pregunta: el jugador personaliza sus unidades en el Laboratorio (R10, R13, R16) a partir de un catálogo base (R11). Lo único abierto es quién crea la **apariencia**. Hay cuatro niveles posibles:

| Nivel | Lo que hace el jugador | Riesgo | Trabajo para un solo desarrollador |
|---|---|---|---|
| **1** | Nada: usa la apariencia que viene con la unidad | Ninguno | Bajo |
| **2** | Arma su unidad eligiendo entre piezas y colores hechos por «nosotros» | Casi ninguno | Medio: dibujar las piezas |
| **3** | Construye figuras libres con un editor dentro del juego | Alto | Muy alto: el editor es un proyecto grande por sí solo |
| **4** | Sube sus propias imágenes o modelos | Muy alto | Muy alto, más moderación permanente |

- **[Sugerencia]** Adoptar el **nivel 2**. El jugador siente que la unidad es suya y no puede crear nada indebido, porque todas las piezas son propias del juego. Es un sistema conocido: el creador de personajes por piezas. Se combina con §8.2 así: la pieza de cada insignia es **obligatoria**, porque muestra la mecánica; el resto (colores, estilo del cuerpo, adornos) es **elección libre** del jugador.
- **[Observación]** Razones para no adoptar los niveles 3 y 4, al menos al inicio:
  1. En un juego donde las aldeas se atacan, las unidades de un jugador las ven otros jugadores. Eso es contenido creado por usuarios y obliga a moderar, recibir reportes y bloquear. Las tiendas de aplicaciones lo exigen como condición para publicar (verificar las políticas vigentes cuando llegue el momento).
  2. Trampa conocida de los editores libres: una parte de los jugadores construye figuras obscenas o copia personajes con derechos de autor.
  3. Se pierde la lectura del combate: una unidad puede disfrazarse de lo que no es, y el rival no sabe a qué se enfrenta.
  4. Hacer que una figura libre camine y ataque exige un editor y un sistema de animación que son un proyecto grande por sí solos.
- **[Observación]** La idea de Carlos no es mala; es cara y riesgosa para empezar. Puede revisarse cuando existan comunidad y recursos para moderar.

## 9. Economía (pendiente de debatir)

- **[Observación]** Está definido cómo crece el **poder** con el nivel, pero no cómo crecen el **costo** y el **tiempo** de cada mejora, ni la **producción** de recursos. Con R4, estas tres curvas marcan el ritmo del juego:
  - Si costo y producción crecen ambos linealmente, cada nivel cuesta aproximadamente el mismo tiempo real que el anterior: una cinta sin fin de ritmo constante.
  - Si el costo crece algo más rápido que la producción, cada nivel toma un poco más que el anterior, sin imponer un límite.
- **[Sugerencia]** Tres curvas derivadas de una base y el nivel, para respetar R7:
  1. `costo(nivel) = costo_base × nivel^k`, con `k` entre 1,1 y 1,5;
  2. `tiempo(nivel)` con la misma forma;
  3. `producción(nivel) = producción_base × nivel`.
- **[Sugerencia]** El costo de producir una unidad es proporcional a su presupuesto y a su nivel. No hace falta una insignia de costo.
- **[Pregunta]** ¿Cuántos tipos de recursos habrá? ¿Habrá un recurso «premium»?

## 10. Ayuntamiento, niveles sin límite y novedad (R3, R4, R5)

- **[Observación]** R3 elimina una trampa clásica del género: mantener el ayuntamiento bajo y maximizar lo demás para abusar de rivales débiles. El único desbalance posible es el inverso (ayuntamiento alto, resto bajo), y ese se castiga solo, como Carlos quiere.
- **[Observación]** R3 y R5 dan gratis una métrica de salud de aldea: a cuántos niveles del ayuntamiento está cada cosa.
- **[Observación]** Con R4, los veteranos se alejan indefinidamente de los nuevos. No es un problema de justicia si se empareja por poder (§11); sí es un problema de **novedad**: si todos los niveles son «lo mismo pero más grande», el jugador puede perder motivación.
- **[Observación]** Las insignias resuelven buena parte de ese problema. Desbloquear casillas e insignias en los primeros niveles, y añadir insignias nuevas con el tiempo, es contenido barato de producir: una regla, un precio y una pieza visual por tema.
- **[Sugerencia]** Después de los desbloqueos, temporadas, ligas o eventos como fuente de novedad.
- **[Sugerencia]** Que la mejora del ayuntamiento sea la más costosa y lenta del juego. No se propone obligar a tener el resto al máximo antes de subirlo.

## 11. Equivalencia y emparejamiento (R6)

- **[Observación]** El nivel del ayuntamiento no sirve como criterio de emparejamiento, porque R3 permite que dos aldeas con el mismo ayuntamiento tengan poder muy distinto.
- **[Sugerencia]** Usar el presupuesto como unidad de cuenta: **poder de una unidad = su presupuesto × su nivel**. El poder ofensivo de un ejército es la suma de sus unidades; el poder defensivo de una aldea, la suma de sus defensas. Se empareja al atacante con defensores cuyo poder defensivo esté dentro de una banda de su poder ofensivo. Esta medida sustituye a la que se propuso en la primera versión (vida × daño) porque no premia ni castiga ningún reparto de puntos: todos los diseños del mismo tamaño valen lo mismo.
- **[Sugerencia]** Mostrar a cada jugador su poder defensivo frente a su poder ofensivo. Es la forma directa de cumplir R5.
- **[Pregunta]** ¿Ataques **asíncronos** (se ataca una copia de la aldea mientras el dueño no está) o en tiempo real? La opción asíncrona es la estándar del género y la más viable para un solo desarrollador.
- **[Pregunta]** ¿Habrá modo contra la máquina, para jugar sin depender de que exista comunidad?

## 12. Coherencia del conjunto

| Regla | ¿Encaja el Laboratorio? | Por qué |
|---|---|---|
| R2, R8 | Sí | Los puntos compran lo que escala con el nivel; las insignias fijan lo que no escala. |
| R3, R5 | Sí | El nivel de cada mesa está acotado por el ayuntamiento; el atraso se sigue leyendo en niveles. |
| R4 | Sí | El presupuesto es el mismo en todos los niveles; las insignias nuevas son el contenido de un juego sin fin. |
| R6 | Sí | El presupuesto da la medida de poder para emparejar. |
| R7 | Sí | Balancear es ajustar precios y valores del punto. |
| R9 | Con condiciones | La contra debe comprarse y la clase debe salir de una casilla explícita (§6.5). |
| R11 | Sí | El catálogo son diseños hechos con las mismas reglas. |
| Apariencia A | Con condiciones | Requiere arte modular por insignia (§8.2). |

**Tensiones reales detectadas hasta ahora:** (1) velocidades y alcances no deben escalar con el nivel, ya resuelta con R8; (2) con unidades personalizadas, la variedad depende de que las defensas premien diseños distintos (§7.12), pendiente de debatir.

## 13. Sugerencias pendientes de decisión

| ID | Propuesta | Sección |
|---|---|---|
| **S1** | El alcance y el ritmo de ataque también se venden por paquetes con precio, igual que la velocidad (ya decidido para la velocidad: R17). | §7.3 |
| **S2** | Los precios de las insignias se expresan en porcentaje del presupuesto. (El presupuesto único ya está decidido: R16.) | §7.4 |
| **S3** | Cuatro casillas (Tamaño, Movimiento, Alcance, Especialidad); una insignia por casilla; máximo una especialidad; la clase sale del Tamaño. | §6.5, §7.5 |
| **S4** | Tres etapas de desbloqueo: catálogo, ajuste de puntos, insignias. | §7.2 |
| **S5** | El nivel pertenece a la mesa de diseño; rediseñar no lo reinicia y toma tiempo. | §7.7 |
| **S6** | Apariencia por piezas: el jugador arma la apariencia de su unidad eligiendo entre piezas y colores hechos por «nosotros», pero no dibuja ni sube nada. La pieza de cada insignia es obligatoria porque muestra su mecánica; un tema es un kit de piezas. | §8.2, §8.5 |
| **S7** | Balance por precios guiado por el uso; rediseño gratuito tras cada cambio. | §7.9 |
| **S8** | Poder para emparejar = presupuesto × nivel. | §11 |
| **S9** | Las defensas las diseñamos «nosotros» con las mismas reglas de presupuesto; la personalización del defensor es la distribución de su aldea. | §7.11 |
| **S10** | Las insignias se ganan jugando y nunca se venden; solo se vende apariencia. | §8, §10 |
| **S11** | Curvas de costo, tiempo y producción derivadas de base y nivel. | §9 |
| **S12** | Campo de pruebas y diseños compartibles por código. | §7.10 |
| **S13** | Apariencia A como base; B como futuro condicionado; variantes C a F. | §8 |
| **S14** | Modo contra la máquina. | §11 |
| **S15** | Números de 64 bits y formato abreviado desde el diseño de datos. | §5.4 |

## 14. Preguntas abiertas para Carlos

1. ¿Nombre provisional del juego?
2. ¿Qué casillas e insignias sobran, faltan o deben renombrarse? (§7.5)
3. ¿Cuántas mesas de diseño al empezar y cómo se desbloquean? (§7.7)
4. ¿Qué da el nivel del propio Laboratorio? (§7.7)
5. ¿Las defensas también se personalizan algún día, o solo las unidades?
6. ¿Cuántos recursos y cuáles? ¿Habrá recurso premium?
7. ¿Ataques asíncronos o en tiempo real?
8. ¿Habrá modo contra la máquina o campaña?
9. ¿Modelo de monetización previsto?
10. ¿Clanes, alianzas o cooperación?
11. ¿Qué cosas del género quiere evitar explícitamente, además de copiar?
12. (Resuelta el 2026-11-21) Carlos confirmó que su duda era cómo dar a una unidad personalizada una apariencia acorde con su identidad mecánica; ver §8.2.

## 15. Próximos pasos propuestos (sin código ni gráficos)

1. Avanzar **una pregunta a la vez**, en este orden: S6 (apariencia modular), S4 (etapas de desbloqueo), S5 (nivel por mesa de diseño), S1 (paquetes también para alcance y ritmo).
2. Debatir el listado de insignias casilla por casilla (S3).
3. Debatir las defensas como «preguntas» que las unidades responden (§7.12).
4. Debatir la economía (§9).
5. Redactar la hoja de reglas de una página.
6. Ejercicio numérico en papel u hoja de cálculo: tres diseños y tres defensas, en nivel 1 y en nivel 10.
7. Solo después: motor, plataforma y estilo visual.

## 16. Registro del debate

- **2026-11-20 — R8 [Decisión de Carlos]:** las magnitudes de tiempo y distancia no escalan con el nivel.
- **2026-11-20 — Forma de trabajo [Decisión de Carlos]:** solo debate y documentación del juego; exportación futura a un repositorio propio.
- **2026-11-21 — R9 [Decisión de Carlos]:** contra como multiplicador solo de daño en el MVP, generalizable, con pocas categorías y multiplicadores entre 1,5 y 3.
- **2026-11-21 — R10 y R11 [Decisión de Carlos]:** Laboratorio para personalizar unidades en lo mecánico, y catálogo base con al menos una unidad por identidad mecánica.
- **2026-11-21 — R12:** Carlos adopta la distinción entre identidad mecánica e identidad temática.
- **2026-11-21 — Preferencia de Carlos:** sistema de mecánicas en forma de insignias. El agente propuso el modelo de §7 (S1 a S5), pendiente de su decisión.
- **2026-11-21 — R13, R14 y R15 [Decisión de Carlos]:** solo vida y daño al inicio, comprados con puntos; la compensación de cada mecánica la elige el jugador; características distintas tienen precios distintos.
- **2026-11-21 — Forma de trabajo [Decisión de Carlos]:** avanzar una pregunta a la vez. El agente debe evaluar, corregir y complementar con mecánicas que ya existan, no darle la razón.
- **2026-11-21 — Vocabulario:** el hueco de la unidad donde va una insignia se llama «casilla», que es la palabra de Carlos; el espacio del Laboratorio que guarda un diseño se llama «mesa de diseño».
- **2026-11-21 — R16 y R17 [Decisión de Carlos]:** presupuesto único sin estadísticas negativas (la versión 3 de la compra por puntos); la velocidad se vende en tres paquetes con precio.
- **2026-11-21 — Apariencia:** el agente propuso la apariencia modular (S6). *(Corregido: aquí se registró por error, como decisión de Carlos, que el usuario no diseña la apariencia.)*
- **2026-11-21 — Aclaración de Carlos:** el «cubo» era una analogía de una entidad sin figura. Su idea de fondo era que el usuario le diera la forma, y está indeciso. El agente recomendó que el jugador arme la apariencia con piezas y colores hechos por «nosotros», sin dibujar ni subir contenido (§8.5), pendiente de su decisión.

## 17. Historial del documento

- 2026-11-20 — Primera versión, a partir del primer dictado de Carlos.
- 2026-11-20 — Se añadió el registro del debate con la aceptación de R8.
- 2026-11-21 — Versión 2: se reorganizó el documento alrededor del modelo de cuatro capas; se incorporaron R9 a R12, el Laboratorio, el sistema de insignias y el arte modular; la medida de poder para emparejar pasó de vida × daño a presupuesto × nivel.
- 2026-11-21 — Se incorporaron R13 a R15 y la referencia a los sistemas de compra por puntos, y se ajustó el vocabulario a las palabras de Carlos.
- 2026-11-21 — Se incorporaron R16 y R17, el tema neutro y la referencia a los sistemas de apariencia modular.
- 2026-11-21 — Se corrigió el registro sobre la apariencia (no era una decisión de Carlos) y se añadió §8.5 con los cuatro niveles de creación de apariencia.
