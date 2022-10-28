# BookingAddPayment

> Ejemplo BookingAddPayment para añadir un pago de tipo inmediato

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingAddPaymentRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials> 
    <hotelCode>1234</hotelCode>
    <reference>DEMOHTT221017XFCN-SALE</reference>
    <paymentDetail>
        <action>Charge</action>
        <paymentStatus>Ok</paymentStatus>
        <type>Inmediate</type>
        <date>02/08/2022 09:43</date>
        <amount>500</amount>
        <externalSystemCode>SER</externalSystemCode>
        <externalReference>12345</externalReference>
    </paymentDetail>
</BookingAddPaymentRequest>
````

````json
{
  "BookingAddPaymentRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "reference": "DEMOHTT221017XFCN-SALE",
    "paymentDetail": {
      "action": "Charge",
      "paymentStatus": "Ok",
      "type": "Inmediate",
      "date": "02/08/2022 09:43",
      "amount": "500",
      "externalSystemCode": "SER",
      "externalReference": "12345"
    }
  }
}
````

> Ejemplo BookingAddPayment para añadir un pago de tipo transferencia bancaria

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingAddPaymentRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials> 
    <hotelCode>1234</hotelCode>
    <reference>DEMOHTT221017XFCN-SALE</reference>
    <paymentDetail>
        <action>Charge</action>
        <paymentStatus>Ok</paymentStatus>
        <type>BankTransfer</type>
        <date>02/08/2022 09:43</date>
        <amount>500</amount>
        <externalReference>12345</externalReference>
    </paymentDetail>
</BookingAddPaymentRequest>
````

````json
{
  "BookingAddPaymentRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "reference": "DEMOHTT221017XFCN-SALE",
    "paymentDetail": {
      "action": "Charge",
      "paymentStatus": "Ok",
      "type": "BankTransfer",
      "date": "02/08/2022 09:43",
      "amount": "500",
      "externalReference": "12345"
    }
  }
}
````

> Ejemplo BookingAddPayment para añadir un pago de tipo payByLink

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingAddPaymentRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials> 
    <hotelCode>1234</hotelCode>
    <reference>DEMOHTT221017XFCN-SALE</reference>
    <paymentDetail>
        <action>Charge</action>
        <paymentStatus>Ok</paymentStatus>
        <type>PayByLink</type>
        <date>02/08/2022 09:43</date>
        <amount>500</amount>
        <externEmail>soportetecnico@hotetec.com</externEmail>
    </paymentDetail>
</BookingAddPaymentRequest>
````

````json
{
  "BookingAddPaymentRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "reference": "DEMOHTT221017XFCN-SALE",
    "paymentDetail": {
      "action": "Charge",
      "paymentStatus": "Ok",
      "type": "PayByLink",
      "date": "02/08/2022 09:43",
      "amount": "500",
      "externEmail": "soportetecnico@hotetec.com"
    }
  }
}
````

> Ejemplo respuesta BookingConfirmResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingAddPaymentResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <booking>
        <reference>DEMOHTT221017XFCN-SALE</reference>
        <creationDate>06/07/2022 12:25</creationDate>
        <modificationDate>12/08/2022 12:47</modificationDate>
        <checkIn>17/10/2022</checkIn>
        <checkOut>19/10/2022</checkOut>
        <status>Confirmed</status>
        <amount>132</amount>
        <amountToInvoice>145.2</amountToInvoice>
        <bookingClient>
            <clientCode>XXX</clientCode>
            <clientReference>6666</clientReference>
        </bookingClient>
        <endCustomer>
            <name>TEST TEST TEST</name>
            <mail>soportetecnico@hotetec.com</mail>
            <phone>+34935500145</phone>
            <country>ES</country>
        </endCustomer>
        <commission>
            <serviceCommission>
                <serviceId>1</serviceId>
                <commissionPercentage>10</commissionPercentage>
            </serviceCommission>
        </commission>
        <hotelCode>1234</hotelCode>
        <currencyCode>EUR</currencyCode>
        <bookingRoom id="1">
            <checkIn>17/10/2022</checkIn>
            <checkOut>19/10/2022</checkOut>
            <status>Confirmed</status>
            <roomCode>DBL#STD</roomCode>
            <mealPlanCode>RO</mealPlanCode>
            <amount>132</amount>
            <totalRoomAmount>132</totalRoomAmount>
            <commissionRoomAmount>13.2</commissionRoomAmount>
            <netRoomAmount>118.8</netRoomAmount>
            <amountRoomToInvoice>118.8</amountRoomToInvoice>
            <roomRateDay>
                <day>17/10/2022</day>
                <rateCode>14426</rateCode>
                <rateName>TEST</rateName>
                <amount>66</amount>
            </roomRateDay>
            <roomRateDay>
                <day>18/10/2022</day>
                <rateCode>14426</rateCode>
                <rateName>TEST</rateName>
                <amount>66</amount>
            </roomRateDay>
            <guest id="0">
                <type>Adult</type>
                <amount>132</amount>
                <name>TEST TEST TEST</name>
                <birthDate>06/07/1989</birthDate>
            </guest>
        </bookingRoom>
        <bookingPayment>
            <modality>ExternManagement</modality>
            <type>ExternalManaged</type>
            <status>Ok</status>
        </bookingPayment>
        <paymentDetail>
            <action>Charge</action>
            <paymentStatus>Inapplicable</paymentStatus>
            <type>Card</type>
            <date>06/07/2022 12:25</date>
            <cardDetail>
                <status>Inapplicable</status>
                <card>
                    <holder>TEST HOLDER</holder>
                    <number>1234123412341234</number>
                    <hashedValue>1234123412341234</hashedValue>
                    <seriesCode>123</seriesCode>
                    <expiryDate>01/06/2027</expiryDate>
                </card>
            </cardDetail>
        </paymentDetail>
        <paymentDetail>
            <action>Charge</action>
            <paymentStatus>Ok</paymentStatus>
            <type>ExternalManaged</type>
            <date>02/08/2022 09:43</date>
            <amount>500</amount>
            <externalManagedDetail>
                <externalSystemCode>SER</externalSystemCode>
                <externalReference>12345</externalReference>
                <status>Ok</status>
            </externalManagedDetail>
        </paymentDetail>
        <extraCustomData>
            <customData>
                <key>CreationSystem</key>
                <value>EDR</value>
            </customData>
            <customData>
                <key>ParentSystem</key>
                <value>STK</value>
            </customData>
            <customData>
                <key>PriceType</key>
                <value>Net</value>
            </customData>
            <customData>
                <key>StatusPaymentBooking</key>
                <value>Pending</value>
            </customData>
            <customData>
                <key>OriginalAmount</key>
                <value>132.0</value>
            </customData>
        </extraCustomData>
    </booking>
</BookingAddPaymentResponse>
````

````json
{
  "BookingAddPaymentResponse": {
    "sessionId": "SUP#FOO#123456789",
    "booking": {
      "reference": "DEMOHTT221017XFCN-SALE",
      "creationDate": "06/07/2022 12:25",
      "modificationDate": "12/08/2022 12:47",
      "checkIn": "17/10/2022",
      "checkOut": "19/10/2022",
      "status": "Confirmed",
      "amount": "132",
      "amountToInvoice": "145.2",
      "bookingClient": {
        "clientCode": "XXX",
        "clientReference": "6666"
      },
      "endCustomer": {
        "name": "TEST TEST TEST",
        "mail": "soportetecnico@hotetec.com",
        "phone": "+34935500145",
        "country": "ES"
      },
      "commission": {
        "serviceCommission": {
          "serviceId": "1",
          "commissionPercentage": "10"
        }
      },
      "hotelCode": "1234",
      "currencyCode": "EUR",
      "bookingRoom": {
        "-id": "1",
        "checkIn": "17/10/2022",
        "checkOut": "19/10/2022",
        "status": "Confirmed",
        "roomCode": "DBL#STD",
        "mealPlanCode": "RO",
        "amount": "132",
        "totalRoomAmount": "132",
        "commissionRoomAmount": "13.2",
        "netRoomAmount": "118.8",
        "amountRoomToInvoice": "118.8",
        "roomRateDay": [
          {
            "day": "17/10/2022",
            "rateCode": "14426",
            "rateName": "TEST",
            "amount": "66"
          },
          {
            "day": "18/10/2022",
            "rateCode": "14426",
            "rateName": "TEST",
            "amount": "66"
          }
        ],
        "guest": {
          "-id": "0",
          "type": "Adult",
          "amount": "132",
          "name": "TEST TEST TEST",
          "birthDate": "06/07/1989"
        }
      },
      "bookingPayment": {
        "modality": "ExternManagement",
        "type": "ExternalManaged",
        "status": "Ok"
      },
      "paymentDetail": [
        {
          "action": "Charge",
          "paymentStatus": "Inapplicable",
          "type": "Card",
          "date": "06/07/2022 12:25",
          "cardDetail": {
            "status": "Inapplicable",
            "card": {
              "holder": "TEST HOLDER",
              "number": "1234123412341234",
              "hashedValue": "1234123412341234",
              "seriesCode": "123",
              "expiryDate": "01/06/2027"
            }
          }
        },
        {
          "action": "Charge",
          "paymentStatus": "Ok",
          "type": "ExternalManaged",
          "date": "02/08/2022 09:43",
          "amount": "500",
          "externalManagedDetail": {
            "externalSystemCode": "SER",
            "externalReference": "12345",
            "status": "Ok"
          }
        }
      ],
      "extraCustomData": {
        "customData": [
          {
            "key": "CreationSystem",
            "value": "EDR"
          },
          {
            "key": "ParentSystem",
            "value": "STK"
          },
          {
            "key": "PriceType",
            "value": "Net"
          },
          {
            "key": "StatusPaymentBooking",
            "value": "Pending"
          },
          {
            "key": "OriginalAmount",
            "value": "132.0"
          }
        ]
      }
    }
  }
}
````

> Ejemplo respuesta BookingConfirmResponse procesada incorrectamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingAddPaymentResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <notification code="DSUP-7">
        <type>E</type>
        <text>La funcionalidad ConfirmBooking-Inbound no está activada. Por favor, consulte su Account Manager</text>
    </notification>
</BookingAddPaymentResponse>
````

````json
{
  "BookingAddPaymentResponse": {
    "sessionId": "SUP#FOO#123456789",
    "notification": {
      "code": "DSUP-7",
      "type": "E",
      "text": "La funcionalidad ConfirmBooking-Inbound no está activada. Por favor, consulte su Account Manager"
    }
  }
}
````

Mensaje utilizado para pagos a reservas reservas.

### BookingAddPaymentRequest

Mensaje petición de recuperación de reservas
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
reference | *String* | Sí | Localizador de la reserva de Hotetec
hotelCode | *Integer* | Sí | Código de hotel
paymentDetail | **BookingPaymentDetail** | Sí | Elemento que contiene el pago a añadir
↳ action| *String* | Sí | Indica si el pago es un cobro (Charge) o una devolución (Refund).
↳ paymentStatus| *String* | Sí | Estado del pago (*Tendría que ser siempre Ok*, aunque acepta *Error*)
↳ type| *String* | Sí | Indica el tipo de pago realizado (Inmediato (**Inmediate**), Transferencia bancaria (**BankTransfer**) o PayByLink (**PayByLink**))
↳ date| *DateTime* | Sí | Fecha del pago (dd/MM/yyyy HH:mm)
↳ amount| *Double* | Sí | Importe total del pago (#.##)
↳ externalSystemCode| *String* | No<sup>1</sup> | Indica el código del sistema externo utilizado para el pago. (PayComet **PAC** o Transfermovil **TFM**)
↳ externalReference| *String* | No<sup>2</sup> | Indica la referencia del pago externo.
↳ externEmail| *String* | No<sup>3</sup> | Indica el email asociado al pago.

<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp;Este campo es obligatorio cuando el tipo de pago a añadir sea del tipo inmediato (**Inmediate**)
</aside>

<aside class="notice">
<sup>2</sup>&nbsp;&nbsp;&nbsp;Este campo es obligatorio cuando el tipo de pago a añadir sea del tipo inmediato (**Inmediate**) o Transferencia bancaria (**BankTransfer**)
</aside>

<aside class="notice">
<sup>3</sup>&nbsp;&nbsp;&nbsp;Este campo es obligatorio cuando el tipo de pago a añadir sea del tipo PayByLink (**PayByLink**)
</aside>

### BookingAddPaymentResponse

Mensaje respuesta de confirmación de reservas

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí|Identificador de la sesión que ha procesado la transacción
booking | **Booking** | No | Información de una reserva de hotel
↳ reference| *String* | Sí | Localizador de la reserva
↳ creationDate| *DateTime* | Sí | Fecha de creación de la reserva (dd/MM/yyy HH:mm)
↳ modificationDate| *DateTime* | No | Fecha de modificación de la reserva (dd/MM/yyyy HH:mm). Sólo viene informado cuando es una modificación de reserva
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
↳↳↳ nationality[]| *String* | No | Nacionalidad del huésped
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
↳ bookingPayment| **BookingPayment** | No | Información del pago de la reserva<sup>1</sup>
↳↳ modality| *Enum* | Sí | Modalidad de pago (Establishment / Inmediate / Deferred / CancelPenalty / Instalment / ExternManagement)
↳↳ type| *Enum* | Sí | Tipo de pago (BankTransfer / Card / VirtualCard / PrepaidCard / WarrantyCard / Cash / Cheque / Credit / Voucher / ExternalManaged / PinPad)
↳↳ otaType| *Enum* | No | Tipo de pago OTA (PA: Agency prepaid/PC: Customer prepaid/PD: Customer payment/PB: Voucher Payment/FC: Credit invoice/PM: Loyalty points + money PU: Loyalty Points/SC: By contract/SD: OTA Virtual card/NN: TPV pending/AW: Prepaid TPV with AMEX/VW: Prepaid TPV NO AMEX)
↳↳ status| *Enum* | Sí | Estado de pago (Pending / Ok / Error / Cancelled / Inapplicable)
↳↳ description| *String* | No | Contiene el nombre comercial asignado a a la modalidad de pago
↳ paymentCardDetail| **PaymentCardDetail** | No | Detalles de la tarjeta que ha realizado el pago (sólo viene informado si bookingPayment.type es Card, PrepaidCard, VirtualCard o WarrantyCard)
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
