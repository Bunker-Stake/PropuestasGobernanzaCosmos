# Propuesta de Gobernanza 825:

- Ver en [Mintscan](https://www.mintscan.io/cosmos/proposals/825).
- Ver en [Ping.pub](https://ping.pub/cosmos/gov/825).
- Ver en [Bigdipper](https://bigdipper.live/cosmos/proposals/825).

## Título: Actualización de software v13

### Resumen:

El lanzamiento de Gaia v13 es un lanzamiento importante que seguirá el proceso de gobernanza estándar, enviando inicialmente este post en el foro del Hub de Cosmos. Tras recoger los comentarios del foro _(~ 1 semana)_ y adaptar la propuesta según sea necesario, se enviará una propuesta de gobernanza al Hub de Cosmos para su votación. El periodo de votación en la cadena suele durar 2 semanas.

Tras la aprobación de la votación de gobernanza, se pedirá a los validadores que actualicen el binario del Hub de Cosmos a la altura especificada en la propuesta en la cadena.

### Contenido de la versión:

La versión correspondiente en Github es: [Gaia v13 Release 3](https://github.com/cosmos/gaia/issues/2700).

Hay dos cambios planeados para la v13:

El **primer cambio** es de carácter interno, con la eliminación del antiguo código del módulo de liquidez de Gravity Dex en la base de código de Gaia. El módulo de liquidez de Gravity Dex, fue desactivado a principios de este año y los fondos restantes han sido devueltos a los depositantes o han sido transferidos a la comunidad del Hub de Cosmos. La versión v13 eliminará todo el código redundante relacionado con este módulo de la base de código de Gaia.

El **segundo cambio** es una actualización del módulo _provider_ de la seguridad Interchain para el Hub de Cosmos.

La release candidata se puede encontrar [aquí](https://github.com/cosmos/gaia/releases/tag/v13.0.0-rc0).

La hoja de ruta para esta y futuras versiones puede comprobarse [aquí](https://informal.systems/blog/informal-hub-team-jan-2023-update#2023-cosmos-hub-roadmap).

### Pruebas y Testnets:

La versión 13 se somete a rigurosas pruebas, como las pruebas e2e, las pruebas de integración y las pruebas diferenciales. Las pruebas diferenciales son similares a las de integración, pero comparan el estado del sistema con un estado esperado generado a partir de la implementación de un modelo. Además, la v13 será probada de forma independiente por el equipo de Hypha co-op.

Los validadores y operadores de nodos pueden unirse a una red de pruebas pública para participar en una prueba de actualización a una versión candidata antes de que el Hub de Cosmos actualice a la versión final. Puede encontrar la información pertinente _(archivo génesis, peers, etc)_ para unirse a la red de prueba de la versión _(theta-testnet-001)_ [aquí](https://github.com/cosmos/testnets/tree/master/public), o a la red de prueba de seguridad replicada _(provider)_ [aquí](https://github.com/cosmos/testnets/blob/master/replicated-security/provider/README.md).

### Factores de riesgo potenciales:

Aunque se hayan realizado pruebas y simulaciones muy exhaustivas, siempre existe el riesgo de que el Hub de Cosmos experimente problemas debidos a posibles fallos o errores de las nuevas funciones. En caso de problemas graves, los validadores deberán dejar de utilizar la red inmediatamente.

La coordinación con los validadores tendrá lugar en el canal _"#cosmos-hub-validators-verified"_ del Discord de Cosmos Network para crear y ejecutar un plan de contingencia. Lo más probable es que se trate de una versión de emergencia con correcciones o la recomendación de considerar abortada la actualización y volver a la versión anterior de gaia (v12).

### Votaciones sobre la gobernanza

Los siguientes puntos resumen las opciones de voto y lo que significan para esta propuesta:

YES - Está de acuerdo en que el Hub de Cosmos se actualice con esta versión.

NO - No está de acuerdo en que el Hub de Cosmos se actualice con esta versión.

NO WITH VETO - Un "NoWithVeto" indica que la propuesta (1) se considera spam, es decir, irrelevante para el Hub de Cosmos, (2) vulnera de forma desproporcionada los intereses minoritarios, o (3) viola o fomenta el no cumplimiento de las normas de participación establecidas actualmente por la gobernanza del Hub de Cosmos. Si el número de votos _"NoWithVeto"_ es superior a un tercio del total de votos, la propuesta se rechaza y los depósitos se queman.

ABSTAIN - Desea contribuir al quórum, pero declina formalmente votar a favor o en contra de la propuesta.




_______________ 
_Traducción realizada por Wimel del validador [Bunker Stake](https://www.bunkerstake.io/) para la comunidad de habla hispana_.