This is the signed SSL certificate for the ABC service.If there is a private key.pem, It will be for a demo certificate and will be used for signed messages destined for ABC incoming service.

There will be the public-cert.cer which is loaded into ABC-msg-incoming service truststore and is used to validate the incoming message signature.

There should also be an alias which represents the common name of the certificate 

To regenerate these certificate upon expiry , please follow the guid in the confluence page:
<URL>
