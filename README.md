node-red-contrib-bithumbpublic
================

Node-RED node for bithumbpublic



## Install

To install the stable version use the `Menu - Manage palette - Install`
option and search for node-red-contrib-bithumbpublic, or run the following
command in your Node-RED user directory, typically `~/.node-red`

    npm install node-red-contrib-bithumbpublic

## Wrapper bithumbpublic.com API  
- https://apidocs.bithumb.com/docs/ticker

## Sample parameters
```js
// msg.api = 'ticker'
msg.api = 'orderbook'
// msg.api = 'transaction_history'
// msg.api = 'assetsstatus'
msg.order_currency = 'ETH'
msg.payment_currency = 'KRW'
// if api is btci then do not set any currency
// msg.api = 'btci'
return msg;

```

## Sample flows
```json
[{"id":"e8250aad.4962f8","type":"bithumbpublic","z":"2422d0a1.5c053","name":"","api":"ticker","order_currency":"BTC","payment_currency":"KRW","x":590,"y":160,"wires":[["8f98f6f3.43cb98"]]},{"id":"d50385f7.cd3d28","type":"function","z":"2422d0a1.5c053","name":"","func":"// msg.api = 'ticker'\nmsg.api = 'orderbook'\n// msg.api = 'transaction_history'\n// msg.api = 'assetsstatus'\n// msg.api = 'btci'\nmsg.order_currency = 'ETH'\nmsg.payment_currency = 'KRW'\nreturn msg;","outputs":1,"noerr":0,"initialize":"","finalize":"","x":380,"y":160,"wires":[["e8250aad.4962f8"]]},{"id":"23f2ba3e.8464c6","type":"inject","z":"2422d0a1.5c053","name":"","props":[{"p":"payload"},{"p":"topic","vt":"str"}],"repeat":"","crontab":"","once":false,"onceDelay":0.1,"topic":"","payload":"","payloadType":"date","x":200,"y":160,"wires":[["d50385f7.cd3d28"]]},{"id":"8f98f6f3.43cb98","type":"debug","z":"2422d0a1.5c053","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"payload","targetType":"msg","statusVal":"","statusType":"auto","x":810,"y":160,"wires":[]}]
```

## Sample result
```json
{"status":"0000","data":{"btai":{"market_index":"3721.49","width":"205.03","rate":"5.83"},"btmi":{"market_index":"7160.36","width":"204.89","rate":"2.95"},"date":"1617750682738"}}
```
