# aws-simple-notification
Send an SMS notification to a phone number via AWS SNS.

## Installation

  npm install aws-simple-notification

## Usage
```javascript
  let sendMsg = require('aws-simple-notification');
  let awsConfig = {
  accessKeyId: '',
  secretAccessKey: '',
  region: ''
  };

  let msg = {
    "message": "123456 is your verification code.", //Note: you can use /n for line separations. IE - Line 1/nLine 2
    "sender": "A Better Way",
    "phoneNumber": "+1XXXXXXXXXX", // 10 digit phone prefixed with country code
    "origination": "+1XXXXXXXXXX" // The phone number or short code from which your message originated, set up in AWS Pinpoint
  };
  sendMsg(awsConfig, msg).then(data => {
    console.log("Message sent");
  })
  .catch(err => {
    consolr.log(err);
  });
```
