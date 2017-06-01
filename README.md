## cielo

Client para a API 3.0 da Cielo em Node.Js

## Installation
```js
npm install --save cielo
```

## Como utilizar?

### Iniciando
```js
var paramsCielo = {
    'MerchantId': 'xxxxxxxxxxxxxxxxxxxxxxx',
    'MerchantKey': 'xxxxxxxxxxxxxxxxxxxxxxxxxx',
    'RequestId': 'xxxxxxx' // Opcional
}

var cielo = require('cielo')(paramsCielo);
```

### Transação Simples
```js
var dados = {  
   "MerchantOrderId":"2014111703",
   "Customer":{  
      "Name":"Comprador crédito simples"
   },
   "Payment":{  
     "Type":"CreditCard",
     "Amount":15700,
     "Installments":1,
     "SoftDescriptor":"123456789ABCD",
     "CreditCard":{  
         "CardNumber":"0000000000000001",
         "Holder":"Teste Holder",
         "ExpirationDate":"12/2030",
         "SecurityCode":"123",
         "Brand":"Visa"
     }
   }
}

cielo.creditCard.simpleTransaction(dados, function(err, data){
    if (err){
        return console.error('ERRO', err);
    }
    return console.log(data);
})
```

## API Reference

PT-Br: http://developercielo.github.io/Webservice-3.0/?shell#integração-api-3.0
En: http://developercielo.github.io/Webservice-3.0/english.html#api-integration-3.0

<!--## Tests

Describe and show how to run the tests with code examples.-->

<!--## Contributors

Let people know how they can dive into the project, include important links to things like issue trackers, irc, twitter accounts if applicable.-->

## License

MIT License

Copyright (c) 2017 banzeh

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.