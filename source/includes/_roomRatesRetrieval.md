# RoomRatesRetrieval

> Ejemplo RoomRatesRetrievalRequest para recuperar la información del hotel (habitaciones y tarifas)

````json
{
    "RoomRatesRetrievalRequest": {
        "user": "userTest",
        "password": "passwordTest",
        "hotelCode": "1234"
    }
}

````

> Ejemplo respuesta RoomRatesRetrievalResponse procesada correctamente

````json
{
  "RoomRatesRetrievalResponse": {
    "hotel": [{
	
	 }]  
  }
}
````

Mensaje utilizado para consultar la información de un hotel (habitaciones y  tarifas).

### RoomRatesRetrievalRequest

Mensaje petición para consultar la información de un hotel (habitaciones y tarifas).
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
user | *String* | Sí | Nombre de Usuario
password | *String* | Si | Password
hotelCode| *String* | Si | Código de hotel

### RoomRatesRetrievalResponse

Mensaje respuesta que contiene la información del hotel publicada.

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí|Identificador de la sesión que ha procesado la transacción
roomRate[] | **RoomRate** | No | Información asociada a una combinación de tarifa y modalidad de hotel
↳ @rateCode| *String* | Sí | Código de tarifa
↳ @roomCode| *String* | Sí | Código de modalidad
↳ roomRateDate| **RomRateDate** | Sí | Información relativa a un rango de fechas
↳↳ @dateFrom| *Date* | Sí | Fecha desde (dd/MM/yyyy, rangos cerrados)
↳↳ @dateTo| *Date* | Sí | Fecha hasta (dd/MM/yyyy, rangos cerrados)
↳↳ availableQuota| *Integer* | Sí | Unidades de cupo disponible
↳↳ status| *Enum* | Sí | Estado del inventario <sup>1</sup> 
↳↳ mealPlan[]| **MealPlan** | No | Información asociada al régimen alimenticio
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
notification | **Notification** | No |Información de notificación (Error o Warning)
↳ type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
↳ code | *String* | Sí | Código de la notificación
↳ text | *String* | Sí | Texto descriptivo de la notificación

