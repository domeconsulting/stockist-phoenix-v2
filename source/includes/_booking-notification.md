# Notificación de reservas PUSH

Soporte para que el proveedor reciba una notificación PUSH cuando se crea una nueva reserva o bien se cancela o modifica
una reserva ya existente. Una vez recibida la notifiación, el proveedor puede utilizar el mensaje BookingRetrievalRequest 
(filtrando por localizador) para recuperar la información actual de la reserva y actualizarla en su sistema.

<aside class="notice">
Aunque no es obligatorio que el proveedor implemente la recepción de reservas PUSH 
(puede recuperar periódicamente las reservas mediante BookingRetrievalRequest filtrando por rango de fechas), recomendamos que así lo haga.
De esta forma, se evitan posibles problemas de overbooking al tener la información sincronizada en tiempo real.
</aside>


### Formato notificación PUSH

Por simplicidad, la notificación PUSH se realizará mediante una llamada HTTP GET a una URL de libre elección para el proveedor, informando los siguientes parámetros:

Parámetro | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
hotelCode | *Integer* | Sí | Identificador de hotel
reference | *String* | Sí |Localizador de la reserva
action | *Enum* | Sí |Acción que se ha realizado sobre la reserva (Creation: Creación de una nueva reserva, Cancellation: Cancelación de la reserva, Modification: Modificación de la reserva)
card | *Boolean* | Sí |Indica si la reserva contiene datos sobre una tarjeta de crédito (true/false)

Ejemplo llamadas:

- Notificación creación nueva reserva EPL10032017140800-SALE: **http://www.anyurl.com/hotelCode?1234&reference?EPL10032017140800-SALE&action?Creation&card?false**
- Notificación cancelación reserva EPL10032017140800-SALE: **http://www.anyurl.com/hotelCode?1234&reference?EPL10032017140800-SALE&action?Cancellation&card?false**
 
 