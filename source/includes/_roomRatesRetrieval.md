# RoomRatesRetrieval

> Ejemplo RoomRatesRetrievalRequest para recuperar la información del hotel (habitaciones y tarifas)

````xml
<RoomRatesRetrievalRequest>
	<user>userTest</user>
	<password>passwordTest</password>
	<hotelCode>1234</hotelCode>    
</RoomRatesRetrievalRequest>
````

> Ejemplo respuesta RoomRatesRetrievalResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<RoomRatesRetrievalResponse>
	<hotel>
		<code>1234</code>
		<name>Hotel Test</name>
		<rooms>
			<room>
				<code>DBLA2</code>
				<name>Double Standard</name>
				<occupations>
					<occupation>
						<adults>2</adults>
						<children>0</children>
						<infant>0</infant>
					</occupation>
					<occupation>
						<adults>2</adults>
						<children>1</children>
						<infant>0</infant>
					</occupation>
				</occupations>
				<rates>
					<rate>
						<code>NRE</code>
						<name>No refundable rate</name>
						<mealplans>
							<mealplan>
								<code>RO</code>
								<name>Room Only</name>
							</mealplan>
							<mealplan>
								<code>AI</code>
								<name>All Inclusive</name>
							</mealplan>
						</mealplans>
					</rate>
				</rates>
			</room>
		</rooms>
	</hotel>
</RoomRatesRetrievalResponse>

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
hotel| **Hotel** | No| Información relativa al hotel 
↳ @code| *String* | Sí | Código del hotel
↳ @name| *String* | NO | Nombre del hotel
↳ @rooms| **Rooms** | Si | Informacion de las habitaciones
↳↳ room[]| **Room** | Sí | Información relativa a una habitacion del hotel
↳↳↳ @code| String | Sí | Código de la habitacion 
↳↳↳ @name| String | No | Nombre de la habitacion
↳↳↳ occupations| **Occupations** | Sí | Informacion de las ocupaciones de la habitacion
↳↳↳↳ occupation[]| **Occupation** | Sí | Informacion relativa a una ocupacion de la habitacion
↳↳↳↳↳ @adults| *Integer* | Sí | Numero de adultos de la ocupacion
↳↳↳↳↳ @children| *Integer* | No | Numero de niños de la ocupacion
↳↳↳↳↳ @infant| *Integer* | No | Numero de bebés de la ocupacion
↳↳↳ rates| **Rates** | Sí | Información relativa a las tarifas de la habitacion
↳↳↳↳ rate[]| **Rate** | Sí | Información relativa a una tarifa de la habitacion
↳↳↳↳↳ code| *String* | Sí | Código de la tarifa
↳↳↳↳↳ name| *String* | No | Nombre de la tarifa
↳↳↳↳ mealplans| **Mealplans** | Sí | Informacion relativa a los regimenes alimenticios de la tarifa
↳↳↳↳↳ mealplan[]| **Mealplan** | Sí | Informacion relativa a un regimen alimenticio de la tarifa
↳↳↳↳↳↳ code| *String* | Sí | Código del regimen alimenticio
↳↳↳↳↳↳ name| *String* | No | Nombre del regimen alimenticio
notification | **Notification** | No |Información de notificación (Error o Warning)
↳ type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
↳ code | *String* | Sí | Código de la notificación
↳ text | *String* | Sí | Texto descriptivo de la notificación

