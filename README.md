# Firmware 
> ClassClicker firmware source files


## Documentation
### Hub
#### Pairing request (to pc)
```json
{"type":"pairing","data":{"id": 1, "macaddr":"aa:bb:cc:dd:ee:ff"}}
```
> `id` is number of the clicker

#### Pairing request (from pc)
```json
{"type":"accept_pairing","data":{"macaddr":"aa:bb:cc:dd:ee:ff"}}
```

#### Remove pairing (from pc)
```json
{"type":"remove_pairing","data":{"macaddr":"aa:bb:cc:dd:ee:ff"}}
```

#### Question (from pc)
```json
{"type":"new_question","data":{"amount_answers":4}}
```
> Using `amount_answer` is `0` will disable answering and the lights on all devices (used to reset when people didnt asnwer in time)

#### End question (from pc)
```json
{"type":"end_question","data":{"correct_answer":4}}
```

#### Answer (to pc)
```json
{"type":"answer","data":{"id":1,"timeToAnswer":0,"answer":4}}
```
> `id` is number of the clicker
> `timeToAnswer` is the time in `millis()` (`unsigned long`) it took to answer
> `answer` is which answer was given (1-4)

#### Powerstatus (to pc)
```json
{"type":"power_status","data":{"id":1,"isCharging":true,"usbPowerConnected":false,"batteryVoltage":3.23131}}
```
> `id` is number of the clicker

### Clickers
#### Set id (from pc)
```json
{"type":"set_id","data":{"id":1}}
```
