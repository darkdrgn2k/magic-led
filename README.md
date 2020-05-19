# magic-led
Blue tooth controled LED strip BLE reverse engineer
Seems to be controlled by writing to attribute  `0x0025`

Remember to update MAC address

Usage
gatttool  -b 50:8C:B1:45:DA:99 --char-write-req -a 0x0025 -n <COMMAND>

## Set Commands

### 03000000
Turn Off leds
ie `gatttool  -b 50:8C:B1:45:DA:99 --char-write-req -a 0x0025 -n 03000000`


### 03XXYYZZ
Turn on and set colour
*colour order may bay be differnet*
XX = R  00-ff 
YY = G  00-ff
ZZ = B  00-ff

ie `gatttool  -b 50:8C:B1:45:DA:99 --char-write-req -a 0x0025 -n 03ff0000`


### 07XXYY
Pre programmed pattern
xx = Type of pattern
- 01 - Outside In

yy - speed 00 - ??  
- fast to slow. 
- 50 seems to crash it

ie `gatttool  -b 50:8C:B1:45:DA:99 --char-write-req -a 0x0025 -n 070125`
`
## Reading current settings

`gatttool -b 50:8C:B1:45:DA:99 --char-read -a 0x0025`
Characteristic value/descriptor: 03 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
meaning `30000000`
