# aws-iot-button

## Setup
### Create certificate

```
aws iot create-keys-and-certificate     --certificate-pem-outfile "myIOTButton.cert.pem"     --public-key-outfile "myIOTButton.public.key"     --private-key-outfile "myIOTButton.private.key"
```

### Connect the button to WIFI
it is possible to connect the AWS button by using AWS IOT app on mobile , or by direct access to the button . 
in order to connect the button directly , perform the following steps:
1. push the AWS button for 8 seconds , and wait for the blue light to blink
2. connect to the newly created wifi "configure me..."
3. the password is the last 8 digits of the serial number , on the back of the AWS button device
