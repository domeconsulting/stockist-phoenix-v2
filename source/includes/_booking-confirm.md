# BookingConfirm

> Ejemplo BookingConfirmRequest para confirmar una reserva en particular

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingConfirmRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>  
    <hotelCode>1234</hotelCode>
    <reference>EPL10032017140800-SALE</reference>
    <confirmReference>REFERENCIACONFIRMACION</confirmReference>
</BookingConfirmRequest>
````

````json
{
  "BookingConfirmRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "reference": "EPL10032017140800-SALE",
    "confirmReference": "REFERENCIACONFIRMACION"
  }
}
````

> Ejemplo respuesta BookingConfirmResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingConfirmResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <status>success</status>
</BookingConfirmResponse>
````

````json
{
  "BookingConfirmResponse": {
    "sessionId": "SUP#FOO#123456789",
    "status": "success"
  }
}
````

> Ejemplo respuesta BookingConfirmResponse procesada incorrectamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingConfirmResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <notification code="DSUP-7">
        <type>E</type>
        <text>La funcionalidad ConfirmBooking-Inbound no está activada. Por favor, consulte su Account Manager</text>
    </notification>
</BookingConfirmResponse>
````

````json
{
  "BookingConfirmResponse": {
    "sessionId": "SUP#FOO#123456789",
    "notification": {
      "-code": "DSUP-7",
      "type": "E",
      "text": "La funcionalidad ConfirmBooking-Inbound no está activada. Por favor, consulte su Account Manager"
    }
  }
}
````

Mensaje utilizado para confirmación de reservas.

### BookingConfirmRequest

Mensaje petición de recuperación de reservas
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
reference | *String* | Sí | Localizador de la reserva de Hotetec
hotelCode | *Integer* | Sí | Código de hotel
confirmReference | *String* | No | Referencia de confirmación de reserva.

### BookingConfirmResponse

Mensaje respuesta de confirmación de reservas

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí |Identificador de la sesión que ha procesado la transacción
status | *String* | No | Indica si la confirmación se ha realizado correctamente o no ('success'=sí, 'Error'=no)
notification| **Notification** | No | En caso de que la confirmación no haya sido correcta, contendrá el error.
↳ @code| *String* | Sí | Contiene el código de error de Hotetec.
↳ type| *String* | Sí | Indica si es un error (E) o un warning (W).
↳ text| *String* | Sí | Texto descriptivo del error
