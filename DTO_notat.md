# DTO'er

# [Hello]
```
GET https://[SB1_Domain/cryptotestapp2000]/hei
//Headers
TOKEN: xxxxxxxxxxx
Content-Type: application/vnd.sparebank1.v1+json; charset=utf-8
```

response:
{response: "heisann!"}


# Buy
## Request:
```
POST https://[SB1_Domain/cryptotestapp2000]/buy
//Headers
USER-ID: xxxxxxxxxx \\String
Content-Type: application/vnd.sparebank1.v1+json; charset=utf-8

{
    id: xxx, //string
    amount: xxx //int
}
```

# Sell request
```
POST https://[SB1_Domain/cryptotestapp2000]/sellrequest
//Headers
USER-ID: xxxxxxxxxx \\String
Content-Type: application/vnd.sparebank1.v1+json; charset=utf-8

{
	orgnumber: "xxxx" //String
  price: xx.xx //Float
  amount: xx //Int
}
```

## utvidelser:
Expirydate


# Buy request
## Description
Publish a request to buy a number of items from the market. 
## Request:
```
POST https://[SB1_Domain/cryptotestapp2000]/buyrequest
//Headers
USER-ID: xxxxxxxxxx \\String
Content-Type: application/vnd.sparebank1.v1+json; charset=utf-8

{
	orgnumber: "xxxx" //String
  price: xx.xx //Float
  amount: xx //Int
}
```


## utvidelser:
Expirydate


# portfolio:
## Request:
```
GET  https://[SB1_Domain/cryptotestapp2000]/portfolio
//Headers
USER-ID: xxxxxxxxxx \\String
Content-Type: application/vnd.sparebank1.v1+json; charset=utf-8
```

## Response:
```
{
items:
  [
  	{
    	id: xxx, //string
      name: xxxx, //String
      price: xxx.xx, //Float
      amount: xxx, //int
    },
  	{
    	id: 1, //string 
      name: "bedrift ABC", //String
      price: 68.9, //Float
      amount: 42 //int
    }
  ]
}
```

# List market items
## Request:
```
GET https://[SB1_Domain/cryptotestapp2000]/listmarket
//Headers
Content-Type: application/vnd.sparebank1.v1+json; charset=utf-8
```

## Response:
```
{
items:
  [
  	{
    	id: xxx, //string
      name: xxxx, //String
      org_nr: xxx //Int
      type: [Sell/Buy] // String/Enum??
      price: xxx.xx, //Float
      amount_total: xxx, //int
    },
  	{
    	id: 2,
      name: "bedrift ABC",
      org_nr: 0123 
      Type: "Sell",
      price: 68.9, 
      amount: 4 
    },
  	{
    	id: 3,
      name: "bedrift ABC",
      org_nr: 0123
      type: "Buy",
      price: 70.4,
      amount: 6
    }
  ]
}
```

## Description
En liste over aksjer for salg. 
hva de ??nskes kj??pt for, eller solgt for.

## utvidelser:
input for ?? filtrere. 
"??nsker bare salg"
eller "??nsker bare kj??p"





# Prioritering Back-end
mock:
- aksjer eid av wallet id: svar med list over akser eid.
- Liste over alle aksjer. 
- aksjer ??nskes kj??pt: svar med "200 ok!"
- Aksjer til salg: svar med "200 solgt!" 
- Opprette aksje selskap - mottar form, svarer ok. 
p?? riktig: 
- lese akjser fra blokkkjede 
- lese portef??le fra blokkjede
------------------------
- publisere salg/kj??p/trasaksjon p?? kjeden
- nytt selskap p?? kjeden. 


# Prioritering Front-end
- Liste akser i portef??le
  - selg aksje
- List alle aksjer
  - kj??p og selg aksjer
- opprette Aksje selskap
------------------------
- liste alle salg, og kj??psordre p?? en aksje (gi bruker inntrykk av verdien p?? aksjen n??)
- 




























