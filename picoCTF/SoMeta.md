# Retos picoCTF

# Level So Meta

## Objetivo
Find the flag in this picture.

## Solucion
picoCTF{s0_m3ta_d8944929}

Para esto solo tuvimos  que ver la metadata de la imagen

'''
┌──(kali㉿kali)-[~/Downloads/SoMeta]
└─$ open pico_img.png 
                                                                                  
┌──(kali㉿kali)-[~/Downloads/SoMeta]
└─$ identify pico_img.png 
pico_img.png PNG 600x600 600x600+0+0 8-bit sRGB 108795B 0.000u 0:00.000
                                                                                  
┌──(kali㉿kali)-[~/Downloads/SoMeta]
└─$ identify -verbose pico_img.png
Image:
  Filename: pico_img.png
  Permissions: rw-r--r--
  Format: PNG (Portable Network Graphics)
  Mime type: image/png
  Class: DirectClass
  Geometry: 600x600+0+0
  Units: Undefined
  Colorspace: sRGB
  Type: TrueColor
  Base type: Undefined
  Endianness: Undefined
  Depth: 8-bit
  Channel depth:
    red: 8-bit
    green: 8-bit
    blue: 8-bit
  Channel statistics:
    Pixels: 360000
'''

'''
 Properties:
    Artist: picoCTF{s0_m3ta_d8944929}
    date:create: 2024-12-02T23:50:43+00:00
    date:modify: 2020-10-26T18:38:23+00:00
    date:timestamp: 2024-12-02T23:52:11+00:00
    png:IHDR.bit-depth-orig: 8
    png:IHDR.bit_depth: 8
    png:IHDR.color-type-orig: 2
    png:IHDR.color_type: 2 (Truecolor)
    png:IHDR.interlace_method: 0 (Not interlaced)
    png:IHDR.width,height: 600, 600
    png:text: 2 tEXt/zTXt/iTXt chunks were found
    signature: b4b34b413063f7efefcf33aeb2711fd6401d564724e71a461f74ba3c2c9087d3
    Software: Adobe ImageReady
  Artifacts:
    filename: pico_img.png
    verbose: true
  Tainted: False
  Filesize: 108795B
  Number pixels: 360000
  Pixels per second: 98.3245MB
  User time: 0.000u
  Elapsed time: 0:01.003
  Version: ImageMagick 6.9.13-12 Q16 x86_64 18420 https://legacy.imagemagick.org
'''

## Referencias


