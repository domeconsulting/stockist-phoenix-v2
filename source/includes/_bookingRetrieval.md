# BookingRetrieval

> Ejemplo BookingRetrievalRequest para recuperar una reserva en particular por referencia (localizador)

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalRequest>
	<user>BAR</user>
	<password>FOOBAR</password>
	<hotelCode>ABC1234</hotelCode>
	<reference>AAABBB123456ZZZZ</reference>
</BookingRetrievalRequest>
````

> Ejemplo BookingRetrievalRequest para para recuperar las reservas de un hotel en un determinado rango de fechas (creadas, canceladas o modificadas)

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalRequest>
	<user>BAR</user>
	<password>FOOBAR</password>
	<hotelCode>ABC1234</hotelCode>
    <dateFrom>10/03/2017 14:30</dateFrom>
    <dateTo>10/03/2017 15:00</dateTo>
</BookingRetrievalRequest>
````

> Ejemplo respuesta BookingRetrievalResponse procesada correctamente
La reserva recuperada contiene dos habitaciones: 1 doble 

````xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<BookingRetrievalResponse>
	<booking>
		<reference>AAAA123456789CCCC</reference>
		<clientReference>ZZZZ99998888XXXX</clientReference>
		<creationDate>01/01/2022 12:00:00</creationDate>
		<bookingRoom>
			<dateFrom>05/02/2022</dateFrom>
			<dateTo>08/02/2022</dateTo>
			<hotelCode>1234</hotelCode>
			<rateCode>Test Rate 001</rateCode>
			<roomCode>DBL#STD</roomCode>
			<mealPlanCode>RO</mealPlanCode>
			<amount>300.0</amount>
			<currencyCode>EUR</currencyCode>
			<status>Confirmed</status>
			<guests>
				<guest>
					<id>1</id>
					<birthDate>01/01/1982</birthDate>
					<name>John</name>
					<surname>Doe</surname>
					<lastname>Smith</lastname>
				</guest>
				<guest>
					<id>2</id>
					<birthDate>01/01/1984</birthDate>
					<name>Diana</name>
					<surname>Doe</surname>
					<lastname>Smith</lastname>
				</guest>
			</guests>
			<remarks>
				<remark>
					<language>ES</language>
					<text>Habitacion bonita</text>
					<source>CLIENT</source>
					<to>VENDOR</to>
				</remark>
			</remarks>
			<supplements>
				<supplement>
					<description>Dinner VIP</description>
					<dateFrom>05/02/2022</dateFrom>
					<dateTo>08/02/2022</dateTo>
					<status>Confirmed</status>
					<amount>25.0</amount>
					<mandatory>true</mandatory>
					<referenceGuestId>1</referenceGuestId>
					<referenceGuestId>2</referenceGuestId>
				</supplement>
			</supplements>
			<cancellationDetail>
				<reason>Test cancel</reason>
				<description>description cancellation reason</description>
				<dateTimeCancellation>15/01/2022 15:00:00</dateTimeCancellation>
				<amount>50.0</amount>
			</cancellationDetail>
			<priceBreakDown>
				<byDayBreakDown>
					<dayBreakDown>
						<day>05/02/2022</day>
						<amount>100.0</amount>
					</dayBreakDown>
					<dayBreakDown>
						<day>06/02/2022</day>
						<amount>100.0</amount>
					</dayBreakDown>
					<dayBreakDown>
						<day>07/02/2022</day>
						<amount>100.0</amount>
					</dayBreakDown>
				</byDayBreakDown>
				<byGuestBreakDown>
					<guestBreakDown>
						<referenceGuestId>1</referenceGuestId>
						<amount>150.0</amount>
					</guestBreakDown>
					<guestBreakDown>
						<referenceGuestId>2</referenceGuestId>
						<amount>150.0</amount>
					</guestBreakDown>
				</byGuestBreakDown>
			</priceBreakDown>
		</bookingRoom>
		<contactPerson>
			<nationality>ES</nationality>
			<birthDate>01/10/1975</birthDate>
			<name>Contact</name>
			<surname>Person Surname</surname>
			<email>test@test.com</email>
			<phoneNumber>666123456</phoneNumber>
			<address>
				<addressLine>Carrer sense nom, 14</addressLine>
				<locationName>Palma</locationName>
				<postalCode>07500</postalCode>
				<country>ES</country>
			</address>
			<documentType>Passport</documentType>
			<documentNumber>123456789</documentNumber>
		</contactPerson>
		<payment>
			<status/>
			<amount>300.0</amount>
			<card>
				<holder>TEST TEST TEST</holder>
				<number>4111111111111111</number>
				<series>123</series>
				<expiryDate>01/04/2025</expiryDate>
			</card>
			<type>Card</type>
		</payment>
		<remarks>
			<remark>
				<language>ES</language>
				<text>Nota Reserva</text>
				<source>CLIENT</source>
				<to>VENDOR</to>
			</remark>
		</remarks>
		<totalAmount>300.0</totalAmount>
		<supplements>
			<supplement>
				<description>Parking</description>
				<dateFrom>05/02/2022</dateFrom>
				<dateTo>08/02/2022</dateTo>
				<status>Confirmed</status>
				<amount>75.0</amount>
				<mandatory>true</mandatory>
			</supplement>
		</supplements>
	</booking>
</BookingRetrievalResponse>

````

Mensaje utilizado para recuperación de reservas. Se puede recuperar una reserva en particular (filtrando por reference),
o bien las reservas de un hotel creadas, canceladas o modificadas dentro de un rango de fechas.

### BookingRetrievalRequest

Mensaje petición de recuperación de reservas
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
user | *String* | Sí | Nombre de Usuario
password | *String* | Si | Password
hotelCode| *String* | Si | Código de hotel
dateFrom | *DateTime* | No<sup>1</sup> | Fecha desde. Devolverá todas las reservas que se hayan creado, cancelado o modificado a partir de esta fecha (dd/MM/yyyy HH:mm)
dateTo | *DateTime* | No<sup>1</sup> | Fecha hasta. Devolverá todas las reservas que se hayan creado, cancelado o modificado hasta esta fecha (dd/MM/yyyy HH:mm)
reference | *String* | No<sup>1</sup> | Localizador de la reserva

<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp;<b>Deberá informarse o el localizador o el rango de fechas.</b>
</aside>

### BookingRetrievalResponse

Mensaje respuesta de recuperación de reservas

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
booking[] | **Booking** | No | Información de una reserva de hotel
↳ reference| *String* | Sí | Localizador de la reserva
↳ clientReference| *String* | No | Localizador de la agencia final
↳ creationDate| *DateTime* | Sí | Fecha de creación de la reserva (dd/MM/yyyy HH:mm)
↳ bookingRoom[]| **BookingRoom** | Sí | Información de habitación de hotel reservada
↳↳ dateFrom| *Date* | Sí | Fecha de entrada (dd/MM/yyyy)
↳↳ dateTo| *Date* | Sí | Fecha de salida (dd/MM/yyyy)
↳↳ hotelCode| *String* | Sí | Código de hotel
↳↳ rateCode| *String* | Sí | Código de la tarifa reservada
↳↳ roomCode| *String* | Sí | Código de habitación
↳↳ mealPlanCode| *String* | Sí | Código de régimen alimenticio
↳↳ amount| *Double* | Sí | Importe de la habitación reservada (#.##)
↳↳ currencyCode| *String* | Sí | Código de divisa (Códigos ISO 4217)
↳↳ status| *Enum* | Sí | Estado de la reserva (Confirmed, Cancelled, OnRequest)
↳↳ guests| **Guests** | Sí | Informacion de los huespedes de la reserva
↳↳↳ guest[]| **Guest** | Sí | Informacion de un huesped de la reserva
↳↳↳↳ @id| *Integer* | Sí | Identificador del huesped. Debe ser unico para toda la reserva.
↳↳↳↳ birthDate| *Date* | Sí | Fecha de nacimiento (dd/MM/yyyy)
↳↳↳↳ name| *String* | Sí | Nombre del huesped.
↳↳↳↳ surname| *String* | Sí | Apellido del huesped.
↳↳↳↳ lastname| *String* | No | Segundo apellido del huesped.
↳↳ remarks| **Remarks** | No | Notas de la habitacion
↳↳↳ remark[]| **Remarks** | Si | Informacion relativa a una nota
↳↳↳↳ language| *String* | Si | Idioma del texto
↳↳↳↳ text| *String* | Si | Texto de la nota
↳↳↳↳ source| *String* | Si | Origen / Creador de la nota 
↳↳↳↳ to| *String* | Si | Destinatario de la nota 
↳↳ supplements| **Supplements** | No | Suplementos de la habitacion
↳↳↳ supplement[]| **Supplement** | Si | Informacion relativa a un suplemento
↳↳↳↳ description| *String* | Si | Nombre / Descripcion del suplemento
↳↳↳↳ dateFrom| *Date* | Si | Fecha de inicio del suplemento
↳↳↳↳ dateTo| *Date* | Si | Fecha de fin del suplemento
↳↳↳↳ status| *String* | Si | Estado del suplemento(Confirmed, Cancelled)
↳↳↳↳ amount| *Double* | Si | Importe del suplemento (#.##)
↳↳↳↳ mandatory| *Boolean* | Si | Indica si es obligatorio el suplemento
↳↳↳↳ referenceGuestId[]| *Integer* | No | Indica los ids de los huespedes afectados por el suplemento
↳↳ cancellationDetail| **CancellationDetail** | No | Informacion de los detalles de la cancelacion de la habitacion
↳↳↳ reason| *String* | Si | Razon del motivo de la cancelacion de la reserva
↳↳↳ description| *String* | No | Descripcion de la cancelacion de la reserva
↳↳↳ dateTimeCancellation| *DateTime* | Si | Fecha y hora de la cancelación (dd/MM/yyyy HH:mm)
↳↳↳ amount| *Double* | Si | Importe de la cancelación (#.##)
↳↳ priceBreakDown| **PriceBreakDown** | No | Desglose de precios de la reserva
↳↳↳ byDayBreakDown| **ByDayBreakDown** | No | Desglose de precios de la reserva
↳↳↳↳ dayBreakDown[]| **DayBreakDown** | Si | Desglose de precios de la reserva por dia
↳↳↳↳↳ day| *Date* | Si | dia del desglose de precios por dia
↳↳↳↳↳ amount| *Double* | Si | Importe del desglose de precios por dia(#.##)
↳↳↳ byGuestBreakDown| **ByGuestBreakDown** | No | Desglose de precios de la reserva por pasajero
↳↳↳↳ guestBreakDown[]| **GuestBreakDown** | Si | Desglose de precios de la reserva por pasajero
↳↳↳↳↳ referenceGuestId| *Integer* | Si | Identificador del huesped 
↳↳↳↳↳ amount| *Double* | Si | Importe del desglose de precios por huesped (#.##)
↳ contactPerson| **ContactPerson** | Sí | Información de la persona de contacto de la reserva
↳↳ nationality| *String* | No | Nacionalidad de la persona de contacto (ISO-3166)
↳↳ birthDate| *Date* | No | Fecha de nacimiento de la persona de contacto (dd/MM/yyyy)
↳↳ name| *String* | Si | Nombre de la persona de contacto
↳↳ surname| *String* | Si | Apellido de la persona de contacto
↳↳ email| *String* | Si | Email de la persona de contacto
↳↳ phoneNumber| *String* | No | Telefono de la persona de contacto
↳↳ address| **Address** | No | Informacion de la direccion de la persona de contacto
↳↳↳ addressLine| *String* | Si | Direccion de la persona de contacto
↳↳↳ locationName| *String* | No | Localidad de la direccion de la persona de contacto
↳↳↳ postalCode| *String* | No | Código postal de la direccion de la persona de contacto
↳↳↳ country| *String* | No | Pais de la direccion de la persona de contacto(ISO-3166)
↳↳ documentType| *String* | Si | Tipo de documento de la persona de contacto
↳↳ documentNumber| *String* | Si | Numero de documento de la persona de contacto
↳ payment| **Payment** | No | Información relativa al pago de la reserva
↳↳ status| *String* | Si | Estado del pago de la reserva(Confirmed, Pending)
↳↳ amount| *Double* | Si | Importe del pago de la reserva
↳↳ card| **Card** | Si | Informacion de la tarjeta del pago de la reserva
↳↳↳ holder| *String* | Si | Titular de la tarjeta de pago
↳↳↳ number| *String* | Si | Numero de la tarjeta de pago
↳↳↳ series| *String* | Si | CVC de la tarjeta de pago
↳↳↳ expiryDate| *Date* | Si | Fecha de caducidad de la tarjeta de pago(dd/MM/yyyy)
↳↳ type| *String* | No | Tipo de pago de la reserva
↳ remarks| **Remarks** | No | Notas de la reserva
↳↳ remark[]| **Remarks** | Si | Informacion relativa a una nota 
↳↳↳ language| *String* | Si | Idioma del texto
↳↳↳ text| *String* | Si | Texto de la nota
↳↳↳ source| *String* | Si | Origen / Creador de la nota 
↳↳↳ to| *String* | Si | Destinatario de la nota 
↳ totalAmount| *Double* | Si | Importe total de la reserva
↳ supplements| **Supplements** | No | Suplementos de la reserva
↳↳ supplement[]| **Supplement** | Si | Informacion relativa a un suplemento de la reserva
↳↳↳ description| *String* | Si | Nombre / Descripcion del suplemento
↳↳↳ dateFrom| *Date* | Si | Fecha de inicio del suplemento
↳↳↳ dateTo| *Date* | Si | Fecha de fin del suplemento
↳↳↳ status| *String* | Si | Estado del suplemento(Confirmed, Cancelled)
↳↳↳ amount| *Double* | Si | Importe del suplemento (#.##)
↳↳↳ mandatory| *Boolean* | Si | Indica si es obligatorio el suplemento
↳↳↳ referenceGuestId[]| *Integer* | No | Indica los ids de los huespedes afectados por el suplemento
notification | **Notification** | No |Información de notificación (Error o Warning)
↳ type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
↳ code | *String* | Sí | Código de la notificación
↳ text | *String* | Sí | Texto descriptivo de la notificación


<aside class="notice">
TODO aclaraciones de la reserva
<sup>1</sup>&nbsp;&nbsp;&nbsp; Ejemplos: 
<ul>
   <li>Pago con tarjeta de garantía, pendiente de cobro, a cobrar en establecimiento. modality: Establishment, type: WarrantyCard, status: Pending</li>
   <li>Pago inmediato, cobrado a traves de una pasarela de pago externa. modality: Inmediate, type: ExternalManaged, status: Ok</li>
   <li>Pago a crédito, acordado con la agencia. modality: ExternManagement, type: Credit, status: Inapplicable</li>
</ul>
</aside>