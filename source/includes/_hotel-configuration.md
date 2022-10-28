# HotelConfiguration

> Ejemplo petición HotelConfigurationRequest para recuperar la configuración del hotel 1234
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<HotelConfigurationRequest>
   <credentials>
      <systemCode>SFO</systemCode>
      <vendorCode>FOO</vendorCode>
      <user>BAR</user>
      <password>FOOBAR</password>
   </credentials>
   <hotelCode>1234</hotelCode>
</HotelConfigurationRequest>
````

````json
{
  "HotelConfigurationRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234"
  }
}
````

> Ejemplo respuesta HotelConfigurationResponse

````xml
<?xml version="1.0" encoding="UTF-8"?>
<HotelConfigurationResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <hotelConfig>
        <hotelCode>1234</hotelCode>
        <name>Hotetec Test</name>
        <currencyCode>EUR</currencyCode>
        <roomConfig>
            <roomCode>SGL#STD</roomCode>
            <name>Individual Estándar</name>
            <occupancy>
                <adults>1</adults>
                <children>0</children>
            </occupancy>
            <occupancy>
                <adults>1</adults>
                <children>1</children>
            </occupancy>
        </roomConfig>        
        <roomConfig>
            <roomCode>DBL#STD</roomCode>
            <name>Doble Estándar</name>
            <occupancy>
                <adults>1</adults>
                <children>0</children>
            </occupancy>
            <occupancy>
                <adults>2</adults>
                <children>0</children>
            </occupancy>
            <occupancy>
                <adults>2</adults>
                <children>1</children>
            </occupancy>
        </roomConfig>
        <mealPlanConfig>
            <mealPlanCode>RO</mealPlanCode>
            <name>Sólo alojamiento</name>
        </mealPlanConfig>
        <mealPlanConfig>
            <mealPlanCode>BB</mealPlanCode>
            <name>Alojamiento y desayuno</name>
        </mealPlanConfig>
        <mealPlanConfig>
            <mealPlanCode>HB</mealPlanCode>
            <name>Media pensión</name>
        </mealPlanConfig>
        <inventoryConfig>
            <inventoryCode>1</inventoryCode>
            <name>Inventario general</name>
        </inventoryConfig>
        <rateConfig>
            <rateCode>BASE</rateCode>
            <name>Tarifa Base</name>
            <inventoryCode>1</inventoryCode>
            <managedByPush>true</managedByPush>
            <cancelPolicyType>Variable</cancelPolicyType>
        </rateConfig>
        <rateConfig>
            <rateCode>OFENRE</rateCode>
            <name>Tarifa No Reembolsable</name>
            <inventoryCode>1</inventoryCode>
            <managedByPush>true</managedByPush>
            <rateProperty>
                <name>Destacada</name>
            </rateProperty>
            <cancelPolicyType>NonRefundable</cancelPolicyType>
        </rateConfig>        
    </hotelConfig>
</HotelConfigurationResponse>
````
````json
{
  "HotelConfigurationResponse": {
    "sessionId": "SUP#FOO#123456789",
    "hotelConfig": {
      "hotelCode": "1234",
      "name": "Hotetec Test",
      "currencyCode": "EUR",
      "roomConfig": [
        {
          "roomCode": "SGL#STD",
          "name": "Individual Estándar",
          "occupancy": [
            {
              "adults": "1",
              "children": "0"
            },
            {
              "adults": "1",
              "children": "1"
            }
          ]
        },
        {
          "roomCode": "DBL#STD",
          "name": "Doble Estándar",
          "occupancy": [
            {
              "adults": "1",
              "children": "0"
            },
            {
              "adults": "2",
              "children": "0"
            },
            {
              "adults": "2",
              "children": "1"
            }
          ]
        }
      ],
      "mealPlanConfig": [
        {
          "mealPlanCode": "RO",
          "name": "Sólo alojamiento"
        },
        {
          "mealPlanCode": "BB",
          "name": "Alojamiento y desayuno"
        },
        {
          "mealPlanCode": "HB",
          "name": "Media pensión"
        }
      ],
      "inventoryConfig": {
        "inventoryCode": "1",
        "name": "Inventario general"
      },
      "rateConfig": [
        {
          "rateCode": "BASE",
          "name": "Tarifa Base",
          "inventoryCode": "1",
          "managedByPush": "true",
          "cancelPolicyType": "Variable"
        },
        {
          "rateCode": "OFENRE",
          "name": "Tarifa No Reembolsable",
          "inventoryCode": "1",
          "managedByPush": "true",
          "rateProperty": { "name": "Destacada" },
          "cancelPolicyType": "NonRefundable"
        }
      ]
    }
  }
}
````

Mensaje utilizado para obtener la configuración del hotel. A través de este mensaje, el proveedor podrá obtener todos 
los códigos y tipología para poder gestionar el hotel vía PUSH. Típicamente, este mensaje es el que utiliza el proveedor 
para recuperar los elementos a mapear. En resumen:

- Habitaciones del hotel así como sus ocupaciones permitidas
- Regímenes alimenticios
- Tarifas del hotel, indicando las que son gestionables a traves de PUSH (managedByPush)

### HotelConfigurationRequest

Mensaje petición para recuperar la configuración de los hoteles del proveedor. 
Opcionalmente se puede filtrar por código de hotel (hotelCode). 
Si no se indica, en la respuesta aparecerán todos los hoteles que gestiona el proveedor.
 
Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
hotelCode | *Integer* | No |Código de hotel

### HotelConfigurationResponse

Mensaje respuesta que contiene la configuración de los hoteles del proveedor (modalidades, regímenes, tarifas...)

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí |Identificador de la sesión que ha procesado la transacción
hotelConfig[] | **HotelConfig** | No |Elemento que contiene la configuración del hotel
hotelCode | *Integer* | Sí | Código de hotel
name | *String* | Sí |Nombre de hotel
currencyCode | *String* | Sí | Código de divisa (Códigos ISO 4217)
roomConfig[] | **RoomConfig** | Sí | Configuración de la modalidad de hotel
↳ roomCode | *String* | Sí |Código de modalidad
↳ name | *String* | Sí | Nombre de modalidad
↳ nestedInventoryRoomCode | *String* | No | Código de la modalidad sobre la cuál anida el inventario <sup>1</sup>
↳ babiesCountInOccupancy | *Boolean* | Sí | Indica si los bebés ocupan plaza <sup>2</sup>
↳ occupancy | **Occupancy** | Sí | Ocupación permitida en la modalidad
↳↳ adults | *Integer* | Sí | Número de adultos de la ocupación
↳↳ children | *Integer* | Sí | Número de niños de la ocupación
mealPlanConfig[] | **MealPlanConfig** | Sí | Configuración de la regímenes alimenticios de hotel
↳ mealPlanCode | *String* | Sí |Código de régimen alimentício
↳ name | *String* | Sí | Nombre de régimen alimentício
inventoryConfig[] | **InventoryConfig** | Sí | Configuración de los inventarios del hotel <sup>3</sup>
↳ inventoryCode | *Integer* | Sí |Código de inventario
↳ name | *String* | Sí | Nombre de inventario
rateConfig[] | **RateConfig** | Sí | Configuración de las tarifas del hotel
↳ rateCode | *String* | Sí |Código de tarifa
↳ name | *String* | Sí | Nombre de tarifa
↳ inventoryCode | *Integer* | Sí | Inventario asociado a la tarifa
↳ managedByPush | *Boolean* | Sí | Indica si la tarifa es gestionable a través de PUSH. Si se informa false, no se podrán realizar actualizaciones sobre la misma a través del API
↳ rateProperty | **RateProperty** | No | Propiedad de la tarifa
↳↳ name | **String** | Sí | Nombre de la propiedad
↳↳ value | **String** | No | Valor de la propiedad. Ej: Propiedad Mayores de, value 55
↳ cancelPolicyType | *Enum* | Sí | Políticas de cancelación de la tarifa (Free/NonRefundable/Variable)


<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp;Generalmente no vendra informado, sólo en aquellos hoteles que trabajan con modalidades de cupo anidado. Ej: Modalidad Doble uso individual
 utiliza el inventario de la modalidad Doble estándar.
</aside>

<aside class="notice">
<sup>2</sup>&nbsp;&nbsp;&nbsp;Si los bebés ocupan plaza, contabilizarán como children en las ocupaciones permitidas en la modalidad. 
Generalmente, el valor será false.
</aside>

<aside class="notice">
<sup>3</sup>&nbsp;&nbsp;&nbsp;Por norma general, el hotel trabaja con un único inventario y todas la tarifas utilizan el mismo.
En el caso de que el hotel utilice varios, con el inventoryCode se podrá distinguir que inventario utiliza cada tarifa.
</aside>

