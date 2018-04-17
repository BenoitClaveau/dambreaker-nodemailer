# damless-nodemailer
Use [nodemailer](https://www.npmjs.com/package/nodemailer) to send email from your [Dam Less server](https://www.npmjs.com/package/damless).

## Features

  * [DamLess](https://www.npmjs.com/package/damless)
  * [Nodemailer](https://www.npmjs.com/package/nodemailer)
  
### Add the nodemailer parameters in config.json

```json
{
  "nodemailer": {
    "transport": {
      "service": "service name",
      "auth": {
        "user": "user",
        "pass": "password"
      }
    },
    "dkim": {
      "domainName": "your domain.com",
      "keySelector": "123456",
      "privateKey": "./key.pem"
    },
    "from": "your e-mail address"
}
```

### Declare and inject nodemailer service

```js
const DamLess = require("damless");
const damless = new DamLess();

damless.inject("mailer", "damless-nodemailer");
```

## API

  * send(mailerOptions)
  
```js
const mailOptions = {
    from: 'Fred Foo ✔ <foo@blurdybloop.com>', // sender address 
    to: 'bar@blurdybloop.com, baz@blurdybloop.com', // list of receivers 
    subject: 'Hello ✔', // Subject line 
    text: 'Hello world ✔', // plaintext body 
    html: '<b>Hello world ✔</b>' // html body 
};

return mailer.send(mailOptions);
```

## Installation

```bash
$ npm install damless-nodemailer
```
