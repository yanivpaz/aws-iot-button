# aws-iot-button setup - the hard way ( but not the hardest) 
it is possible to connect the AWS button by using AWS IOT app on mobile .
However , in order to 

## AWS account setup
from AWS IOT core service , perform the following steps

### Create policy
```
aws iot create-policy \
    --policy-name MyIOTButtonPolicy \
    --policy-document file://policy.json
```

where policy.json is 
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "iot:Publish",
      "Resource": "arn:aws:iot:eu-west-1:<account id>:topic/iotbutton/G030JF0583773HL9"
    }
  ]
}
```

### Create certificate
```
aws iot create-keys-and-certificate   \
--certificate-pem-outfile "myIOTButton.cert.pem"    \
--public-key-outfile "myIOTButton.public.key"   \
--private-key-outfile "myIOTButton.private.key"
```
Attach the security policy to the certificate 


### Create thing type
```
aws iot create-thing-type \
    --thing-type-name "IOTButton" \
    --thing-type-properties "thingTypeDescription=AWS IOT button v1, searchableAttributes=wattage,model"
```

### Create thing
```
aws iot create-thing \
    --thing-name "MyIOTButton" \
    --thing-type-name "IOTButton" 
```
attach certificate to the thing 


### Get IOT Gateway URL in the IOT Button 
GET the IOT UTL , which will be used later to setup the button 
```
aws iot describe-endpoint --endpoint-type iot:Data-ATS
```

### Connect the button to WIFI

1. Push the AWS button for 6 seconds , and wait for the blue light to flash 
2. Connect to the newly created wifi "configure me..."
3. The password is the last 8 digits of the serial number , on the back of the AWS button device



# Resources
* https://www.youtube.com/watch?v=oIPsQhStbnY
