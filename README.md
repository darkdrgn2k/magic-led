# magic-led
Blue tooth controled LED strip BLE reverse engineer


Ussage
gatttool  -b 50:8C:B1:45:DA:99 --char-write-req -a 0x0025 -n <COMMAND>

IE 
`gatttool  -b 50:8C:B1:45:DA:99 --char-write-req -a 0x0025 -n 03000000`

## Commands

### 03000000
Turn Off leds

### 03XXYYZZ
Turn on and set colour
*colour order may bay be differnet*
XX = R  00-ff 
YY = G  00-ff
ZZ = B  00-ff

### 07XXYY
Pre programmed pattern
xx = Type of pattern
- 01 - Outside In
yy - speed 00 - ??  
- fast to slow. 
- 50 seems to crash it

