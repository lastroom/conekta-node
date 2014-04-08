Conekta node.js wrapper
=========

Install

```sh
npm install conekta-node
```

Charge via card

```javascript
var conekta = require('conekta');

conekta.api_key = '';

var data = {
    "description": "Grad Stogies: Second Class",
    "amount": 20000,
    "currency": "MXN",
    "reference_id": "9893-cohib_s1_wolf_pack",
    "card": {
        "number": 4111111111111111,
        "exp_month": 12,
        "exp_year": 2015,
        "name": "Thomas Logan",
        "cvc": 666,
        "address": {
            "street1": "250 Alexis St",
            "city": "Red Deer",
            "state": "Alberta",
            "country": "Canada",
            "zip": "T4N 0B8"
        }
    }
}

var charge = conekta.Charge.create(data);

//Also you can get the attributes from the conekta response class:
console.log(charge.id);

//Or if you get an error:
console.log(charge.error.type);
```

Charge via oxxo

```javascript
var conekta = require('conekta');

conekta.api_key = '';

var data = {
    "currency": "MXN",
    "amount": 20000,
    "description": "Grad Stogies: Second Class",
    "reference_id": "9893-cohib_s1_wolf_pack",
    "cash": {
        "type": "oxxo"
    },
    "details": {
        "name": "Wolverine",
        "email": "logan.thomas@xmen.org",
        "phone": "403-342-0642"
    }
}

var charge = conekta.Charge.create(data);

//Also you can get the attributes from the conekta response class:
console.log(charge.id);

//Or if you get an error:
console.log(charge.error.type);
```

Charge via bank:

```javascript
var conekta = require('conekta');

conekta.api_key = '';

var data = {
    "currency": "MXN",
    "amount": 20000,
    "description": "Grad Stogies: Second Class",
    "reference_id": "9893-cohib_s1_wolf_pack",
    "bank": {
        "type": "banorte"
    },
    "details": {
        "name": "Wolverine",
        "email": "logan.thomas@xmen.org",
        "phone": "403-342-0642"
    }
}

var charge = conekta.Charge.create(data);

//Also you can get the attributes from the conekta response class:
console.log(charge.id);

//Or if you get an error:
console.log(charge.error.type);
```


#Retrieve events

```javascript
var conekta = require('conekta');

conekta.api_key = '';

var events = conekta.Event.all();

console.log(events);
```

## Endpoints

```
conekta.Charge.create()
conekta.Event.all()
```
