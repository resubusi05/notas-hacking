# Retos picoCTF

# Level WebNet1

## Objetivo
We found this packet capture and key. Recover the flag.

## Solucion
    Usando wireshark nos vamos a editar-preferencias-protocols y buscamos TLS agragamos la llave que se nos dio y nos encontramos con un .jpg al verlo a detalle encontramos la bandera 
```
GET /starter-template.css HTTP/1.1
Host: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: text/css,*/*;q=0.1
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Referer: https://ec2-18-223-184-200.us-east-2.compute.amazonaws.com/second.html
Pragma: no-cache
Cache-Control: no-cache

HTTP/1.1 200 OK
Date: Fri, 23 Aug 2019 16:27:04 GMT
Server: Apache/2.4.29 (Ubuntu)
Last-Modified: Mon, 12 Aug 2019 16:47:05 GMT
ETag: "62-58fee462bf227-gzip"
Accept-Ranges: bytes
Vary: Accept-Encoding
Content-Encoding: gzip
Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
Content-Length: 100
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/css

body {
  padding-top: 5rem;
}
.starter-template {
  padding: 3rem 1.5rem;
  text-align: center;
}
GET /vulture.jpg HTTP/1.1
Host: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: image/webp,*/*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Referer: https://ec2-18-223-184-200.us-east-2.compute.amazonaws.com/second.html
Pragma: no-cache
Cache-Control: no-cache

HTTP/1.1 200 OK
Date: Fri, 23 Aug 2019 16:27:04 GMT
Server: Apache/2.4.29 (Ubuntu)
Last-Modified: Fri, 23 Aug 2019 16:26:33 GMT
ETag: "112fb-590cb44f2cbe6"
Accept-Ranges: bytes
Content-Length: 70395
Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
Keep-Alive: timeout=5, max=99
Connection: Keep-Alive
Content-Type: image/jpeg

......JFIF..............Exif..MM.*.................J...........R.(...........;.........Z................................picoCTF{honey.roasted.peanuts}......ICC_PROFILE.......lcms....mntrRGB XYZ .........).9acspAPPL...................................-lcms...............................................
desc.......^cprt...\....wtpt...h....bkpt...|....rXYZ........gXYZ........bXYZ........rTRC.......@gTRC.......@bTRC.......@desc........c2..................................................................................text....FB..XYZ ...............-XYZ ...........3....XYZ ......o...8.....XYZ ......b.........XYZ ......$.........curv...............c...k...?.Q.4!.).2.;.F.Qw].kpz....|.i.}...0.....C.................
```



## Referencias


