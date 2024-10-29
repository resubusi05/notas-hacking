# Retos picoCTF

# Level Local Authority

## Objetivo
Can you get the flag?
Go to this website and see what you can discover.

## Solucion
 picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb} 

La solucion esta despues de iniciar sesion con el usuario y contraseña que se encuentra en secure.js

```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

## Referencias


