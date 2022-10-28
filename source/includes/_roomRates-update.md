# RoomRatesUpdate

> Ejemplo RoomRatesUpdateRequest dónde únicamente se actualiza inventario
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>
    <hotelCode>1234</hotelCode>
    <rate rateCode="BASE">
        <room roomCode="SGL#STD">
            <roomRateDate dateFrom="01/01/2016" dateTo="02/01/2016">
                <availableQuota>9</availableQuota>
                <status>Open</status>
            </roomRateDate>
            <roomRateDate dateFrom="03/01/2016" dateTo="04/01/2016">
                <availableQuota>9</availableQuota>
                <status>Open</status>
            </roomRateDate>
        </room>
        <room roomCode="DBL#STD">
            <roomRateDate dateFrom="01/01/2016" dateTo="02/01/2016">
                <availableQuota>9</availableQuota>
                <status>5</status>
            </roomRateDate>
        </room>
    </rate>
</RoomRatesUpdateRequest>
````

````json
{
  "RoomRatesUpdateRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "rate": {
      "rateCode": "BASE",
      "room": [
        {
          "roomCode": "SGL#STD",
          "roomRateDate": [
            {
              "dateFrom": "01/01/2016",
              "dateTo": "02/01/2016",
              "availableQuota": "9",
              "status": "Open"
            },
            {
              "dateFrom": "03/01/2016",
              "dateTo": "04/01/2016",
              "availableQuota": "9",
              "status": "Open"
            }
          ]
        },
        {
          "roomCode": "DBL#STD",
          "roomRateDate": {
            "dateFrom": "01/01/2016",
            "dateTo": "02/01/2016",
            "availableQuota": "9",
            "status": "5"
          }
        }
      ]
    }
  }
}
````

> Ejemplo RoomRatesUpdateRequest dónde únicamente se actualizan mealPlans (precios y restricciones, sin inventario)
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>
    <hotelCode>1234</hotelCode>
    <rate rateCode="BASE">
        <room roomCode="DBL#STD">
            <roomRateDate dateFrom="01/01/2016" dateTo="07/01/2016">
                <mealPlan code="RO">
                    <minimumStay>2</minimumStay>
                    <maximumStay>7</maximumStay>
                    <closedOnCheckIn>false</closedOnCheckIn>
                    <closedOnCheckOut>false</closedOnCheckOut>
                    <release>0</release>
                    <price>
                        <adults>2</adults>
                        <children>0</children>
                        <amount>100.0</amount>
                        <status>Open</status>
                    </price>
                    <price>
                        <adults>2</adults>
                        <children>1</children>
                        <amount>125.0</amount>
                        <status>Open</status>
                    </price>
                </mealPlan>                
            </roomRateDate>            
        </room>
    </rate>
</RoomRatesUpdateRequest>
````

````json
{
  "RoomRatesUpdateRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "rate": {
      "rateCode": "BASE",
      "room": {
        "roomCode": "DBL#STD",
        "roomRateDate": [
          {
            "dateFrom": "01/01/2016",
            "dateTo": "07/01/2016",
            "mealPlan": [
              {
                "code": "RO",
                "minimumStay": "2",
                "maximumStay": "7",
                "closedOnCheckIn": "false",
                "closedOnCheckOut": "false",
                "release": "0",
                "price": [
                  {
                    "adults": "2",
                    "children": "0",
                    "amount": "100.0",
                    "status": "Open"
                  },
                  {
                    "adults": "2",
                    "children": "1",
                    "amount": "125.0",
                    "status": "Open"
                  }
                ]
              }          
            ]
          }
        ]
      }
    }
  }
}
````

> Ejemplo RoomRatesUpdateRequest actualizando inventario, precios y restricciones para los régimenes RO y BB de la tarifa BASE, modalidad DBL#STD
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>
    <hotelCode>1234</hotelCode>
    <rate rateCode="BASE">
        <room roomCode="DBL#STD">
            <roomRateDate dateFrom="01/01/2016" dateTo="07/01/2016">
                <availableQuota>10</availableQuota>
                <status>Open</status>
                <mealPlan code="RO">
                    <minimumStay>2</minimumStay>
                    <maximumStay>7</maximumStay>
                    <closedOnCheckIn>false</closedOnCheckIn>
                    <closedOnCheckOut>false</closedOnCheckOut>
                    <release>0</release>
                    <price>
                        <adults>2</adults>
                        <children>0</children>
                        <amount>100.0</amount>
                        <status>Open</status>
                    </price>
                    <price>
                        <adults>2</adults>
                        <children>1</children>
                        <amount>125.0</amount>
                        <status>Open</status>
                    </price>
                </mealPlan>
                <mealPlan code="BB">
                    <minimumStay>2</minimumStay>
                    <maximumStay>7</maximumStay>
                    <closedOnCheckIn>false</closedOnCheckIn>
                    <closedOnCheckOut>false</closedOnCheckOut>
                    <release>7</release>
                    <price>
                        <adults>2</adults>
                        <children>0</children>
                        <amount>130.0</amount>
                        <status>Open</status>
                    </price>
                    <price>
                        <adults>2</adults>
                        <children>1</children>
                        <amount>150</amount>
                        <status>Open</status>
                    </price>
                </mealPlan>
            </roomRateDate>
            <roomRateDate dateFrom="08/01/2016" dateTo="09/01/2016">
                <availableQuota>5</availableQuota>
                <status>Open</status>
                <mealPlan code="RO">
                    <minimumStay>2</minimumStay>
                    <maximumStay>7</maximumStay>
                    <closedOnCheckIn>false</closedOnCheckIn>
                    <closedOnCheckOut>false</closedOnCheckOut>
                    <release>0</release>
                    <price>
                        <adults>2</adults>
                        <children>0</children>
                        <amount>110.0</amount>
                        <status>Open</status>
                    </price>
                    <price>
                        <adults>2</adults>
                        <children>1</children>
                        <amount>135.0</amount>
                        <status>Open</status>
                    </price>
                </mealPlan>
            </roomRateDate>
        </room>
    </rate>
</RoomRatesUpdateRequest>
````

````json
{
  "RoomRatesUpdateRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "rate": {
      "rateCode": "BASE",
      "room": {
        "roomCode": "DBL#STD",
        "roomRateDate": [
          {
            "dateFrom": "01/01/2016",
            "dateTo": "07/01/2016",
            "availableQuota": "10",
            "status": "Open",
            "mealPlan": [
              {
                "code": "RO",
                "minimumStay": "2",
                "maximumStay": "7",
                "closedOnCheckIn": "false",
                "closedOnCheckOut": "false",
                "release": "0",
                "price": [
                  {
                    "adults": "2",
                    "children": "0",
                    "amount": "100.0",
                    "status": "Open"
                  },
                  {
                    "adults": "2",
                    "children": "1",
                    "amount": "125.0",
                    "status": "Open"
                  }
                ]
              },
              {
                "code": "BB",
                "minimumStay": "2",
                "maximumStay": "7",
                "closedOnCheckIn": "false",
                "closedOnCheckOut": "false",
                "release": "7",
                "price": [
                  {
                    "adults": "2",
                    "children": "0",
                    "amount": "130.0",
                    "status": "Open"
                  },
                  {
                    "adults": "2",
                    "children": "1",
                    "amount": "150",
                    "status": "Open"
                  }
                ]
              }
            ]
          },
          {
            "dateFrom": "08/01/2016",
            "dateTo": "09/01/2016",
            "availableQuota": "5",
            "status": "Open",
            "mealPlan": {
              "code": "RO",
              "minimumStay": "2",
              "maximumStay": "7",
              "closedOnCheckIn": "false",
              "closedOnCheckOut": "false",
              "release": "0",
              "price": [
                {
                  "adults": "2",
                  "children": "0",
                  "amount": "110.0",
                  "status": "Open"
                },
                {
                  "adults": "2",
                  "children": "1",
                  "amount": "135.0",
                  "status": "Open"
                }
              ]
            }
          }
        ]
      }
    }
  }
}
````

> Ejemplo respuesta RoomRatesUpdateResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
</RoomRatesUpdateResponse>
````

````json
{
  "RoomRatesUpdateResponse": { 
    "sessionId": "SUP#FOO#123456789" 
  }
}
````

Mensaje utilizado para la actualización de inventario y tarifas (precios, paros de venta y restricciones) de un hotel.
Se puede actualizar: 
- Únicamente inventario: Informar los tags availableQuota y status pero no será necesario informar mealPlan.<br/>
- Únicamente precios y restricciones (sin inventario): Informar mealPlan pero no será necesario informar los tags availableQuota y status.<br/>
- Inventario, precios y restricciones en conjunto: Se tendrán que informar los tags availableQuota, status y mealPlan.<br/>

### RoomRatesUpdateRequest

Mensaje petición de actualización de inventario y tarifas de hotel.
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
hotelCode | *Integer* | Sí |Código de hotel
roomRate[] | **RoomRate** | Sí | Información asociada a una combinación de tarifa y modalidad de hotel
↳ @rateCode| *String* | Sí | Código de tarifa
↳ @roomCode| *String* | Sí | Código de modalidad
↳ roomRateDate| **RomRateDate** | Sí | Información relativa a un rango de fechas
↳↳ @dateFrom| *Date* | Sí | Fecha desde (dd/MM/yyyy, rangos cerrados)
↳↳ @dateTo| *Date* | Sí | Fecha hasta (dd/MM/yyyy, rangos cerrados)
↳↳ availableQuota| *Integer* | No<sup>1</sup> | Unidades de cupo disponible
↳↳ status| *Enum* | No<sup>1</sup> | Estado del inventario
↳↳ mealPlan[]| **MealPlan** | No<sup>2</sup> | Información asociada al régimen alimenticio
↳↳↳ @code| *String* | Sí | Código de régimen alimenticio
↳↳↳ minimumStay| *Integer* | Sí | Días de estancia mínima (0: No hay estancia mínima)
↳↳↳ maximumStay| *Integer* | Sí | Días de estancia máxima (0: No hay límite de estancia)
↳↳↳ release| *Integer* | Sí | Días de release (0: No hay release)
↳↳↳ closedOnCheckIn| *Boolean* | Sí | Indica si no está permitida la entrada
↳↳↳ closedOnCheckOut| *Boolean* | Sí | Indica si no está permitida la salida
↳↳↳ price[]| **Price** | Sí | Precio para una ocupación
↳↳↳↳ adults| *Integer* | Sí | Número de adultos
↳↳↳↳ children| *Integer* | Sí | Número de niños
↳↳↳↳ amount| *Double* | Sí | Precio para el total de la ocupación (#.##)
↳↳↳↳ status| *Enum* | Sí | Estado de la ocupación

### RoomRatesUpdateResponse

Mensaje respuesta que indica si la actualización se ha procesado correctamente

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí|Identificador de la sesión que ha procesado la transacción
notification | **Notification** | No |Información de notificación (Error o Warning)
↳ type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
↳ code | *String* | Sí | Código de la notificación
↳ text | *String* | Sí | Texto descriptivo de la notificación

<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp; Si se quiere actualizar la información del inventario los tags availableQuota y status son obligatorios.
</aside>

<aside class="notice">
<sup>2</sup>&nbsp;&nbsp;&nbsp; Si se quiere actualizar la información de precios y restricciones el tag mealPlan es obligatorio.
</aside>
