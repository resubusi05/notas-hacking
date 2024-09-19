# Retos picoCTF

# Level First Find 

## Objetivo
Unzip this archive and find the file named 'uber-secret.txt'

## Solución

```
──(kali㉿kali)-[~/retosPico]
└─$ mkdir firstFind       
                                                                        
┌──(kali㉿kali)-[~/retosPico]
└─$ cd firstFind   
                                                                        
┌──(kali㉿kali)-[~/retosPico/firstFind]
└─$ cat files.zip  
PK
���Tfiles/UT    ��~b��~bux
                          ��PK
b��Tfiles/satisfactory_books/UT 7�~b:�~bux
                                          ��PK
r��T$files/satisfactory_books/more_books/UT     W�~bX�~bux
                                                          ��P�!�T��a;▒���3files/satisfactory_books/more_books/37121.txt.utf-8UT ��[bX�~bux
                                                                  �����rW�-
�ӌ��D��H����ʺ�:         �P�(ղce2�
                                 �Q��"����z�1�\kHff��ڻD~Yk�ys�������a�mS��~j�y3ܞ���u=l��z�.��n<�_����t���m3Ϊ�����>y��fݎU����*�Ǫ�i�T����UUw��k���u3�?����E?N��e��N��O����?
�bj�n���4��}3�W���������P�Ӭ�m�GU?�o��铡9�M�W�n��)�f؎x���[Woڅ��}�[l��f���>����6m�'xx8��/���-^���6�7�x�����O>�?}l6Mm����j�۽����1���������K>���O�����/|�M����[��ew�iǵ��_��_�뛋�7��瀞�W�Շ���|yS}��������._�����닏o.��WW/�r�����՛W/�������صtQ��-�r�h�������k{�f��N�����euy^�▒����k|�佖�U�����-��jh�e��V7M��⮧i7~���c�w���y�L��������llm�▒b�M��wC�M��k�Es�
                                                   >������e�����ݫ����������.n����U^��2�o��B��xyv�����V��|u����o.?����{��?���������7�������_VWo��x}������;����ū�7��
                  �����ǟ��77�o��^��������������tV}������|�b�������_/_�E�b/�^����\;��i:�Tc��٩+�tw�T]�mx����7K;�������P�<�]5��M??<}��fqWE��g���a�O��x�����f�β�������>vd����]?�I�Q��`�iYm��~7�w�f�$H���~������*��C�O�ܚ�����0pϱ��n!�P;�B����Z�$w�`M=t���C��/��'�z�o�����&ꛍݩ�Q���K�J�����`�p���>Y��fX��S&���B��v��r}����z��v�%�*<�r�U_��������^��▒.����{��i�����k������v�l����wak�u2]�/�l6����ڽ��fc:�?]l��>�.�&F�r��^�CgZ_�a���o>;�\
                                                       Ͷl�f��7����^۞o�o��C������'���dO�U�k�
                   ����n~�F�x)  Ҳ]��ɺ��^�����@~�n�;\p�to�f�z���.�      ��D1���[w�<}\����0�V��_;��I��
                            X���uߛ%ӻq���5�UK��\�H�[���fB]�����;���X�yg��)����P�Op��E\�R�>�.��v��ǘ�>;�/`Oa����65��h�sR���p"��f<yx��~h���9@Aт-��
                                                                      �{�xgFo��K        �▒���U�=���}��&��Q�6<p�+=�N8؋���o�#��~������������khB;��5�vnjn�L�Q�fyۄ����U�2�� ��~����p����&�T�g�fC��k�������(�|q���_h׾_�WS��G~��m��y�v�ݙfЦ�:f������
E���a��](�yk2��2I���PR`�Ħj<�]���ۮ<W��|"�W�f�&��'����Ŷ�\��O<Iҁ!
                                                              ߞ�R;��3]��ٴ��ږ��!��&��$�9��f|����-�����UW��j��y�n�X���gTE�,�aO��O���:+sj�}L;_���C�E�o�����>���5�.=�9���N���<4��m��Tu�M��=lEm���ZЦCK��?��,�`����tR�)�Z���vK~h�S�؛mh����(
              ھ��h��^Ͷ��bn����d_��3�O���3�h���F�[�"3y{
                                                      �ʏ��[�j2��y�~�հ�U���Rzس�w���0�~^��;�K.C׽�@Xj+��n�b��w�"s�L+���7�R{kohOj>��
                                                        N�����Z�d��?^�"�&���5v▒���X�V'n?�����n�G���+ى���g
ӜG�$�{;s��a�����N㧥�@�����;R

�ya�AThǐ�▒;]�J���?�*�'�;�;ʍ���xBzI&W�r%�Xm�I�_�M�$=�y��_}�[8j3���?�������j�����V��Ң���n��S��u���4�x��~%´����P`Y�dǻ��1k�����e�綗撙�|臻��gz�!N�@bA!48S<l�Ɣ
        t|l�ݥ��

┌──(kali㉿kali)-[~/retosPico/firstFind]
└─$ strings files.zip | grep pico                                       
picoCTF{f1nd_15_f457_ab443fd1}

```

## Notas adicionales
El comando strings files.zip | grep pico busca y muestra todas las cadenas de texto legible dentro del archivo files.zip que contienen la palabra "pico".

    strings: extrae texto legible de archivos binarios.
    grep pico: filtra las líneas que contienen la palabra "pico". 

## Referencias


