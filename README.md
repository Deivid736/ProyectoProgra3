Arquitectura del Sistema

El proyecto utiliza una arquitectura basada en el patrón Producer–Consumer utilizando RabbitMQ para manejar la comunicación entre componentes.

El Producer obtiene un lote de transacciones desde una API mediante una petición GET. Cada transacción se convierte en un mensaje y se publica en RabbitMQ. Dependiendo del banco destino, el mensaje se envía a una cola específica.

RabbitMQ funciona como intermediario, almacenando los mensajes en colas hasta que puedan ser procesados.

El Consumer escucha las colas, recibe las transacciones y las procesa. Finalmente, cada transacción se envía a otra API mediante una petición POST.

Flujo del sistema

El Producer obtiene transacciones mediante un GET.

Las transacciones se publican en RabbitMQ.

RabbitMQ las organiza en colas por banco.

El Consumer consume los mensajes.

El Consumer envía las transacciones a la API mediante un POST.
