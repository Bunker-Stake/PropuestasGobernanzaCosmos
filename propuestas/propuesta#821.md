# Propuesta de Gobernanza 821:

- Ver en [Mintscan](https://www.mintscan.io/cosmos/proposals/821).
- Ver en [Ping.pub](https://ping.pub/cosmos/gov/821).
- Ver en [Bigdipper](https://bigdipper.live/cosmos/proposals/821).

## Título: Actualización de Gaia a V12

**Contexto**


El lanzamiento de la versión de Gaia v12 es un lanzamiento importante que seguirá el proceso de gobernanza estándar, presentando en primer lugar este post en el foro del Hub de Cosmos. Tras recoger los comentarios del foro, se enviará una propuesta de gobernanza al Hub de Cosmos para su votación.

Cuando se apruebe la propuesta de gobernanza, los validadores deberán actualizar el binario del Hub de Cosmos a la altura de bloque especificada en la propuesta.

### Contenido de la versión

Esta versión contiene la incorporación del módulo "*Liquid Staking*" y una serie de actualizaciones de las dependencias básicas.

- La propuesta de comunicación pertinente para el módulo de "*Liquid Staking*" es la [nº 790. Liquid staking module: Regulated and efficient liquid staking](https://www.mintscan.io/cosmos/proposals/790).
- El registro completo de cambios y los binarios correspondientes se pueden encontrar [aquí](https://github.com/cosmos/gaia/releases/tag/v12.0.0).
- La hoja de ruta para esta y futuras versiones puede consultarse [aquí](https://informal.systems/blog/informal-hub-team-jan-2023-update#2023-cosmos-hub-roadmap).
  
### Pruebas y testnets

La versión 12 ha sido sometida a rigurosas pruebas, como las pruebas e2e, las pruebas de integración y las pruebas diferenciales. Las pruebas diferenciales son similares a las de integración, pero comparan el estado del sistema con un estado esperado generado a partir de la implementación de un modelo. Además, la versión 12 ha sido probada de forma independiente por Hypha.

Los validadores y operadores de nodos pueden unirse a una red de prueba pública para participar en una actualización de prueba a una versión candidata antes de que el Hub de Cosmos actualice a la versión final. Puede encontrar la información pertinente (archivo génesis, peers, etc.) para unirse a la red de pruebas de la versión (theta-testnet-001) [aquí](https://github.com/cosmos/testnets/tree/master/public), o a la red de pruebas de seguridad replicada *(provider)* [aquí](https://github.com/cosmos/testnets/blob/master/replicated-security/provider/README.md).

### Factores de riesgo potenciales

Aunque se han realizado pruebas y simulaciones muy exhaustivas, siempre existe el riesgo de que el Hub de Cosmos experimente problemas debidos a posibles fallos o errores de las nuevas funciones. En caso de problemas graves, los validadores deberán dejar de utilizar la red inmediatamente.

La coordinación con los validadores tendrá lugar en el canal #cosmos-hub-validators-verified del Discord de Cosmos Network para crear y ejecutar un plan de contingencia. Lo más probable es que se trate de una versión de emergencia con correcciones o la recomendación de considerar cancelada la actualización y volver a la versión anterior de gaia (v11).

### Votaciones sobre la gobernanza

Los siguientes puntos resumen las opciones de voto y lo que significan para esta propuesta:

YES - Está de acuerdo en que el Hub de Cosmos se actualice con esta versión.
NO - No está de acuerdo en que el Hub de Cosmos se actualice con esta versión.
NO WITH VETO - Un "NoWithVeto" indica que la propuesta (1) se considera spam, es decir, irrelevante para el Hub de Cosmos, (2) vulnera de forma desproporcionada los intereses minoritarios, o (3) viola o fomenta el no cumplimiento de las normas de participación establecidas actualmente por la gobernanza del Hub de Cosmos. Si el número de votos "NoWithVeto" es superior a un tercio del total de votos, la propuesta se rechaza y los depósitos se queman.
ABSTAIN - Desea contribuir al quórum, pero declina formalmente votar a favor o en contra de la propuesta.




_______________ 
_Traducción realizada por Wimel del validador [Bunker Stake](https://www.bunkerstake.io/) para la comunidad de habla hispana_.