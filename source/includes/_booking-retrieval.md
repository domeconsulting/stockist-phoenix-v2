# BookingRetrieval

> Ejemplo BookingRetrievalRequest para recuperar una reserva en particular
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>   
    <hotelCode>1234</hotelCode>
    <reference>EPL10032017140800-SALE</reference>
</BookingRetrievalRequest>
````

````json
{
  "BookingRetrievalRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "reference": "EPL10032017140800-SALE"
  }
}
````

> Ejemplo BookingRetrievalRequest para para recuperar las reservas de un hotel en un determinado rango de fechas (creadas, canceladas o modificadas)
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>   
    <hotelCode>1234</hotelCode>
    <dateFrom>10/03/2017 14:30</dateFrom>
    <dateTo>10/03/2017 15:00</dateTo>
</BookingRetrievalRequest>
````

````json
{
  "BookingRetrievalRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "dateFrom": "10/03/2017 14:30",
    "dateTo": "10/03/2017 15:00"
  }
}
````

> Ejemplo respuesta BookingRetrievalResponse procesada correctamente
La reserva recuperada contiene dos habitaciones: 1 doble + 1 individual

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <booking>
        <reference>EPL10032017140800-SALE</reference>
        <creationDate>10/03/2017 14:15</creationDate>
        <checkIn>15/04/2017</checkIn>
        <checkOut>18/04/2017</checkOut>
        <status>Confirmed</status>
        <amount>550.00</amount>
        <bookingClient>
            <clientCode>EPL</clientCode>
            <clientName>Europlayas</clientName>
            <clientReference>AA45645D55</clientReference>
        </bookingClient>
        <endCustomer>
            <name>Elena Ballester</name>
            <mail>elena_ballester1234@mail.com</mail>
            <phone>003466667788</phone>
        </endCustomer>
	<commission>
    	    <serviceCommission>
                <serviceId>1</serviceId>
                <commissionAmount>0</commissionAmount>
                <commissionPercentage>0</commissionPercentage>
            </serviceCommission>
            <serviceCommission>
                <serviceId>2</serviceId>
                <commissionAmount>0</commissionAmount>
                <commissionPercentage>0</commissionPercentage>
            </serviceCommission>
        </commission>
        <hotelCode>1234</hotelCode>
        <bookingRoom id="1">
            <checkIn>15/04/2017</checkIn>
            <checkOut>17/04/2017</checkOut>
            <status>Confirmed</status>
            <roomCode>DBL#STD</roomCode>
            <mealPlanCode>BB</mealPlanCode>
            <amount>350.00</amount>
            <roomRateDay>
                <day>15/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>116.67</amount>
            </roomRateDay>
            <roomRateDay>
                <day>16/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>116.67</amount>
            </roomRateDay>
            <roomRateDay>
                <day>17/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>116.67</amount>
            </roomRateDay>
            <guest id="1">
                <type>Adult</type>
		<name>Juan Ballester</name>
                <amount>175.00</amount>
            </guest>
            <guest id="2">
                <type>Adult</type>
		<name>Elena Ballester</name>
                <amount>175.00</amount>
            </guest>
        </bookingRoom>
        <bookingRoom id="2">
            <checkIn>15/04/2017</checkIn>
            <checkOut>17/04/2017</checkOut>
            <status>Confirmed</status>
            <roomCode>SGL#STD</roomCode>
            <mealPlanCode>BB</mealPlanCode>
            <amount>150.00</amount>
            <roomRateDay>
                <day>15/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>50.00</amount>
            </roomRateDay>
            <roomRateDay>
                <day>16/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>50.00</amount>
            </roomRateDay>
            <roomRateDay>
                <day>17/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>50.00</amount>
            </roomRateDay>
            <guest id="3">
                <type>Adult</type>
		<name>Elena Ballester</name>
		<gender>Female</gender>
                <amount>100.00</amount>
            </guest>
            <guest id="4">
                <type>Child</type>
		<name>Elena Ballester</name>
		<gender>Female</gender>
                <amount>50.00</amount>
            </guest>
        </bookingRoom>
        <bookingSupplement>
            <code>PKG</code>
            <code>Parking</code>
            <description>Suplemento Parking toda la estancia</description>
            <checkIn>15/04/2017</checkIn>
            <checkOut>17/04/2017</checkOut>
            <amount>50.00</amount>
        </bookingSupplement>
        <remark>
            <code>GENERAL</code>
            <from>Hotel</from>
            <to>Client</to>
            <text>Piscina cerrada hasta el 15/04/2017</text>
        </remark>
        <remark>
            <code>GENERAL</code>
            <from>Client</from>
            <to>Hotel</to>
            <text>Por favor, habitaciones no fumadores</text>
        </remark>
        <bookingPayment>
            <modality>Establishment</modality>
            <type>PrepaidCard</type>
	    <otaType>PC</otaType>
	    <description>Tarjeta de prepago</description>
            <status>Pending</status>
        </bookingPayment>
        <paymentCardDetail>
            <holder>Elena Ballester</holder>
            <number>4111111111111111</number>
            <expiryDate>01/01/2020</expiryDate>
            <securityCode>123</securityCode>
        </paymentCardDetail>
		<paymentDetail>
			<action>Charge</action>
			<paymentStatus>Ok</paymentStatus>
			<type>ExternalManaged</type>
			<date>24/01/2019 17:18</date>
			<amount>2635.663</amount>
			<externalManagedDetail>
			<externalSystemCode>TARJETA VIRTUAL</externalSystemCode>
			<externalReference>5227</externalReference>
			<status>Ok</status>
			</externalManagedDetail>
		</paymentDetail>
		<paymentDetail>
			<action>Charge</action>
			<paymentStatus>Pending</paymentStatus>
			<type>PrepaidCard</type>
			<otaType>PC</otaType>
			<date>23/07/2019 09:42</date>
			<amount>2635.66</amount>
			<prepaidCardDetail>
				<status>Pending</status>
				<card>
					<cardTypeCode>Visa</cardTypeCode>
					<holder>Elena Ballester</holder>
					<number>4111111111111111</number>
					<expiryDate>01/01/2020</expiryDate>
					<securityCode>123</securityCode>
				</card>
			</prepaidCardDetail>
		</paymentDetail>
    </booking>
</BookingRetrievalResponse>
````

````json
{
  "BookingRetrievalResponse": {
    "sessionId": "SUP#FOO#123456789",
    "booking": {
      "reference": "EPL10032017140800-SALE",
      "creationDate": "10/03/2017 14:15",
      "checkIn": "15/04/2017",
      "checkOut": "18/04/2017",
      "status": "Confirmed",
      "amount": "550.00",
      "bookingClient": {
        "clientCode": "EPL",
        "clientName": "Europlayas",
        "clientReference": "AA45645D55"
      },
      "endCustomer": {
        "name": "Elena Ballester",
        "mail": "elena_ballester1234@mail.com",
        "phone": "003466667788"
      },
      "hotelCode": "1234",
      "bookingRoom": [
        {
          "id": "1",
          "checkIn": "15/04/2017",
          "checkOut": "17/04/2017",
          "status": "Confirmed",
          "roomCode": "DBL#STD",
          "mealPlanCode": "BB",
          "amount": "350.00",
          "roomRateDay": [
            {
              "day": "15/04/2017",
              "rateCode": "BASE",
              "amount": "116.67"
            },
            {
              "day": "16/04/2017",
              "rateCode": "BASE",
              "amount": "116.67"
            },
            {
              "day": "17/04/2017",
              "rateCode": "BASE",
              "amount": "116.67"
            }
          ],
          "guest": [
            {
              "id": "1",
	      "name": "Juan Ballester",
              "type": "Adult",
              "amount": "175.00"
            },
            {
              "id": "2",
	      "name": "Elena Ballester",
              "type": "Adult",
              "amount": "175.00"
            }
          ]
        },
        {
          "id": "2",
          "checkIn": "15/04/2017",
          "checkOut": "17/04/2017",
          "status": "Confirmed",
          "roomCode": "SGL#STD",
          "mealPlanCode": "BB",
          "amount": "150.00",
          "roomRateDay": [
            {
              "day": "15/04/2017",
              "rateCode": "BASE",
              "amount": "50.00"
            },
            {
              "day": "16/04/2017",
              "rateCode": "BASE",
              "amount": "50.00"
            },
            {
              "day": "17/04/2017",
              "rateCode": "BASE",
              "amount": "50.00"
            }
          ],
          "guest": [
            {
              "id": "3",
	      "name": "Elena Ballester",
              "type": "Adult",
	      "gender": "Female",
              "amount": "100.00"
            },
            {
              "id": "4",
	      "name": "Elena Ballester",
	      "gender": "Female",
              "type": "Child",
              "amount": "50.00"
            }
          ]
        }
      ],
      "bookingSupplement": {
        "code": [
          "PKG",
          "Parking"
        ],
        "description": "Suplemento Parking toda la estancia",
        "checkIn": "15/04/2017",
        "checkOut": "17/04/2017",
        "amount": "50.00"
      },
      "remark": [
        {
          "code": "GENERAL",
          "from": "Hotel",
          "to": "Client",
          "text": "Piscina cerrada hasta el 15/04/2017"
        },
        {
          "code": "GENERAL",
          "from": "Client",
          "to": "Hotel",
          "text": "Por favor, habitaciones no fumadores"
        }
      ],            
      "bookingPayment": {
        "modality": "Establishment",
        "type": "WarrantyCard",
	"otaType": "PC",
	"description": "Tarjeta de garantía",
        "status": "Pending"
      },
      "paymentCardDetail": {
        "holder": "Elena Ballester",
        "number": "4111111111111111",
        "expiryDate": "01/01/2020",
        "securityCode": "123"
      }
    }
  }
}
````

Mensaje utilizado para recuperación de reservas. Se puede recuperar una reserva en particular (filtrando por reference),
o bien las reservas de un hotel creadas, canceladas o modificadas dentro de un rango de fechas.

### BookingRetrievalRequest

Mensaje petición de recuperación de reservas
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
reference | *String* | No<sup>1</sup> | Localizador de la reserva
hotelCode | *Integer* | Sí | Código de hotel
dateFrom | *DateTime* | No<sup>1</sup> | Fecha desde. Devolverá todas las reservas que se hayan creado, cancelado o modificado a partir de esta fecha (dd/MM/yyy HH:mm)
dateTo | *DateTime* | No<sup>1</sup> | Fecha hasta. Devolverá todas las reservas que se hayan creado, cancelado o modificado hasta esta fecha (dd/MM/yyy HH:mm)
notificationStatus | *Enum* | No<sup>1</sup> | Filtro por estado de notificación de reserva (Delivered: Notificada / UnDelivered: No notificada) No<sup>2</sup>

<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp;Si no se informa localizador de la reserva (reference), es obligatorio filtrar por fechas y/o estado de notificación (dateFrom/dateTo y/o notificationStatus)
</aside>

<aside class="notice">
<sup>2</sup>&nbsp;&nbsp;&nbsp;Si no se informa, se devolverán todas las reservas sea cual sea su estado. Una reserva se marca como notificada cuando se entrega vía PUSH o bien se devuelve en alguna respuesta BookingRetrievalResponse.
</aside>

### BookingRetrievalResponse

Mensaje respuesta de recuperación de reservas

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí|Identificador de la sesión que ha procesado la transacción
booking[] | **Booking** | No | Información de una reserva de hotel
↳ reference| *String* | Sí | Localizador de la reserva
↳ creationDate| *DateTime* | Sí | Fecha de creación de la reserva (dd/MM/yyy HH:mm)
↳ modificationDate| *DateTime* | No | Fecha de creación de la reserva (dd/MM/yyyy HH:mm). Sólo viene informado cuando es una modificación de reserva
↳ cancellationDate| *DateTime* | No | Fecha de cancelación de la reserva (dd/MM/yyyy HH:mm). Sólo viene informado cuando es una cancelación de reserva
↳ country| *String* | No | Código del país de origen de la reserva (2 letter ISO 3166). Sólo vendrá informado en la reservas propias de Hotetec
↳ checkIn| *Date* | Sí | Fecha de entrada (dd/MM/yyy)
↳ checkOut| *Date* | Sí | Fecha de salida (dd/MM/yyy)
↳ status| *Enum* | Sí | Estado de la reserva (Confirmed, Cancelled, OnRequest)
↳ amount| *Double* | Sí | Importe total de la reserva (#.##)
↳ bookingClient| **BookingClient** | Sí | Información del cliente que ha realizado la reserva, refiriéndose a la agencia (Ej: Logitravel), OTA (Ej: Booking.com), o el propio hotel
↳↳ clientCode| *String* | Sí | Código de cliente
↳↳ clientName| *String* | Sí | Nombre de cliente
↳↳ fiscalClientName| *String* | No | Nombre fiscal referente al cliente de la reserva
↳↳ addressClient| *String* | No | Dirección física de la empresa cliente
↳↳ postalClientCode| *String* | No | Código postal de la empresa cliente
↳↳ countryClient| *String* | No | País de la empresa cliente
↳↳ cifClient| *String* | No | Número CIF de la empresa cliente
↳↳ emailClient| *String* | No | Correo electrónico de la empresa cliente
↳↳ clientReference| *String* | No | Referencia de la reserva del cliente (habitualmente su localizador)
↳ endCustomer| **EndCustomer** | Sí | Información del cliente final de la reserva
↳↳ name| *String* | Sí | Nombre del cliente final
↳↳ birthDate| *Date* | No | Fecha de nacimiento (dd/MM/yyy)
↳↳ mail| *String* | No | Email del cliente final
↳↳ phone| *String* | No | Teléfono de contacto del cliente final
↳↳ nationality| *String* | No | Nacionadlidad (2 letter ISO 3166)
↳↳ document| **Document** | No | Información referente al documento de identificación de la persona de contacto
↳↳↳ typeDocument| *String* | No | Tipo de documento (DNI, NIE, Passport o IdentityCard)
↳↳↳ numberDocument| *String* | No | Número de documento
↳ commision| **Commission** | No | Información sobre las comisiones aplicadas en la reserva
↳↳ serviceCommission[]| *ServiceCommission* | No | Información específica sobre un servicio reservado
↳↳↳ serviceId| *Integer* | Sí | Identificador que identifica la habitación reservada
↳↳↳ commissionAmount| *Double* | No| Importe de la comisión aplicada
↳↳↳ commissionPercentage| *Double* | No | Porcentage de la comisión aplicada
↳ hotelCode| *Integer* | Sí | Código de hotel
↳ currencyCode| *String* | Sí | Código de divisa (Códigos ISO 4217)
↳ bookingRoom[]| **BookingRoom** | Sí | Información de habitación de hotel reservada
↳↳ checkIn| *Date* | Sí | Fecha de entrada (dd/MM/yyy)
↳↳ checkOut| *Date* | Sí | Fecha de salida (dd/MM/yyy)
↳↳ status| *Enum* | Sí | Estado de la reserva (Confirmed, Cancelled, OnRequest)
↳↳ roomCode| *String* | Sí | Código de habitación
↳↳ mealPlanCode| *String* | Sí | Código de régimen alimenticio
↳↳ amount| *Double* | Sí | Importe de la habitación reservada (#.##)
↳↳ totalRoomAmount| *Double* | No | Coste de la habitación: Precio Hab x Noches + Suplementos Obligatorios (#.##)
↳↳ commissionRoomAmount| *Double* | No | Comisión de la habitación: Coste de la habitación * Porcentaje comisión (#.##)
↳↳ netRoomAmount| *Double* | No | Coste neto de la habitación: Coste de la habitación - Comisión habitación (#.##)
↳↳ amountRoomToInvoice| *Double* | No | Coste a facturar de la habitación: Amount - porcentaje de comisión (#.##)
↳↳ roomRateDay[]| **RoomRateDay** | Sí | Desglose de reserva por día, informando la tarifa y precio correspondiente a cada día de la estancia
↳↳↳ day| *Date* | Sí | Día de la estancia (dd/MM/yyy)
↳↳↳ rateCode| *String* | No | Código de tarifa
↳↳↳ amount| *String* | Sí | Importe del día
↳↳ guest[]| **Guest** | Sí | Pasajero de la reserva
↳↳↳ @id| *Integer* | Sí | Identificador del pasajero
↳↳↳ name| *String* | Sí | Nombre del pasajero. Si el nombre no ha sido informado en la reserva, se substituirá por el nombre de la persona de contacto
↳↳↳ gender| *String* | No | Género del pasajero ('Male': Hombre, 'Female': Mujer y 'Undefined': Indefinido). 
↳↳↳ type| *Enum* | Sí | Tipo (Adult, Child, Baby)
↳↳↳ amount| *Double* | Sí | Importe correspondiente al pasajero
↳↳↳ birthDate| *Date* | No | Fecha de nacimiento
↳↳↳ nationality[]| *String* | No | Nacionalidad del huésped. Se incorpora el código ISO-3166. Ejemplo: <nationality>España (ES)</nationality>.
↳↳↳ document[]| *Document* | No | Información relativa a los documentos aportados por el huésped
↳↳↳↳ typeDocument| *String* | No | Tipo del documento aportado ('D': Dni, 'E': Nie y 'P':Pasaporte)
↳↳↳↳ numberDocument| *String* | No | Número del documento aportado
↳↳↳↳ expeditionDate| *Date* | No | Fecha de expedición del documento (dd/MM/yyyy)
↳↳↳↳ expiryDocument| *Date* | No | Fecha de caducidad del documento (dd/MM/yyyy)
↳↳↳ contact[]| *ContactAddress* | No | Información relativa a los datos de contacto aportados por el huésped
↳↳↳↳ phone| *String* | No | Teléfono aportado por el huésped
↳↳↳↳ email| *String* | No | Email aportado por el huésped
↳↳↳↳ addressText| *String* | No | Dirección aportada por el huésped
↳↳↳↳ postalCode| *String* | No | Código postal
↳↳ cancellationData| **CancellationData** | No| Gastos de cancelación de la habitación
↳↳↳ cancelPenaltyPolicy[]| *CancelPenaltyPolicy* | Sí | Gasto de cancelación aplicable a partir de una fecha de cancelación
↳↳↳↳ @id| *Integer* | Sí | Identificador del gasto de cancelación
↳↳↳↳ date| *Calendar* | Sí | Elemento que contiene la fecha a partir de la cual se aplican los gastos de cancelación
↳↳↳↳ timeRelevant| *Boolean* | Sí | Elemento que indica si las horas en la fecha de cancelación son relevantes o se debe tomar sólo la fecha como dato significativo
↳↳↳↳ amount| *Double* | Sí | Importe que se aplicará al cancelar la habitación
↳↳↳↳ description| *String* | No | Descripción de los gastos de cancelación
↳ bookingSupplement[]| **BookingSupplement** | No | Información de suplemento reservado
↳↳ code| *String* | Sí | Código del suplemento opcional reservado
↳↳ name| *String* | Sí | Nombre del suplemento opcional reservado
↳↳ typeSupplement| *String* | Sí | Indica el tipo de suplemento que tratamos (Mandatory / Optional / SalePolicy)
↳↳ internalName| *String* | No | Nombre interno de la política comercial (suplementos del tipo SP) aplicada en la reserva.
↳↳ description| *String* | No | Descripción detallada del suplemento opcional reservado
↳↳ checkIn| *Date* | No | Fecha de inicio del suplemento (dd/MM/yyy)
↳↳ checkOut| *Date* | No | Fecha de fin del suplemento (dd/MM/yyy)
↳↳ bookingRoomId| *Integer* | No | Identificador de la habitación reservada, si el suplemento referencia a una habitación en concreto
↳↳ guestId[]| *Integer* | No | Identificador del pasajero al que se hace referencia, si el suplemento referencia a un pasajero/os en concreto
↳↳ amount| *Double* | Sí | Importe total del suplemento opcional reservado
↳↳ commissionSupplementAmount| *Double* | No | Comisión del suplemento (#.##)
↳↳ netSupplementAmount| *Double* | No | Coste neto del suplemento: Valor total del Suplemento -  Importe de Comisión del suplemento (#.##)
↳↳ promotionalCode[]| *String* | No | Indica los códigos aplicados en el suplemento en cuestión
↳↳ mandatory| *Boolean* | Sí | Indica si el suplemento es obligatorio (true) o opcional (false)
↳↳ detail| **SupplementDetail** | No | Indica los detalles del suplemento.
↳↳↳ shuttleDetail| **SupplementShuttleDetail** | No | Indica los detalles de transporte (siempre y cuando el suplemento sea de tipo TRF)
↳↳↳↳ mailTransferProvider| *String* | No | Indica el email del proveedor del transfer
↳↳↳↳ arrivalFlight| **ShuttleFlightDetail** | No | Indica los detalles del vuelo de llegada
↳↳↳↳↳ airportCode| *String* | No | Indica el código del aeropuerto
↳↳↳↳↳ airportName| *String* | No | Indica el nombre del aeropuerto
↳↳↳↳↳ companyCode| *String* | No | Indica el código de la compañía que emite el billete
↳↳↳↳↳ companyName| *String* | No | Indica el nombre de la compañía que emite el billete
↳↳↳↳↳ flightNumber| *String* | No | Indica el número de vuelo
↳↳↳↳↳ flightTime| *Calendar* | No | Indica la fecha y hora del vuelo (dd/MM/yyyy HH:mm)
↳↳↳↳ departureFlight| **ShuttleFlightDetail** | No | Indica los detalles del vuelo de salida
↳↳↳↳↳ airportCode| *String* | No | Indica el código del aeropuerto
↳↳↳↳↳ airportName| *String* | No | Indica el nombre del aeropuerto
↳↳↳↳↳ companyCode| *String* | No | Indica el código de la compañía que emite el billete
↳↳↳↳↳ companyName| *String* | No | Indica el nombre de la compañía que emite el billete
↳↳↳↳↳ flightNumber| *String* | No | Indica el número de vuelo
↳↳↳↳↳ flightTime| *Calendar* | No | Indica la fecha y hora del vuelo (dd/MM/yyyy HH:mm)
↳ bookingPayment| **BookingPayment** | No | Información del último pago de la reserva<sup>1</sup>
↳↳ modality| *Enum* | Sí | Modalidad de pago (Establishment / Inmediate / Deferred / CancelPenalty / Instalment / ExternManagement)
↳↳ type| *Enum* | Sí | Tipo de pago (BankTransfer / Card / VirtualCard / PrepaidCard / WarrantyCard / Cash / Cheque / Credit / Voucher / ExternalManaged / PinPad)
↳↳ otaType| *Enum* | No | Tipo de pago OTA (PA: Agency prepaid/PC: Customer prepaid/PD: Customer payment/PB: Voucher Payment/FC: Credit invoice/PM: Loyalty points + money PU: Loyalty Points/SC: By contract/SD: OTA Virtual card/NN: TPV pending/AW: Prepaid TPV with AMEX/VW: Prepaid TPV NO AMEX)
↳↳ status| *Enum* | Sí | Estado de pago (Pending / Ok / Error / Cancelled / Inapplicable)
↳↳ description| *String* | No | Contiene el nombre comercial asignado a a la modalidad de pago
↳ paymentCardDetail| **PaymentCardDetail** | No | Detalles de la tarjeta que ha realizado el último pago (sólo viene informado si bookingPayment.type es Card, PrepaidCard, VirtualCard o WarrantyCard)
↳↳ holder| *String* | Sí | Nombre del titular de la tarjeta
↳↳ number| *String* | Sí | Número de la tarjeta
↳↳ expiryDate| *Date* | Sí | Fecha de caducidad (dd/MM/yyy)
↳↳ securityCode| *String* | No | Código de seguridad (cvc2)
↳ paymentDetail[]| **PaymentDetail** | No | Log con todos los pagos realizados en la reserva
↳↳ action| *String* | Sí | Tipo de operación (charge / refund)
↳↳ paymentStatus| *String* | Sí | Estado del pago (Pending / Ok / Error / Cancelled / Inapplicable)
↳↳ type| *String* | Sí | Código del tipo de pago (Establishment / Inmediate / Deferred / CancelPenalty / Instalment / ExternManagement)
↳↳ otaType| *Enum* | No | Tipo de pago OTA (PA: Agency prepaid/PC: Customer prepaid/PD: Customer payment/PB: Voucher Payment/FC: Credit invoice/PM: Loyalty points + money PU: Loyalty Points/SC: By contract/SD: OTA Virtual card/NN: TPV pending/AW: Prepaid TPV with AMEX/VW: Prepaid TPV NO AMEX)
↳↳ date| *Calendar* | Sí | Fecha de la transacción
↳↳ amount| *Double* | Sí | Importe (#.##)
↳↳↳ cardDetail| *PaymentDetailCardDetail* | No | Detalle pago con tarjeta de crédito
↳↳↳↳ status| *String* | Sí | Estado del pago (Pending / Ok / Error / Cancelled / Inapplicable)
↳↳↳↳ card| *CreditCard* | Sí | Información de la tarjeta de crédito
↳↳↳↳↳ cardTypeCode| *String* | No | Código de la tarjeta de crédito
↳↳↳↳↳ cardTypeDescription| *String* | No | Nombre del tipo de tarjeta de crédito
↳↳↳↳↳ holder| *String* | Sí | Nombre del titular de la tarjeta
↳↳↳↳↳ number| *String* | Sí | Número de la tarjeta
↳↳↳↳↳ hashedValue| *String* | No | Número de la tarjeta
↳↳↳↳↳ seriesCode| *String* | No | CVC
↳↳↳↳↳ expiryDate| *Date* | Sí | Fecha de caducidad (dd/MM/yyy)
↳↳↳↳ systemCode| *String* | Sí | Identificador del sistema de pago
↳↳↳↳ reference| *String* | Sí | Localizador de la reserva
↳↳↳↳ authorizedCode| *String* | Sí | Código de autorización
↳↳↳↳ errorDescription| *String* | No | Descripción del error en el pago
↳↳↳ externalManagedDetail| *PaymentExternalManagedDetail* | No | Datos detallados de un sistema de pago externo, por ejemplo Paypal
↳↳↳↳ externalSystemCode| *String* | Sí | Código del sistema externo
↳↳↳↳ externalReference| *String* | Sí | Referencia externa
↳↳↳↳ status| *String* | Sí | Estado del pago (Pending / Ok / Error / Cancelled / Inapplicable)
↳↳↳ virtualCard| *VirtualCard* | No | Información de la tarjeta virtual
↳↳↳↳ code| *String* | Sí | Código de tarjeta virtual
↳↳↳↳ accountCode| *String* | Sí | Código de la cuenta que gestiona las tarjetas virtuales
↳↳↳↳ authorizedCode| *String* | Sí | Código de autorización del pago
↳↳↳↳ currencyCode| *String* | Sí | Código de divisa asociada al usuario
↳↳↳↳ availableAmount| *String* | Sí | Importe disponible en la cuenta que gestiona las tarjetas virtuales
↳↳↳↳ status| *String* | Sí | Estado de la tarjeta virtual (Active / Inactive / Blocked / Close)
↳↳↳↳ referencePayClient| *String* | Sí | eferencia del pago para el cliente
↳↳↳↳ description| *String* | No | Descripción del elemento
↳↳↳↳ person| *BasePerson* | No | Persona con los datos básicos
↳↳↳↳↳ firstName| *String* | No | Nombre de la persona
↳↳↳↳↳ firstLastName| *String* | No | Primer apellido de la persona
↳↳↳↳↳ secondLastName| *String* | No | Segundo apellido de la persona
↳↳↳↳↳ birthDate| *Date* | No | Fecha de nacimiento
↳↳↳↳ contact| *BaseContact* | No | Contacto con los datos básicos
↳↳↳↳↳ phone| *String* | No | Número de teléfono
↳↳↳↳↳ fax| *String* | No | Número de Fax
↳↳↳↳↳ email| *String* | No | Dirección de e-mail
↳↳↳↳↳ web| *Date* | No | Dirección de la página web
↳↳↳↳ address| *Address* | No | Información de Dirección
↳↳↳↳↳ countryCode| *String* | No | Código del país
↳↳↳↳↳ countryName| *String* | No | Nombre del país
↳↳↳↳↳ state| *String* | No | Estado
↳↳↳↳↳ county| *Date* | No | Condado
↳↳↳↳↳ province| *String* | No | Provincia
↳↳↳↳↳ locationCode| *String* | No | Código de la localidad, ciudad, zona rural
↳↳↳↳↳ locationName| *String* | No | Nombre de la localidad, ciudad, zona rural
↳↳↳↳↳ postalCode| *Date* | No | Código postal
↳↳↳↳ creditCard| *CreditCard* | No | Información de la tarjeta de crédito
↳↳↳↳↳ cardTypeCode| *String* | No | Código de la tarjeta de crédito
↳↳↳↳↳ cardTypeDescription| *String* | No | Nombre del tipo de tarjeta de crédito
↳↳↳↳↳ holder| *String* | Sí | Nombre del titular de la tarjeta
↳↳↳↳↳ number| *String* | Sí | Número de la tarjeta
↳↳↳↳↳ hashedValue| *String* | No | Número de la tarjeta
↳↳↳↳↳ seriesCode| *String* | No | CVC
↳↳↳↳↳ expiryDate| *Date* | Sí | Fecha de caducidad (dd/MM/yyy)
↳↳↳ prepaidCardDetail| *PrepaidCardDetail* | No | Detalle pago con tarjeta de prepago
↳↳↳↳ status| *String* | Sí | Estado del pago (Pending / Ok / Error / Cancelled / Inapplicable)
↳↳↳↳ systemCode| *String* | No | Identificador del sistema de pago
↳↳↳↳ card| *CreditCard* | Sí | Datos de la tarjeta prepago
↳↳↳↳↳ cardTypeCode| *String* | No | Código de la tarjeta de crédito
↳↳↳↳↳ cardTypeDescription| *String* | No | Nombre del tipo de tarjeta de crédito
↳↳↳↳↳ holder| *String* | Sí | Nombre del titular de la tarjeta
↳↳↳↳↳ number| *String* | Sí | Número de la tarjeta
↳↳↳↳↳ hashedValue| *String* | No | Número de la tarjeta
↳↳↳↳↳ seriesCode| *String* | No | CVC
↳↳↳↳↳ expiryDate| *Date* | Sí | Fecha de caducidad (dd/MM/yyy)
↳↳↳ warrantyCardDetail| *WarrantyCardDetail* | No | Detalle pago con tarjeta de garantía
↳↳↳↳ status| *String* | Sí | Estado del pago (Pending / Ok / Error / Cancelled / Inapplicable)
↳↳↳↳ systemCode| *String* | No | Identificador del sistema de pago
↳↳↳↳ card| *CreditCard* | Sí | Datos de la tarjeta de garantía
↳↳↳↳↳ cardTypeCode| *String* | No | Código de la tarjeta de crédito
↳↳↳↳↳ cardTypeDescription| *String* | No | Nombre del tipo de tarjeta de crédito
↳↳↳↳↳ holder| *String* | Sí | Nombre del titular de la tarjeta
↳↳↳↳↳ number| *String* | Sí | Número de la tarjeta
↳↳↳↳↳ hashedValue| *String* | No | Número de la tarjeta
↳↳↳↳↳ seriesCode| *String* | No | CVC
↳↳↳↳↳ expiryDate| *Date* | Sí | Fecha de caducidad (dd/MM/yyy)
↳ saleRules| **SaleRules** | No | Elemento que contiene las reglas de ventas cargadas en Hotetec, y que se han aplicado en la reserva.
↳↳ bookingRoom[]| *Room* | No | Elemento que contiene las reglas de venta aplicadas en una habitación en concreto.
↳↳↳ @id| *Integer* | Sí | Identificador de la habitación
↳↳↳ saleRulesByDay[]| *SaleRulesByDay* | Sí | Elemento que contiene un desglose de las reglas de venta aplicadas por día.
↳↳↳↳ day| *Date* | Sí | Día aplicado
↳↳↳↳ saleRule[]| *SaleRule* | No | Elemento que contiene una regla de venta aplicada en el día concreto.
↳↳↳↳↳ name| *String*| Sí | Nombre de la regla de venta.
↳↳↳↳↳ amount| *String*| No | Importe cargado en la regla de venta aplicada.
↳↳↳↳↳ percentage| *String*| No | Percentaje cargado en la regla de venta aplicada.

<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp; Ejemplos: 
<ul>
   <li>Pago con tarjeta de garantía, pendiente de cobro, a cobrar en establecimiento. modality: Establishment, type: WarrantyCard, status: Pending</li>
   <li>Pago inmediato, cobrado a traves de una pasarela de pago externa. modality: Inmediate, type: ExternalManaged, status: Ok</li>
   <li>Pago a crédito, acordado con la agencia. modality: ExternManagement, type: Credit, status: Inapplicable</li>
</ul>
</aside>