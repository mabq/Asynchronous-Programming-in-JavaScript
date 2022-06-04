# Asynchronous-Programming-in-JavaScript

Siempre ten en cuenta que todo lo síncrono tiene que ver con el Call-Stack y todo lo asíncrono con el Task-Queue.

Mira los siguientes protocolos, la finalidad de ambos es producir data de forma progresiva, la principal diferencia entre ambos radica en quien tiene el control:


## Iterator pattern

Un iterador consume valores jalándolos uno a uno desde una colección existente. El iterador tiene el control puesto que decide cuando jalar un valor.

Un iterador puede ser finito o infinito, solamente deja de producir valores cuando ya no existen más valores en la colección o cuando se produce un error.

Es una operación síncrona dado que todo sucede en el Call-Stack.

No importa que la implementación entre una estructura de datos y otra se diferente, si ambas implementan el protocolo iterador podemos consumir los valores utilizando la misma API.


## Observer pattern

Este patrón surge pensado principalmente en interfaces de usuario, donde la generación de la data dependerá de lo que el haga el usuario. La información del evento se pasa como argumento al Callback designado para el manejo del evento.

Los valores son producidos por una fuente externa. El productor tiene el control.

Dado que es imposible determinar la cantidad de eventos que un usuario puede generar (piensa en `mousemove`) estos siempre fueron vistos como eventos puntuales y no como colecciones de datos. El truco esta en cambiar esta mentalidad y __aprender a ver a los eventos como colecciones de datos que arriban con el tiempo__.

Justamente por este motivo las WebAPIs no tienen forma de comunicar un fin o incluso a veces un error en la ejecución, y varían tanto entre unas y otras (mira las APIs entre `onClick`, `fetch`, `setInterval`, etc).

