# Propuesta de Gobernanza 810

- Ver en [Mintscan](https://www.mintscan.io/cosmos/proposals/810).
- Ver en [Ping.pub](https://ping.pub/cosmos/gov/810).
- Ver en [Bigdipper](https://bigdipper.live/cosmos/proposals/810).
  
## Título: Propuesta de comunicación, Añadir el Módulo `Fee Abstraction` al Hub de Cosmos

Esta es una propuesta de comunicación para añadir el módulo `Fee Abstraction` al Hub de Cosmos. A un alto nivel, el módulo permitirá que las comisiones de las transacciones en el Hub de Cosmos se paguen con cualquier token cambiando primero ese token por ATOM en Osmosis. La función del módulo se describe con más detalle a continuación.

El módulo `Fee Abstraction` fue desarrollado por el equipo de Notional, y financiado por el Programa de Subvenciones de Osmosis, como un método para resolver los problemas de abstracción de comisiones que actualmente afectan al Ecosistema de Cosmos y dificultan su adopción por parte de ecosistemas externos. El módulo soluciona este problema permitiendo que las comisiones se paguen en cualquier activo de las cadenas que lo implementen sin necesidad de que la cadena cambie sus activos de comisiones aceptadas.

Esta propuesta es meramente una propuesta de comunicación y no supondrá ningún cambio inmediato en el Hub de Cosmos si se aprueba. El módulo deberá añadirse mediante una actualización de software posterior que requerirá una votación independiente. Si se aprueba esta votación, el equipo de Notional ayudará a los responsables del código base del Hub de Cosmos con la integración cuando sea necesario y ayudará a resolver cualquier problema técnico que pueda surgir en el proceso de añadir el módulo.

**Descripción del problema**

Gracias a la `Replicated Security`, el Hub de Cosmos está atravesando un periodo de crecimiento rápido. Hace poco, Neutron se convirtió en el primer cliente de su sistema de seguridad, seguido de cerca por Stride y poco después por Duality.

A medida que crezcan estas integraciones, también aumentará la diversidad de activos recibidos por los stakers de ATOM _(sólo Stride recompensará a los stakers de ATOM con 10 activos diferentes como recompensas de staking)_. A corto plazo, muchas de estas recompensas serán pequeñas y no valdrán las comisiones de gas en ATOM necesarias para transferirlas de vuelta a sus cadenas nativas a través de IBC. Esto es especialmente válido para los delegadores más pequeños.

En lugar de dejar que estos activos se queden sin utilizar en sus carteras, ¿qué pasaría si los participantes en ATOM pudieran utilizar estos activos para pagar las tasas de gas en sustitución de sus ATOMs? Además, ¿qué pasaría si estas tasas de gas se pudieran utilizar para crear un suministro constante de presión de compra constante en el token ATOM? Aquí es donde entra en juego el módulo `Fee Abstraction`.

Del mismo modo, los nuevos usuarios que lleguen a Cosmos como resultado de los próximos cambios de Metamask necesitarán una forma sencilla de integrarse en ATOM utilizando únicamente activos como wETH, USDC o USDT. El módulo de abstracción de comisiones hará todo esto, ayudando a reducir la fricción de la UX de incorporación para los más de 30 millones de usuarios de Metamask.

**Funcionamiento del módulo `Fee Abstraction`**

El módulo `Fee Abstraction` aprovecha las consultas entre cadenas, el middleware de reenvío de paquetes y los recursos ibc para intercambiar periódicamente las comisiones cobradas por transacciones al token nativo de una cadena utilizando Osmosis. La frecuencia con la que se intercambian las comisiones se parametriza. Usando esta característica, el Hub de Cosmos puede tener sus tarifas de transacción pagadas en cualquier activo que tenga un fondo de liquidez en Osmosis, y el activo será intercambiado a ATOM para ser utilizado como una comisión de transacción.

El módulo funciona con el siguiente flujo de trabajo:

- Interchain consulta a Osmosis para determinar el tipo de cambio entre el activo de la comisión y ATOM.
- Recauda los activos de las comisiones de las transacciones ejecutadas.
- El IBC transfiere a Osmosis los activos procedentes de los cobros de comisiones.
- [Si es necesario] Deshace el IBC para preservar la fungibilidad.
- Cambio de ATOM en Osmosis.
- Transferencia del IBC al Hub para su distribución a los validadores y delegadores ATOM.

### Consulta entre cadenas

**Descripción**

De forma periódica, el módulo consulta los datos TWAP de Osmosis a través del IBC para determinar el tipo de cambio entre un determinado activo de comisiones y el token nativo de la cadena _(en este caso, ATOM)_. Osmosis devuelve un acuse de recibo a través del IBC con el tipo de cambio al módulo, que luego se utiliza para establecer el tipo de cambio al que se cobran las comisiones en otros activos para intercambiar.

La frecuencia con la que el módulo envía un mensaje de consulta entre cadenas a Osmosis se rige por el parámetro de periodo de cambio de actualización. Este parámetro es modificable y por defecto está configurado con una frecuencia de 1 hora. Este parámetro se recomienda para limitar al máximo el número de mensajes de consulta enviados a través del IBC por el Hub, manteniendo al mismo tiempo un alto grado de fiabilidad en el tipo de cambio.

**Cobro de comisiones, transferencia, desbloqueo de ruta y cambios**

Las comisiones de transacción recaudadas por el Hub en activos IBC se almacenan en el módulo en el momento de la recogida, y se envían periódicamente a Osmosis a través del IBC. Si el activo de comisiones es nativo de la cadena de Osmosis _(es decir, OSMO o ION)_, se intercambiará por ATOM inmediatamente a través del contrato de intercambio entre cadenas de Osmosis y se enviará de vuelta al Hub.

Si el activo de pago es una denominación IBC que no tiene Osmosis como su cadena de origen, su ruta IBC primero será desbloqueada para mantener la fungibilidad con el correspondiente activo IBC en Osmosis. Por ejemplo, si una transacción en el Hub se paga en el token STARS nativo de Stargaze, el módulo enviaría el token STARs a Osmosis con instrucciones para desbloquear la ruta IBC de los tokens de la siguiente manera:

- Envía los STARs al Hub de Cosmos.
- Envía los STARs a Stargaze.
- Envía los STARs to Osmosis.
- A partir de ahí, los STARs se cambiarán a ATOMs de forma normal y volverán al Hub, donde se distribuirán a los participantes en ATOMs.

Las comisiones se transfieren e intercambian cada hora antes de ser repartidas. Esta característica es un parámetro controlado por el gobierno que puede ajustarse dependiendo de cuántos activos de comisiones externas se utilicen para pagar las comisiones de transacción en el Hub. Cuantas más comisiones que no sean ATOM se paguen, con más frecuencia el Hub debería querer hacer esta transferencia.

**Impacto y beneficios**

El principal beneficio de este módulo es que permitirá aumentar el estatus de ATOM como fuente principal de liquidez de entrada al ecosistema Cosmos. Con la afluencia de nuevos usuarios de Cosmos que acompañará a la próxima integración de Metamask, los usuarios que lleguen a Cosmos con ETH, USDC, USDT, wBTC u otros activos puente de elevado volumen, podrán utilizar fácilmente estos activos para pagar las comisiones de transacción en el Hub de Cosmos antes de poder obtener los tokens de ATOM. La entrada de FIAT como Kado, también podrían permitir la incorporación de liquidez directamente al Hub de Cosmos en activos no ATOM como USDC o ETH. Es importante contar con un mecanismo de incorporación de este tipo antes de que se ponga en marcha la integración de Metamask para que la experiencia de usuario sea lo más sencilla posible para los no usuarios de Cosmos.

Este módulo también permite que las comisiones de transacción en el Hub de Cosmos se paguen en activos recibidos por los participantes de ATOM a través del _Interchain Security_, a la vez que supone una fuente constante de demanda sobre el token ATOM.

Por ejemplo, los participantes de ATOM pueden empezar a pagar las comisiones de transacción en el Hub con activos como NTRN, STRD o incluso stATOM, que se les pagarán a través del _Interchain Security_. Esto no sólo evitará la necesidad de que los participantes de ATOM utilicen ATOM para las comisiones de transacción, sino que también provocará una fuente de demanda constante para el token ATOM en el DEX de Osmosis.

**Fuentes de información**

Repositoro del `Fee Abstraction` en Github: [https://github.com/osmosis-labs/fee-abstraction](https://github.com/osmosis-labs/fee-abstraction).

Enlace de la discusión en el foro: [https://forum.cosmos.network/t/last-call-on-chain-08-02-signaling-proposal-add-the-fee-abstraction-module-to-the-cosmos-hub/11127](https://forum.cosmos.network/t/last-call-on-chain-08-02-signaling-proposal-add-the-fee-abstraction-module-to-the-cosmos-hub/11127)
