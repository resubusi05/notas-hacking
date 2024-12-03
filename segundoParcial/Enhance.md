# Retos picoCTF

# Level Enhance!

## Objetivo
Download this image file and find the flag.
Download image file
## Solucion
picCTF{3nh4nc 3 d _aab729dd} 

LA bandera se puede encontrar en la metadata de la imagen

´´´
┌──(kali㉿kali)-[~/Downloads/Enhance]
└─$ ls
drawing.flag.svg
                                                          
┌──(kali㉿kali)-[~/Downloads/Enhance]
└─$ identify -verbose drawing.flag.svg 
Image:
  Filename: drawing.flag.svg
  Permissions: rw-------
  Format: SVG (Scalable Vector Graphics)
  Mime type: image/svg+xml
  Class: DirectClass
  Geometry: 794x1123+0+0
  Units: Undefined
  Colorspace: sRGB
  Type: GrayscaleAlpha
  Base type: Undefined
  Endianness: Undefined
  Depth: 16-bit
  Channel depth:
    red: 16-bit
    green: 16-bit
    blue: 16-bit
    alpha: 1-bit
  Channel statistics:
    Pixels: 891662
    Red:
      min: 0  (0)
      max: 65535 (1)
      mean: 32098.7 (0.489794)
      standard deviation: 32736.5 (0.499527)
      kurtosis: -1.99724
      skewness: 0.0407538
      entropy: 0.0940438
    Green:
      min: 0  (0)
      max: 65535 (1)
      mean: 32098.7 (0.489794)
      standard deviation: 32736.5 (0.499527)
      kurtosis: -1.99724
      skewness: 0.0407538
      entropy: 0.0940438
    Blue:
      min: 0  (0)
      max: 65535 (1)
      mean: 32098.7 (0.489794)
      standard deviation: 32736.5 (0.499527)
      kurtosis: -1.99724
      skewness: 0.0407538
      entropy: 0.0940438
    Alpha:
      min: 65535  (1)
      max: 65535 (1)
      mean: 65535 (1)
      standard deviation: 0 (0)
      kurtosis: -3
      skewness: 0
      entropy: 0
  Image statistics:
    Overall:
      min: 0  (0)
      max: 65535 (1)
      mean: 40457.8 (0.617346)
      standard deviation: 24552.4 (0.374645)
      kurtosis: -1.76585
      skewness: -0.482932
      entropy: 0.0705329
  Rendering intent: Perceptual
  Gamma: 0.454545
  Chromaticity:
    red primary: (0.64,0.33,0.03)
    green primary: (0.3,0.6,0.1)
    blue primary: (0.15,0.06,0.79)
    white point: (0.3127,0.329,0.3583)
  Background color: white
  Border color: srgba(223,223,223,1)
  Matte color: grey74
  Transparent color: none
  Interlace: None
  Intensity: Undefined
  Compose: Over
  Page geometry: 794x1123+0+0
  Dispose: Undefined
  Iterations: 0
  Compression: Undefined
  Orientation: Undefined
  Properties:
    date:create: 2024-12-03T15:14:50+00:00
    date:modify: 2024-12-03T15:14:50+00:00
    date:timestamp: 2024-12-03T15:14:50+00:00
    signature: 7a60750a29041765cd5c62f85e4b0b3dffdf3be30460eb745065c6788499530a
    svg:comment:  Created with Inkscape (http://www.inkscape.org/) 
    svg:title:          
  Artifacts:
    filename: drawing.flag.svg
    mvg:vector-graphics: push graphic-context "svg8"
compliance "SVG"
fill "black"
fill-opacity 1
stroke "none"
stroke-width 1
stroke-opacity 0
fill-rule nonzero
encoding "UTF-8"
viewbox 0 0 794 1123
affine 3.78095 0 0 3.78114 0 0
push defs
pop defs
push graphic-context "layer1"
push graphic-context "path3713"
stroke-width 0.264583
ellipse 106.212,134.472 102.054,99.0298 0,360
pop graphic-context
push graphic-context "path3717"
fill "#ffffff"
stroke-width 0.264583
circle 107.591,132.302 107.591,135.636
pop graphic-context
push graphic-context "path3719"
fill "#000000"
stroke-width 0.264583
ellipse 107.452,132.101 0.0278425,0.03182 0,360
pop graphic-context
push graphic-context "text3723"
font-size 0.00352781
font-style "normal"
font-weight "normal"
font-size 0.00352781
font-family "sans-serif"
letter-spacing "0px"
fill "#ffffff"
fill-opacity "1"
stroke "none"
stroke-width 0.264583
text 107.43,132.085 "     "
push graphic-context "tspan3748"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.085 "p "
pop graphic-context
push graphic-context "tspan3754"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.089 "i "
pop graphic-context
push graphic-context "tspan3756"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.094 "c "
pop graphic-context
push graphic-context "tspan3758"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.098 "o "
pop graphic-context
push graphic-context "tspan3760"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.103 "C "
pop graphic-context
push graphic-context "tspan3762"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.107 "T "
pop graphic-context
push graphic-context "tspan3764"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.111 "F { 3 n h 4 n "
pop graphic-context
push graphic-context "tspan3752"
font-size 0.00352781
font-size 0.00352781
fill "#ffffff"
stroke-width 0.264583
text 107.43,132.116 "c 3 d _ a a b 7 2 9 d d }"
pop graphic-context
pop graphic-context
pop graphic-context
pop graphic-context

    verbose: true
  Tainted: False
  Filesize: 2248B
  Number pixels: 891662
  Pixels per second: 5.01937MB
  User time: 0.230u
  Elapsed time: 0:01.177
  Version: ImageMagick 6.9.13-12 Q16 x86_64 18420 https://legacy.imagemagick.org
                                   
´´´

## Referencias


