# aws-iot-button setup - the hard way ( but not the hardest) 
it is possible to connect the AWS button by using AWS IOT app on mobile .
However , in order to 


## Setup

### Create thing type
```
aws iot create-thing-type \
    --thing-type-name "IOTButton" \
    --thing-type-properties "thingTypeDescription=AWS IOT button v1, searchableAttributes=wattage,model"
```

### Create thing

### Create certificate

```
aws iot create-keys-and-certificate   \
--certificate-pem-outfile "myIOTButton.cert.pem"    \
--public-key-outfile "myIOTButton.public.key"   \
--private-key-outfile "myIOTButton.private.key"
```

### Connect the button to WIFI

1. push the AWS button for 8 seconds , and wait for the blue light to blink
2. connect to the newly created wifi "configure me..."
3. the password is the last 8 digits of the serial number , on the back of the AWS button device




# Resources
* https://www.youtube.com/watch?v=oIPsQhStbnY
