# Propuesta de Gobernanza 804:

- Ver en [Mintscan](https://www.mintscan.io/cosmos/proposals/804).
- Ver en [Ping.pub](https://ping.pub/cosmos/gov/804).
- Ver en [Bigdipper](https://bigdipper.live/cosmos/proposals/804).

## Título: Actualización de software v11

### Actualización v11 de Gaia

#### Contexto

La hoja de ruta para esta y futuras versiones puede consultarse aquí:

[https://informal.systems/blog/informal-hub-team-jan-2023-update#2023-cosmos-hub-roadmap](https://informal.systems/blog/informal-hub-team-jan-2023-update#2023-cosmos-hub-roadmap)

El lanzamiento de Gaia v11 es un avance importante que seguirá el proceso de gobernanza estándar mediante el envío inicial de este post en el foro de Cosmos Hub. Tras obtener los comentarios del foro, se enviará una propuesta de gobernanza al Hub de Cosmos para su votación.

Una vez aprobado el voto de gobernanza, los validadores deberán actualizar el binario del Hub de Cosmos en el bloque de parada especificado en la propuesta en cadena.

#### Contenido de la versión

Esta versión contiene una serie de actualizaciones de las dependencias básicas y varias correcciones. Las principales características de esta versión son:

- Una actualización de _"Replicated Security"_ a v2.0.0.
- Una versión refactorizada del módulo `Global Fee`.
- Eliminación del estado del módulo de liquidez con retirada forzosa para todas las _pools_ en preparación a eliminar el módulo, de acuerdo con la pasada [Propuesta 801](https://ping.pub/cosmos/gov/801) aprobada.
  
La _release_ y más detalles pueden consultarse aquí: [https://github.com/cosmos/gaia/releases/tag/v11.0.0](https://github.com/cosmos/gaia/releases/tag/v11.0.0)

Nota: La v11 no incluye el módulo _[Liquid Staking](https://ping.pub/cosmos/gov/790)_, ya que aún no está listo para la producción. El módulo _Liquid Staking_ está previsto para la próxima versión de Gaia (v12).

#### Pruebas y redes de prueba

La versión v11 se ha sometido a rigurosas pruebas, como los test e2e, los test de integración y los test diferenciales. Las pruebas diferenciales son similares a las de integración, pero comparan el estado del sistema con un estado esperado generado a partir de la implementación de un modelo. Además, la v11 ha sido probada de forma independiente por Hypha.

Los validadores y operadores de nodos pueden unirse a una red de prueba pública para participar en una actualización de prueba a una versión candidata antes de que el Hub de Cosmos actualice a la versión final. Puede encontrar la información pertinente (archivo génesis, peers, etc.) para unirse a la red de pruebas de la versión _(theta-testnet-001)_ [aquí](https://github.com/cosmos/testnets/tree/master/public), o a la red de pruebas de _"Replicated Security"_ _(provider)_ [aquí](https://github.com/cosmos/testnets/blob/master/replicated-security/provider/README.md).

#### Potenciales factores de riesgo

Aunque se han realizado pruebas y simulaciones muy exhaustivas, siempre existe el riesgo de que el Hub de Cosmos experimente problemas debidos a posibles fallos o errores de las nuevas funciones. En caso de problemas graves, los validadores deben interrumpir inmediatamente el funcionamiento de la red.

La coordinación con los validadores tendrá lugar en el canal [#cosmos-hub-validators-verified](https://discord.com/channels/669268347736686612/798937713474142229) del Discord de la red de Cosmos para crear y ejecutar un plan de contingencia. Lo más probable es que se trate de una versión de emergencia con correcciones o la recomendación de considerar la actualización cancelada y volver a la versión anterior de gaia (v10.0.2).

#### Votaciones en materia de gobernanza

A continuación se resumen las opciones de voto y lo que significan para esta propuesta:

**YES**

Usted acepta que el Hub de Cosmos se actualice con esta versión.

**NO**

No está de acuerdo en que el Hub de Cosmos se actualice con esta versión.

**NO WITH VETO**

EL `NoWithVeto` indica que la propuesta (1) se considera spam, es decir, irrelevante para el Hub de Cosmos, (2) infringe de forma desproporcionada los intereses minoritarios, o (3) viola o fomenta la ruptura de las reglas de compromiso establecidas actualmente por la gobernanza del Hub de Cosmos. Si el número de votos  `NoWithVeto` es superior a un tercio del total de votos, la propuesta se rechaza y los fondos depositados en ella se queman.

**ABSTAIN**

Desea contribuir al quorum pero renuncia formalmente a votar a favor o en contra de la propuesta.




_______________ 
_Traducción realizada por Wimel del validador [Bunker Stake](https://www.bunkerstake.io/) para la comunidad de habla hispana_.
