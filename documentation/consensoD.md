# Consenso Distribuído

## Contenido:

 1. Introducción
 2. Consenso Distribuído en bitcoins
 3. Otras aplicaciones
      - Consenso distribuído en Elecciones
      - Consenso distribuído en Energía
      - Consenso distribuído en IoT
 4. Experimento con Ethereum - Programar un sistema de votación
 5. Nuevas fronteras - ideas y conclusiones
 6. Bibliografía

## I. Introducción

La base fundamental del **consenso distribuído** está en la idea de compartir el control de la evolución de datos en una red común. Uno de los ejemplos más conocidos de Consenso Distribuído es Blockchain, una gran base de datos distribuída entre varios participantes, o nodos. Este sistema está contenido en un _ledger_ que contiene el historial de todas las transacciones actualizadas. Los nodos están conectados en una red descentralizada, y se comunican a través de un protocolo concreto.

La clave que mueve todo este sistema, está alrededor de un tipo concreto de mensajes llamados "token", estos token contienen información, que viaja encriptada, y puede contener cualquier cosa que digitalmente se permita, como dinero (este es el caso de los bitcoins), un voto, un alquiler, energía, cualquier cosa. En relación con economía (impulso inicial para este sistema) se espera que el consenso distribuído reduzca el riesgo operacional, y aunque incluso una de las criptomonedas de más peso (bitcoins) no han conseguido despegar con toda la fuerza que podía esperarse, varias startups, usuarios e incluso bancos están apostando por este sistema.

## II. Consenso distribuído en bitcoins

Dado que el sistema se planteó inicialmente para su uso con las criptomonedas, es conveniente comprender cómo funciona este sistema con los Bitcoins. Para ello, pretendo basarme en la explicación de una transacción corriente.

Alice tiene una cartera con x cantidad de bitcoins, y pretende comprar un café en el puesto de Bob, que tiene otra cartera. Para ello, se _propone_ una transacción por el valor en BTC entre Alice y Bob. De este modo, si la transacción queda aprobada, la custodia de esa cantidad de BTC queda cedida irrevocablemente a la cartera de Bob. Para que esto ocurra, la transacción pasa a una cadena de transacciones pendientes de resolverse, en una red compuesta por varios nodos. La _firma_ de esta transacción depende de un problema matemático, que requiere de trabajo computacional para resolverse, y que una vez resuelto, actualizará la red y declarará la transacción como hecha, de forma que esa misma transacción no pueda modificarse, y esta información actualizada llegará al resto de nodos. En este paso encontramos lo que se denomina _mining_, es decir, el proceso por el cual los nodos compiten por procesar ese trabajo matemático a cambio de una recompensa en BTC que se crea en ese mismo momento, es decir, no son transacciones, si no creaciones de más BTC que posteriormente se moverán en transacciones.

Una vez que la transacción del café entre Alice y Bob está firmada por algún nodo de la red y la información se actualiza, este gesto es irrevocable y esos bitcoins pasan a la custodia de Bob. Alice y Bob pueden mantenerse anónimos y tener, respectivamente, más de una cartera.

La firma de dicha transacción supone que ésta pase a manos de todos los nodos interesados en resolver el problema (y obtener la recompensa) pero no los datos de la transacción, si no simplemente su incorporación en el historial. De modo que los usuarios y los motivos se mantienen privados, pero el control del flujo de transacciones es compartido.

## III. Otras aplicaciones de Consenso Distribuído

Una vez hemos analizado cómo funciona el sistema distribuído en una red P2P aplicado a los BTC, podemos abarcar el concepto en otros contextos. Algunos de los más punteros para los próximos años son:

### En procesos electorales

Es interesante como, el proceso anteriormente descrito puede agregarse a otros conceptos clásicos, como una votación democrática. Un ejemplo de esto es Horizon State. En su _white paper_, Horizon State explica cómo utiliza la plataforma de Ethereum para desplegar sus contratos (el sistema de votación) y que además [liberan en github](). Los contratos que han realizado se basan, a su vez, en documentación que la propia organización de Ethereum cede bajo el nombre de "Cómo crear una democracia en blockchain".

La idea principal es asegurar el voto único del usuario pero a su vez mantener el anonimato y la privacidad de su voto, en consecuencia, sin renunciar a una vía actualizada de voto. En este caso el voto será el _token_, y éste será verificado por el resto de nodos, y añadido a la lista de votos realizados una vez firmado de forma irrevocable al actualizarse la red. De este modo, al igual que ocurriría con los BTC, un ataque supone una cantidad de variables casi imposible de asumir (el momento adecuado, una capacidad computacional importante, etc) para cada uno de los votos, lo que lo convierte en un sistema de votación bastante seguro. Además, defienden, el coste de la votación es mucho menos que usando un sistema convencional.   

### En energía

Hace unos meses, una startup llamada [Powerledger](https://tge.powerledger.io) lanzó la idea de aplicar consenso distribuído al intercambio de energía solar a través de nodos en una _blockchain_. La idea es dar la opción de vender su energía solar extra a los usuarios sin necesidad de intermediarios en un sistema centralizado. La aplicación pretende llevar un seguimiento del consumo energético de cada participante y generar transacciones a tiempo real en base a las necesidades de cada usuario. En la página web explican los beneficios de darle control a los participantes de la red, además de la transparencia de las transacciones. Por ahora, tan sólo han lanzado un evento para generar tokens tradeables en el futuro y han comenzado el desarrollo de la aplicación, pero ya cuentan con millones de euros para llevar a cabo el proyecto.

### En IoT

Empresas de peso como IBM ya han empezado a explorar las posibilidades de utilizar el modelo distribuído en IoT. La idea que IBM quiere implementar es una comunicación directa entre los elementos que componen una red de IoT (como la monitorización de un entorno) sin necesidad de intermediarios.

Bajo esta idea se sustenta, por ejemplo, [Filament](https://filament.com), es una empresa que pretende crear un sistema extra seguro de comunicación entre dispositivos hardware, que actualizan la información en tiempo real y cada dispositivo (nodo) tiene la oportunidad de validar la interacción con el entorno (la transacción) y añadir dicha información (token) a la pila común. La seguridad del sistema reside en que los posibles ataques en despliegue hacia los dispositivos accediendo a un server principal mediante reconocimiento no son funcionales, y que los ataques a nodos por separado en el momento justo, a parte de ser complicados y costosos, son prácticamente inócuos si no están enmarcados en el contexto global.

## IV.  Experimento con Ethereum - Programar un sistema de votación

Como se ha mencionado previamente, Ethereum da la oportunidad de desplegar contratos en su plataforma (cartera de ethereum) tanto en un sandbox virtual sin repercusión real como en el sistema principal, usando ETH real. Para la realización de este apartado, he probado el despliegue en virtual, y más tarde he comprado ETH para realizar un experimento a mínimo coste (0'0003 ETH) en el sistema central. Para que el experimento funcione deben tenerse en cuenta los elementos fundamentales del consenso distribuído:

- Los token
- Los nodos
- Las transacciones

Para programar y desplegar un token, en su mínima expresión, sería:

```
contract MiToken {
    /* esto crea un array con el balance */
    mapping (address => uint256) public balanceOf;

    /*Inicializa el contrato con una cantidad inicial de tokens para el creador del contrato*/
    function MiToken(
        uint256 initialSupply
        ) {
        balanceOf[msg.sender] = initialSupply;              // Darle al creador los tokens
    }

    /* enviar monedas */
    function transfer(address _to, uint256 _value) {
        require(balanceOf[msg.sender] >= _value);           // Comprobar que el emisor tiene solvencia
        require(balanceOf[_to] + _value >= balanceOf[_to]); // Comprobar overflows
        balanceOf[msg.sender] -= _value;                    // Sustraer del emisor
        balanceOf[_to] += _value;                           // Añadir al receptor
    }
}
```
Sin embargo, para añadirle algo de complejidad, existen otras variables a tener en cuenta, como declarar el **nombre**, el **símbolo**, notificaciones para clientes, etc. En el [anexo de contratos](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts) se puede encontrar un [ejemplo más completo](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts/complextoken.cpp) de token.

Los detalles de la transferencia también se especifican en los bloques de contratos de token, por ejemplo podemos observar la implementación de la función `_transfer` que es local y sólo puede usarse dentro del propio contrato que definamos.

```
    function _transfer(address _from, address _to, uint _value) internal {
        require (_to != 0x0);                               // previene transferencias a 0x0 address.
        require (balanceOf[_from] > _value);                // Comprueba solvencia
        require (balanceOf[_to] + _value > balanceOf[_to]); // Comprueba overflows
        require(!frozenAccount[_from]);                     // Comprueba si la cuenta esta congelada
        require(!frozenAccount[_to]);                       // Comprueba si el receptor (su cuenta) está congelada
        balanceOf[_from] -= _value;                         // Retira del emisor
        balanceOf[_to] += _value;                           // Añade al receptor
        Transfer(_from, _to, _value);
    }
```
 Y también pueden automatizarse ventas y compras, función muy útil, por ejemplo, en la aplicación de Consenso Descentralizado de IoT. Para ello, se pueden decinir funciones para ambos procesos y ser llamados en el propio contrato. Por último, pueden definirse funciones para POW (Proof of Work) de forma que agreguemos el esfuerzo matemático para la minería de nuestra moneda. Ets parte es interesante porque podemos añadir la fórmula que deseemos.

 ```
 uint PruebaActual = 1; // puedes averiguar la raiz cuadrada de este número?

     function premioAlGenio(uint respuesta, uint siguiente) {
         require(respuesta**3 == PruebaActual); // Si responde mal no continúa
         balanceOf[msg.sender] += 1;         // Premia a este usuario
         PruebaActual = siguiente;   // Pone la siguiente prueba
     }
 ```

 Evidentemente el trabajo computacional de esta prueba es mínimo, pero por ejemplo puede intercambiarse por una prueba que implique generar _hashes_ de varios números hasta que encuentre uno menor a la dificultad dada. Existen también [otros sistemas](https://blog.ethereum.org/2015/12/28/understanding-serenity-part-2-casper/) que ya están siendo utilizados.

 UNa vez que tenemos definido nuestro token y los detalles de las transacciones, podemos empezar a trabajar sobre los nodos. Los nodos pueden representar a usuarios individuales o bots que interaccionan automáticamente, pero también podemos trabajar con asociaciones de nodos (que exiten dentro del propio blockchain) y que a su vez pueden tener diferentes esquemas. Por ejemplo, podemos trabajar con uno de los esquemas previamente definidos, una votación democrática, con un líder que organiza a los miembros del grupo, pero cada miembro tiene un voto (el token) y pueden automatizarse el conteo de forma limpia y eficaz. Podemos encontrar un [ejemplo de este contrato](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts/demo.cpp) en el anexo de contratos. Puede modificarse ligeramente este mismo modelo para crear, en lugar de un organizador y varios usuarios iguales, usuarios con distinto peso dependiendo, por ejemplo, de su solvencia en tokens.

```
uint quorum = 0;
uint seh = 0;
uint nah = 0;

for (uint i = 0; i <  p.votos.length; ++i) {
    Vote v = p.votos[i];
    uint pesoDelVoto = compartirDireccionToken.balanceDel(v.votante);
    quorum += pesoDelVoto;
    if (v.inSupport) {
        seh += pesoDelVoto;
    } else {
        nah += pesoDelVoto;
    }
}
```

 También es posible implementar un sistema de [_democracia líquida_](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts/democracialiq.cpp) en el que un votante puede delegar su voto en otro usuario. De este modo, la transferencia de tokens le cedería al receptor el voto del emisor.

 Para experimentar con nuestros contratos en el sandbox, tan sólo tenemos que incluir el código en la plataforma de ethereum y desplegarlo. Nos saldrán algunas opciones que debemos rellenar, y una vez desplegado, podemos compartir el contrato con otros usuarios. Podemos utilizarlo tanto con nuestro propio token (definido previamente en otro contrato) como usando ETH real.

 ## V. Nuevas fronteras - ideas y conclusiones

Uno de los mayores obstáculos que este sistema tiene que superar antes de incluirse con más profundidad en la tecnología es precisamente la aceptación de los usuarios. SIn embargo, una vez traspasada esta barrera, el modelo resuelve algunos de los problemas fundamentales de las aplicaciones actuales para los casos que se han estudiado en este artículo: la seguridad, la eficiencia y el coste. Es por esto, que más y más empresas se lanzan a 
