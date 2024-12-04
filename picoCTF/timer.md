# Retos picoCTF

# Level timer

## Objetivo
You will find the flag after analysing this apk
Download here.
## Solucion
´´´
┌──(kali㉿kali)-[~/Downloads/timer]
└─$ ls
timer.apk
                                                                            
┌──(kali㉿kali)-[~/Downloads/timer]
└─$ unzip timer.apk 
Archive:  timer.apk
  inflating: META-INF/com/android/build/gradle/app-metadata.properties  
  inflating: classes3.dex            
  inflating: classes2.dex            
  inflating: AndroidManifest.xml     
´´´

´´´
extracting: META-INF/androidx.print_print.version  
 extracting: META-INF/androidx.recyclerview_recyclerview.version  
 extracting: META-INF/androidx.savedstate_savedstate.version  
 extracting: META-INF/androidx.startup_startup-runtime.version  
 extracting: META-INF/androidx.tracing_tracing.version  
 extracting: META-INF/androidx.transition_transition.version  
 extracting: META-INF/androidx.vectordrawable_vectordrawable-animated.version  
 extracting: META-INF/androidx.vectordrawable_vectordrawable.version  
 extracting: META-INF/androidx.versionedparcelable_versionedparcelable.version  
 extracting: META-INF/androidx.viewpager2_viewpager2.version  
 extracting: META-INF/androidx.viewpager_viewpager.version  
 extracting: META-INF/com.google.android.material_material.version  
  inflating: kotlin/annotation/annotation.kotlin_builtins  
  inflating: kotlin/collections/collections.kotlin_builtins  
  inflating: kotlin/coroutines/coroutines.kotlin_builtins  
  inflating: kotlin/internal/internal.kotlin_builtins  
  inflating: kotlin/kotlin.kotlin_builtins  
  inflating: kotlin/ranges/ranges.kotlin_builtins  
  inflating: kotlin/reflect/reflect.kotlin_builtins  
  inflating: classes.dex             
  inflating: META-INF/CERT.SF        
  inflating: META-INF/CERT.RSA       
  inflating: META-INF/MANIFEST.MF    
                                                                            
┌──(kali㉿kali)-[~/Downloads/timer]
└─$ ls
AndroidManifest.xml  classes3.dex  kotlin    res             timer.apk
classes2.dex         classes.dex   META-INF  resources.arsc
                                                                            
┌──(kali㉿kali)-[~/Downloads/timer]
└─$ grep -rw picoCTF              
grep: classes3.dex: binary file matches
                                                                            
┌──(kali㉿kali)-[~/Downloads/timer]
└─$ strings -t c classes3.dex | grep picoCTF
Usage: strings [option(s)] [file(s)]
 Display printable strings in [file(s)] (stdin by default)
 The options are:
  -a - --all                Scan the entire file, not just the data section [default]
  -d --data                 Only scan the data sections in the file
  -f --print-file-name      Print the name of the file before each string
  -n <number>               Locate & print any sequence of at least <number>
    --bytes=<number>         displayable characters.  (The default is 4).
  -t --radix={o,d,x}        Print the location of the string in base 8, 10 or 16
  -w --include-all-whitespace Include all whitespace as valid string characters
  -o                        An alias for --radix=o
  -T --target=<BFDNAME>     Specify the binary file format
  -e --encoding={s,S,b,l,B,L} Select character size and endianness:
                            s = 7-bit, S = 8-bit, {b,l} = 16-bit, {B,L} = 32-bit
  --unicode={default|show|invalid|hex|escape|highlight}
  -U {d|s|i|x|e|h}          Specify how to treat UTF-8 encoded unicode characters
  -s --output-separator=<string> String used to separate strings in output.
  @<file>                   Read options from <file>
  -h --help                 Display this information
  -v -V --version           Print the program's version number
strings: supported targets: elf64-x86-64 elf32-i386 elf32-iamcu elf32-x86-64 pei-i386 pe-x86-64 pei-x86-64 elf64-little elf64-big elf32-little elf32-big pe-bigobj-x86-64 pe-i386 pdb srec symbolsrec verilog tekhex binary ihex plugin
                                                                            
┌──(kali㉿kali)-[~/Downloads/timer]
└─$ strings -t x classes3.dex | grep picoCTF
   160f *picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
´´´
## Referencias


