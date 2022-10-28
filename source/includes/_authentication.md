# Autenticación

> Ejemplo elemento credentials, presente en todas las peticiones XML


````xml
<RoomRatesRetrievalRequest>
   <user>userTest</user>
   <password>passwordTest</password>   
</RoomRatesRetrievalRequest>
````

Todas las peticiones contienen los elementos user y password (ejemplo a la derecha), el cuál contiene las credenciales de autenticación (usuario y password) que deberán ser proporcionadas por el distribuidor.

**El distribuidor debe proporcionar user, password y url del endpoint al que enviar las peticiones.**

