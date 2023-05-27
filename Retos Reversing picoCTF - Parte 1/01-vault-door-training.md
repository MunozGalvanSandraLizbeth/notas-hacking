# vault-door-training

## Descripción

Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java)

## Pistas

The password is revealed in the program's source code.

## Solución

```
┌──(kali㉿kali)-[~/picoctf/revercing/vaultdoortraining]
└─$ wget https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java
--2023-05-06 20:33:49--  https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 943 [application/octet-stream]
Saving to: ‘VaultDoorTraining.java’

VaultDoorTraining.java               100%[======================================================================>]     943  --.-KB/s    in 0s      

2023-05-06 20:33:50 (12.3 MB/s) - ‘VaultDoorTraining.java’ saved [943/943]

                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/revercing/vaultdoortraining]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_be8d9806f18");
    }
}

┌──(kali㉿kali)-[~/picoctf/revercing/vaultdoortraining]
└─$ javac VaultDoorTraining.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/revercing/vaultdoortraining]
└─$ ls -la
total 20
drwxr-xr-x 3 kali kali 4096 May  6 20:43 .
drwxr-xr-x 6 kali kali 4096 May  4 15:14 ..
drwxr-xr-x 2 kali kali 4096 May  2 14:41 vaultdoor1
-rw-r--r-- 1 kali kali 1106 May  6 20:43 VaultDoorTraining.class
-rw-r--r-- 1 kali kali  943 Oct 26  2020 VaultDoorTraining.java

┌──(kali㉿kali)-[~/picoctf/revercing/vaultdoortraining]
└─$ java VaultDoorTraining.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18} 
Access granted.
```

## Bandera

picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}

## Notas adicionales



## Referencias
- https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java