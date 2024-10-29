# Retos picoCTF

# Level vault-door-3

## Objetivo
This vault uses for-loops and byte arrays. The source code for this vault is here: VaultDoor3.java

## Solucion

```
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
        String password = vaultDoor.findPassword();
        System.out.println("Password: picoCTF{" + password + "}");
    }

    public String findPassword() {
        String target = "jU5t_a_sna_3lpm18gb41_u_4_mfr340";
        char[] password = new char[32];

        for (int i = 0; i < 8; i++) {
            password[i] = target.charAt(i);
        }

        for (int i = 8; i < 16; i++) {
            password[23 - i] = target.charAt(i);
        }

        for (int i = 16; i < 32; i += 2) {
            password[46 - i] = target.charAt(i);
        }

        for (int i = 31; i >= 17; i -= 2) {
            password[i] = target.charAt(i);
        }

        return new String(password);
    }

    public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm18gb41_u_4_mfr340");
    }
}
```

```
PS C:\Users\vitoe>  & 'C:\Program Files\BellSoft\LibericaJDK-8-Full\bin\java.exe' '-agentlib:jdwp=transport=dt_socket,server=n,suspend=y,address=localhost:61225' '-cp' 'C:\Users\vitoe\AppData\Local\Temp\vscodesws_6ce9a\jdt_ws\jdt.ls-java-project\bin'
 'VaultDoor3'
Password: picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}
PS C:\Users\vitoe> 
```

## Referencias


