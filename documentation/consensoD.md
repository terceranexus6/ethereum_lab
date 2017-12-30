# Consenso Distribu�do

## Contenido:

 1. Introducci�n
 2. Consenso Distribu�do en bitcoins
 3. Otras aplicaciones
      - Consenso distribu�do en Elecciones
      - Consenso distribu�do en Energ�a
      - Consenso distribu�do en IoT
 4. Experimento con Ethereum - Programar un sistema de votaci�n
 5. Nuevas fronteras - ideas y conclusiones
 6. Bibliograf�a

## I. Introducci�n

La base fundamental del **consenso distribu�do** est� en la idea de compartir el control de la evoluci�n de datos en una red com�n. Uno de los ejemplos m�s conocidos de Consenso Distribu�do es Blockchain, una gran base de datos distribu�da entre varios participantes, o nodos. Este sistema est� contenido en un _ledger_ que contiene el historial de todas las transacciones actualizadas. Los nodos est�n conectados en una red descentralizada, y se comunican a trav�s de un protocolo concreto.

La clave que mueve todo este sistema, est� alrededor de un tipo concreto de mensajes llamados "token", estos token contienen informaci�n, que viaja encriptada, y puede contener cualquier cosa que digitalmente se permita, como dinero (este es el caso de los bitcoins), un voto, un alquiler, energ�a, cualquier cosa. En relaci�n con econom�a (impulso inicial para este sistema) se espera que el consenso distribu�do reduzca el riesgo operacional, y aunque incluso una de las criptomonedas de m�s peso (bitcoins) no han conseguido despegar con toda la fuerza que pod�a esperarse, varias startups, usuarios e incluso bancos est�n apostando por este sistema.

## II. Consenso distribu�do en bitcoins

Dado que el sistema se plante� inicialmente para su uso con las criptomonedas, es conveniente comprender c�mo funciona este sistema con los Bitcoins. Para ello, pretendo basarme en la explicaci�n de una transacci�n corriente.

Alice tiene una cartera con x cantidad de bitcoins, y pretende comprar un caf� en el puesto de Bob, que tiene otra cartera. Para ello, se _propone_ una transacci�n por el valor en BTC entre Alice y Bob. De este modo, si la transacci�n queda aprobada, la custodia de esa cantidad de BTC queda cedida irrevocablemente a la cartera de Bob. Para que esto ocurra, la transacci�n pasa a una cadena de transacciones pendientes de resolverse, en una red compuesta por varios nodos. La _firma_ de esta transacci�n depende de un problema matem�tico, que requiere de trabajo computacional para resolverse, y que una vez resuelto, actualizar� la red y declarar� la transacci�n como hecha, de forma que esa misma transacci�n no pueda modificarse, y esta informaci�n actualizada llegar� al resto de nodos. En este paso encontramos lo que se denomina _mining_, es decir, el proceso por el cual los nodos compiten por procesar ese trabajo matem�tico a cambio de una recompensa en BTC que se crea en ese mismo momento, es decir, no son transacciones, si no creaciones de m�s BTC que posteriormente se mover�n en transacciones.

Una vez que la transacci�n del caf� entre Alice y Bob est� firmada por alg�n nodo de la red y la informaci�n se actualiza, este gesto es irrevocable y esos bitcoins pasan a la custodia de Bob. Alice y Bob pueden mantenerse an�nimos y tener, respectivamente, m�s de una cartera.

La firma de dicha transacci�n supone que �sta pase a manos de todos los nodos interesados en resolver el problema (y obtener la recompensa) pero no los datos de la transacci�n, si no simplemente su incorporaci�n en el historial. De modo que los usuarios y los motivos se mantienen privados, pero el control del flujo de transacciones es compartido.

## III. Otras aplicaciones de Consenso Distribu�do

Una vez hemos analizado c�mo funciona el sistema distribu�do en una red P2P aplicado a los BTC, podemos abarcar el concepto en otros contextos. Algunos de los m�s punteros para los pr�ximos a�os son:

### En procesos electorales

Es interesante como, el proceso anteriormente descrito puede agregarse a otros conceptos cl�sicos, como una votaci�n democr�tica. Un ejemplo de esto es Horizon State. En su _white paper_, Horizon State explica c�mo utiliza la plataforma de Ethereum para desplegar sus contratos (el sistema de votaci�n) y que adem�s [liberan en github](). Los contratos que han realizado se basan, a su vez, en documentaci�n que la propia organizaci�n de Ethereum cede bajo el nombre de "C�mo crear una democracia en blockchain".

La idea principal es asegurar el voto �nico del usuario pero a su vez mantener el anonimato y la privacidad de su voto, en consecuencia, sin renunciar a una v�a actualizada de voto. En este caso el voto ser� el _token_, y �ste ser� verificado por el resto de nodos, y a�adido a la lista de votos realizados una vez firmado de forma irrevocable al actualizarse la red. De este modo, al igual que ocurrir�a con los BTC, un ataque supone una cantidad de variables casi imposible de asumir (el momento adecuado, una capacidad computacional importante, etc) para cada uno de los votos, lo que lo convierte en un sistema de votaci�n bastante seguro. Adem�s, defienden, el coste de la votaci�n es mucho menos que usando un sistema convencional.   

### En energ�a

Hace unos meses, una startup llamada [Powerledger](https://tge.powerledger.io) lanz� la idea de aplicar consenso distribu�do al intercambio de energ�a solar a trav�s de nodos en una _blockchain_. La idea es dar la opci�n de vender su energ�a solar extra a los usuarios sin necesidad de intermediarios en un sistema centralizado. La aplicaci�n pretende llevar un seguimiento del consumo energ�tico de cada participante y generar transacciones a tiempo real en base a las necesidades de cada usuario. En la p�gina web explican los beneficios de darle control a los participantes de la red, adem�s de la transparencia de las transacciones. Por ahora, tan s�lo han lanzado un evento para generar tokens tradeables en el futuro y han comenzado el desarrollo de la aplicaci�n, pero ya cuentan con millones de euros para llevar a cabo el proyecto.

### En IoT

Empresas de peso como IBM ya han empezado a explorar las posibilidades de utilizar el modelo distribu�do en IoT. La idea que IBM quiere implementar es una comunicaci�n directa entre los elementos que componen una red de IoT (como la monitorizaci�n de un entorno) sin necesidad de intermediarios.

Bajo esta idea se sustenta, por ejemplo, [Filament](https://filament.com), es una empresa que pretende crear un sistema extra seguro de comunicaci�n entre dispositivos hardware, que actualizan la informaci�n en tiempo real y cada dispositivo (nodo) tiene la oportunidad de validar la interacci�n con el entorno (la transacci�n) y a�adir dicha informaci�n (token) a la pila com�n. La seguridad del sistema reside en que los posibles ataques en despliegue hacia los dispositivos accediendo a un server principal mediante reconocimiento no son funcionales, y que los ataques a nodos por separado en el momento justo, a parte de ser complicados y costosos, son pr�cticamente in�cuos si no est�n enmarcados en el contexto global.

## IV.  Experimento con Ethereum - Programar un sistema de votaci�n

Como se ha mencionado previamente, Ethereum da la oportunidad de desplegar contratos en su plataforma (cartera de ethereum) tanto en un sandbox virtual sin repercusi�n real como en el sistema principal, usando ETH real. Para la realizaci�n de este apartado, he probado el despliegue en virtual, y m�s tarde he comprado ETH para realizar un experimento a m�nimo coste (0'0003 ETH) en el sistema central. Para que el experimento funcione deben tenerse en cuenta los elementos fundamentales del consenso distribu�do:

- Los token
- Los nodos
- Las transacciones

Para programar y desplegar un token, en su m�nima expresi�n, ser�a:

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
        balanceOf[_to] += _value;                           // A�adir al receptor
    }
}
```
Sin embargo, para a�adirle algo de complejidad, existen otras variables a tener en cuenta, como declarar el **nombre**, el **s�mbolo**, notificaciones para clientes, etc. En el [anexo de contratos](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts) se puede encontrar un [ejemplo m�s completo](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts/complextoken.cpp) de token.

Los detalles de la transferencia tambi�n se especifican en los bloques de contratos de token, por ejemplo podemos observar la implementaci�n de la funci�n `_transfer` que es local y s�lo puede usarse dentro del propio contrato que definamos.

```
    function _transfer(address _from, address _to, uint _value) internal {
        require (_to != 0x0);                               // previene transferencias a 0x0 address.
        require (balanceOf[_from] > _value);                // Comprueba solvencia
        require (balanceOf[_to] + _value > balanceOf[_to]); // Comprueba overflows
        require(!frozenAccount[_from]);                     // Comprueba si la cuenta esta congelada
        require(!frozenAccount[_to]);                       // Comprueba si el receptor (su cuenta) est� congelada
        balanceOf[_from] -= _value;                         // Retira del emisor
        balanceOf[_to] += _value;                           // A�ade al receptor
        Transfer(_from, _to, _value);
    }
```
 Y tambi�n pueden automatizarse ventas y compras, funci�n muy �til, por ejemplo, en la aplicaci�n de Consenso Descentralizado de IoT. Para ello, se pueden decinir funciones para ambos procesos y ser llamados en el propio contrato. Por �ltimo, pueden definirse funciones para POW (Proof of Work) de forma que agreguemos el esfuerzo matem�tico para la miner�a de nuestra moneda. Ets parte es interesante porque podemos a�adir la f�rmula que deseemos.

 ```
 uint PruebaActual = 1; // puedes averiguar el cubo de este n�mero?

     function premioAlGenio(uint respuesta, uint siguiente) {
         require(respuesta**3 == PruebaActual); // Si responde mal no contin�a
         balanceOf[msg.sender] += 1;         // Premia a este usuario
         PruebaActual = siguiente;   // Pone la siguiente prueba
     }
 ```

 Evidentemente el trabajo computacional de esta prueba es m�nimo, pero por ejemplo puede intercambiarse por una prueba que implique generar _hashes_ de varios n�meros hasta que encuentre uno menor a la dificultad dada. Existen tambi�n [otros sistemas](https://blog.ethereum.org/2015/12/28/understanding-serenity-part-2-casper/) que ya est�n siendo utilizados.

 UNa vez que tenemos definido nuestro token y los detalles de las transacciones, podemos empezar a trabajar sobre los nodos. Los nodos pueden representar a usuarios individuales o bots que interaccionan autom�ticamente, pero tambi�n podemos trabajar con asociaciones de nodos (que exiten dentro del propio blockchain) y que a su vez pueden tener diferentes esquemas. Por ejemplo, podemos trabajar con uno de los esquemas previamente definidos, una votaci�n democr�tica, con un l�der que organiza a los miembros del grupo, pero cada miembro tiene un voto (el token) y pueden automatizarse el conteo de forma limpia y eficaz. Podemos encontrar un [ejemplo de este contrato](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts/demo.cpp) en el anexo de contratos. Puede modificarse ligeramente este mismo modelo para crear, en lugar de un organizador y varios usuarios iguales, usuarios con distinto peso dependiendo, por ejemplo, de su solvencia en tokens.

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

 Tambi�n es posible implementar un sistema de [_democracia l�quida_](https://github.com/terceranexus6/ethereum_lab/tree/master/contracts/democracialiq.cpp) en el que un votante puede delegar su voto en otro usuario. De este modo, la transferencia de tokens le ceder�a al receptor el voto del emisor.

 Para experimentar con nuestros contratos en el sandbox, tan s�lo tenemos que incluir el c�digo en la plataforma de ethereum y desplegarlo. Nos saldr�n algunas opciones que debemos rellenar, y una vez desplegado, podemos compartir el contrato con otros usuarios. Podemos utilizarlo tanto con nuestro propio token (definido previamente en otro contrato) como usando ETH real.

 ## V. Nuevas fronteras - ideas y conclusiones

Uno de los mayores obstáculos que este sistema tiene que superar antes de incluirse con más profundidad en la tecnología es precisamente la aceptación de los usuarios. Sin embargo, una vez traspasada esta barrera, el modelo resuelve algunos de los problemas fundamentales de las aplicaciones actuales para los casos que se han estudiado en este art�culo: la seguridad, la eficiencia y el coste. Es por esto, que más y más empresas se lanzan a adaptar sus sistemas a esta nueva forma de red.

## IV. Bibliografía

- [Ethereum.org](https://blog.ethereum.org)
- [Powerledger](https://tge.powerledger.io)
- [Filament](https://filament.com)
