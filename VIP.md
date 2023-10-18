```
Description:
A very simple system at a party. If you are a VIP, you can get everything.

Challenge : nc ctf.tcp1p.com 23345
```

After connecting to nc :

```[vielite@fedora blockchain]$ nc ctf.tcp1p.com 23345
Welcome to TCP1P Blockchain Challenge

1. How to 101?
2. get Contract
>> 1
Same as the last challenge, but this time, call the help() function first
```
so we call `help()`:
```vielite@fedora blockchain$ cast call 0xd4d782c57B2399B4DA8E112FDF9026F7AF62A859 "help()(string)" --rpc-url https://eth-sepolia.g.alchemy.com/v2/SMfUKiFXRNaIsjRSccFuYCq8Q3QJgks8
Welcome to TCP1P Private Club!

Enjoy the CTF Party of your life here!
But first... Please give me your id, normal people have at least member role
Of Course, there are also many VIPs over here. B-)

Functions:

Entrance(role) -> verify your role here, are you a member or VIP Class
   > role  --> input your role as string
stealVIPCode() -> someone might've just steal a vip code and want to give it to you
getFlag()      -> Once you show your role, you can try your luck! ONLY VIP Can get the Flag!

```
`stealVIPcode()` looks intresting so we call that.

```[vielite@fedora blockchain]$ cast call 0xd4d782c57B2399B4DA8E112FDF9026F7AF62A859 "stealVIPCode()(string)" --rpc-url https://eth-sepolia.g.alchemy.com/v2/SMfUKiFXRNaIsjRSccFuYCq8Q3QJgks8
 I may or may not get you a ticket, but I don't understand much about how to decode this.
It's some sort of their abiCoder policy. 
VIP-Ticket: 0x0000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000000000000002f5443503150317374436c61737353656174202d2069732074686520564950205469636b6574207468657920736169640000000000000000000000000000000000

[vielite@fedora blockchain]$ 
```
After seeing what looks like hex, i used python 

```python
 print(bytes.fromhex("0000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000000000000002f5443503150317374436c61737353656174202d2069732074686520564950205469636b6574207468657920736169640000000000000000000000000000000000"))
```
we get: 

```
b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00 \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00/TCP1P1stClassSeat - is the VIP Ticket they said\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
```
Next we call `Entrance()` with our ticket `TCP1P1stClassSeat`

```
[vielite@fedora blockchain]$ cast send 0xd4d782c57B2399B4DA8E112FDF9026F7AF62A859 "Entrance(string)" "TCP1P1stClassSeat" https://eth-sepolia.g.alchemy.com/v2/SMfUKiFXRNaIsjRSccFuYCq8Q3QJgks8
```

And finally we call `getFlag()`

```
cast call 0xd4d782c57B2399B4DA8E112FDF9026F7AF62A859 "getFlag()(string)" --rpc-url https://eth-sepolia.g.alchemy.com/v2/SMfUKiFXRNaIsjRSccFuYCq8Q3QJgks8
```

And we get our flag :p

Flag was : `TCP1P{4_b1t_of_f0undry_s3nd_4nd_abiCoder_w0n7_hur7_y34h}`

