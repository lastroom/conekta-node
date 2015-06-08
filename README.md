Conekta 
=========

### This project is depricated we suggest the official module: https://github.com/conekta/conekta-node

Install

```sh
npm install conekta
```

Charge via card

```javascript
var conekta = require('conekta');

conekta.api_key = '1tv5yJp3xnVZ7eK67m4h';

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

var charge = conekta.Charge.create({
    params: data,
    success: function() {},
    errror: function() {}
});
```

Charge via oxxo

```javascript
var conekta = require('conekta');

conekta.api_key = '1tv5yJp3xnVZ7eK67m4h';

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

var charge = conekta.Charge.create({
    params: data,
    success: function() {},
    errror: function() {}
});
```

Charge via bank:

```javascript
var conekta = require('conekta');

conekta.api_key = '1tv5yJp3xnVZ7eK67m4h';

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

var charge = conekta.Charge.create({
    params: data,
    success: function() {},
    errror: function() {}
});
```

# Payee

Create payee

```javascript
var conekta = require('conekta');

conekta.api_key = '1tv5yJp3xnVZ7eK67m4h';

var data = {
    name: 'Julian Ceballos',
    email: 'julian@lastroom.mx',
    phone: '9991622695',
    payout_method: {
        type: 'bank_transfer_payout_method',
        account_number: '123456789012345678',
        account_holder: 'Julian Ceballos'
    }
};

conekta.Payee.create({
    params: data,
    success: function(payeeResp) {},
    error: function(payeeErr) {}
});
```

# Payouts

Create payout

```javascript
var conekta = require('conekta');

conekta.api_key = '1tv5yJp3xnVZ7eK67m4h';

var data = {
    amount: 10000,
    currency: 'MXN',
    payee_id: payee_id
};

conekta.Payout.create(
    params: data,
    success: function(payoutResp) {},
    error: function(payoutErr) {}
});
```

#Retrieve events

```javascript
var conekta = require('conekta');

conekta.api_key = '1tv5yJp3xnVZ7eK67m4h';

var events = conekta.Event.all();

console.log(events);
```

## Endpoints

```
conekta.Charge.create()
conekta.Payee.create()
conekta.Payout.create()
conekta.Event.all()
```
