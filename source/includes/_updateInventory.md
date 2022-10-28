# UpdateInventory

> Ejemplo UpdateInventoryRequest donde se actualiza inventario para un dia concreto y dos tipos de habitación
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<UpdateInventoryRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>
    <hotelCode>1234</hotelCode>
    <inventoryCode>4321</inventoryCode>
    <room>
        <code>DBL#STD</code>
        <day date="20/05/2020">
            <availableQuota>100</availableQuota>
            <status>Open</status>
        </day>
    </room>
    <room>
        <code>SGL#GAL</code>
        <day date="20/05/2020">
            <availableQuota>100</availableQuota>
            <status>Open</status>
        </day>
    </room>
</UpdateInventoryRequest>
````

````json
{
   "UpdateInventoryRequest": {
      "credentials": {
         "systemCode": "SFO",
         "vendorCode": "FOO",
         "user": "BAR",
         "password": "FOOBAR"
      },
      "hotelCode": "1234",
      "inventoryCode": "4321",
      "room": [
         {
            "code": "DBL#STD",
            "day": {
               "availableQuota": "100",
               "status": "Open",
               "date": "20/05/2020"
            }
         },
         {
            "code": "SGL#GAL",
            "day": {
               "availableQuota": "100",
               "status": "Open",
               "date": "20/05/2020"
            }
         }
      ]
   }
}
````

> Ejemplo RoomRatesUpdateRequest donde además de inventario, enviamos un cierre de inventario para una habitación
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<UpdateInventoryRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>
    <hotelCode>1234</hotelCode>
    <inventoryCode>4321</inventoryCode>
    <room>
        <code>DBL#STD</code>
        <day date="20/05/2020">
            <availableQuota>100</availableQuota>
            <status>Closed</status>
        </day>
    </room>
</UpdateInventoryRequest>
````

````json
{
   "UpdateInventoryRequest": {
      "credentials": {
         "systemCode": "SFO",
         "vendorCode": "FOO",
         "user": "BAR",
         "password": "FOOBAR"
      },
      "hotelCode": "1234",
      "inventoryCode": "4321",
      "room": {
         "code": "DBL#STD",
         "day": {
            "availableQuota": "100",
            "status": "Closed",
            "date": "20/05/2020"
         }
      }
   }
}
````

> Ejemplo respuesta UpdateInventoryResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<UpdateInventoryResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
</UpdateInventoryResponse>
````

````json
{
   "UpdateInventoryResponse": {
      "sessionId": "SUP#FOO#123456789"
   }
}
````

Mensaje utilizado para la actualización de inventario de un hotel.
Se puede actualizar: 
- Inventario
- Paros sobre inventario.<br/>

### UpdateInventoryRequest

Mensaje petición de actualización de inventario de hotel.
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
hotelCode | *Integer* | Sí |Código de hotel
inventoryCode| *Integer* | Sí |Código de hotel
room[] | **Room** | Sí | Información asociada a la modalidad de hotel
↳ code| *String* | Sí | Código de habitación y características
↳ day[]| **Day** | Sí | Información asociada a un dia
↳↳ date| *Date* | Sí | Fecha (dd/MM/yyyy)
↳↳ availableQuota| *Integer* | Sí | Unidades de cupo disponible
↳↳ status| *Enum* | Sí | Estado del inventario (Open, OnRequest, Closed)

### UpdateInventoryResponse

Mensaje respuesta que indica si la actualización se ha procesado correctamente

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí| Identificador de la sesión que ha procesado la transacción
notification | **Notification** | No | Información de notificación (Error o Warning)
↳ type | *Enum* | Sí | Tipo de notificación (E:Error, W: Warning)
↳ code | *String* | Sí | Código de la notificación
↳ text | *String* | Sí | Texto descriptivo de la notificación

