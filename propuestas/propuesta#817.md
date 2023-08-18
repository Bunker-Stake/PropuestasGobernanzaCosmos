# Propuesta de Gobernanza 817:

- Ver en [Mintscan](https://www.mintscan.io/cosmos/proposals/817).
- Ver en [Ping.pub](https://ping.pub/cosmos/gov/817).
- Ver en [Bigdipper](https://bigdipper.live/cosmos/proposals/817).

## Título: Propuesta de comunicación, aprobar el proceso de delegación de Stride para el consejo asesor del Hub de Cosmos.

Durante las últimas 3 semanas, Stride ha estado aceptando solicitudes para su programa de delegación, el proceso por el cual la gobernanza de Stride selecciona los validadores a los que delega el ATOM líquido a través del protocolo de Stride.

Como parte de este proceso, Stride solicitó públicamente candidaturas de miembros de la comunidad del Hub de Cosmos para formar parte del consejo asesor, un órgano de 5 miembros que seleccionará a los validadores de la cadena del Hub de Cosmos de acuerdo con criterios objetivos preseleccionados. Como uno de los muchos controles y mecanismos de equilibrio en el proceso de selección de validadores de Stride, la comunidad de Stride presenta esta propuesta de comunicación para pedir a la comunidad del Hub de Cosmos que ratifique a los candidatos seleccionados para el consejo asesor.

**Contexto del proceso de delegación**

El protocolo Stride está diseñado de tal forma que los delegadores de STRD votan para determinar qué validadores de la cadena anfitriona reciben delegaciones. En cualquier momento, cualquiera es libre de realizar una votación de gobierno en la cadena para añadir o eliminar validadores de un conjunto de validadores. Pero siempre son los delegadores de STRD los que tienen la última autoridad para aprobar o denegar cualquier cambio.

Los delegadores de STRD necesitan un marco sistemático, organizado y justo para seleccionar el conjunto de validadores de la cadena anfitriona.

Este marco se desarrolló e implementó a finales de 2022. Denominado _Stride Host-chain Validator Selection Process_, se utilizó para seleccionar un conjunto de treinta y seis validadores del Hub de Cosmos para recibir delegaciones del protocolo Stride. Los delegadores de STRD respondieron favorablemente al proceso y votaron para aprobar el nuevo conjunto de validadores. Desde que se utilizó el proceso a finales de 2022, se han realizado varias pequeñas optimizaciones, para hacerlo más organizado y eficiente.

Se ha pensado mucho en este proceso para que sea lo más justo y responsable posible, tanto desde el punto de vista del protocolo Stride como de las cadenas anfitrionas.

En los próximos meses, el proceso de selección de validadores de la cadena Stride se utilizará para seleccionar nuevos conjuntos de validadores para el Hub de Cosmos. Este es el aspecto que tendrá el proceso:

### Paso 1: Aplicaciones

Para poder optar a una delegación, los validadores deben cumplir estos cuatro requisitos mínimos:

- Un tiempo de actividad igual o superior al 99% en los últimos meses.
- Una comisión igual o inferior al 10%.
- Votó como mínimo siete de las diez últimas propuestas de gobernanza.
- Lleva al menos tres meses en el conjunto activo de validadores.

Si un validador cumple los requisitos, debe enviar una solicitud para que se le tenga en cuenta en la delegación del protocolo Stride. En el formulario de solicitud, los validadores deben responder a dos preguntas clave. El consejo asesor utilizará sus respuestas para evaluarlos. Las dos preguntas clave son:

- `¿Cómo ha contribuido técnicamente a la blockchain en los últimos seis meses?`
- `¿Cómo ha contribuido socialmente a la blockchain en los últimos seis meses?`

Las personas que deseen formar parte del consejo asesor también deben rellenar una solicitud. El consejo asesor es un grupo de cinco personas que evalúan a los solicitantes de validadores. Cualquiera puede presentar una solicitud para formar parte del consejo, pero sólo se elegirá a personas que conozcan bien la cadena de bloques, sean conocidas y respetadas por la comunidad correspondiente. Stride Labs tiene la función ejecutiva de proponer un consejo asesor de cinco miembros.

### Paso 2: Consejo asesor aprobado por la cadena de acogida

Como control del poder de Stride Labs, se presenta entonces una propuesta de comunicación _onchain_ en la cadena correspondiente, preguntando a los delegadores si aprueban el consejo asesor elegido. Este es el objetivo de la propuesta actual.

Si la gobernanza aprueba el consejo, entonces se procede a evaluar a los solicitantes. Si la gobernanza lo desaprueba, Stride Labs debe cambiar los miembros del consejo, y los nuevos miembros del consejo deben ser presentados en una nueva votación de señalización.

### Paso 3: Evaluación

Una vez recibidas las solicitudes y aprobado el consejo asesor por la cadena anfitriona correspondiente, los miembros del consejo evalúan de forma independiente a los solicitantes, otorgando a cada validador una puntuación sobre diez.

A continuación, se calcula la media de las puntuaciones de los cinco miembros del consejo, dando a cada validador una puntuación final sobre diez. Si un miembro del consejo tiene un conflicto de intereses con respecto a un validador determinado, no lo evalúa.

### Paso 4: Clasificación de cuartiles y ponderación

Una vez que cada validador tiene una puntuación final, los validadores se separan en cuatro cuartiles, en función de sus delegaciones existentes. Por ejemplo, el veinticinco por ciento de los mejores validadores están en el primer cuartil, los siguientes veinticinco percentiles están en el segundo cuartil, y así sucesivamente.

En cada uno de los cuatro cuartiles, los validadores se clasifican en función de su puntuación final. Se eligen los ocho mejores validadores de cada cuartil, lo que da como resultado un conjunto de treinta y seis validadores de todo el conjunto activo.

Por último, se pondera cada validador para determinar la parte de la delegación total que recibirá.

Vea los detalles completos de la evaluación aquí: [https://docs.google.com/document/d/19NfSHfUuXiwQ2e2NOx2PhK17Xpevp9r9SwxXXoUAVQM/edit](https://docs.google.com/document/d/19NfSHfUuXiwQ2e2NOx2PhK17Xpevp9r9SwxXXoUAVQM/edit)

### Paso 5: Propuesta enviada a los delegadores de STRD

El conjunto de validadores de cadena resultante se presenta a los delegadores de STRD, que tienen total autoridad para aprobar o denegar el conjunto.

**Propuesta actual**

Actualmente nos encontramos en el paso 2 del proceso. Stride Labs ha seleccionado un consejo asesor de 5 miembros, y la comunidad Stride está buscando la aprobación de este consejo por el gobierno del Hub de Cosmos. El consejo de 5 miembros está compuesto por los siguientes miembros:

· Lexa (Hypha Coop) - [https://twitter.com/LexaMichaelides](https://twitter.com/LexaMichaelides)

· Crypto Cakir (Stake and Relax) - [https://twitter.com/CryptoCakir](https://twitter.com/CryptoCakir)

· EffortCapital (Blockworks) - [https://twitter.com/effortcapital](https://twitter.com/effortcapital)

· Damien (SimplyStaking) - [https://twitter.com/damobon](https://twitter.com/damobon)

· Long (Notional) - [https://twitter.com/mgl2150](https://twitter.com/mgl2150)

En caso de que los siguientes miembros sean aprobados por el gobierno, comenzarán a evaluar las solicitudes de los validadores el 21 de agosto, y el conjunto de validadores se elegirá a más tardar el 28 de agosto. Los validadores seleccionados se debatirán en el foro de gobierno de Stride el 30 de agosto y se someterán a votación en la cadena de bloques de Stride el 6 de septiembre. Si se aprueba esta votación, el proceso de delegación se habrá completado.

**Vota SÍ a esta propuesta para expresar la aprobación del consejo consultivo de 5 miembros seleccionado.**

**Vote NO a esta propuesta para expresar su desacuerdo con el consejo consultivo de 5 miembros seleccionado.**




_______________ 
_Traducción realizada por Wimel del validador [Bunker Stake](https://www.bunkerstake.io/) para la comunidad de habla hispana_.