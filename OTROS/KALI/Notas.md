**NERF FONT PAGINA WEB**
ALT + . : Para tener el argumento del ultimo comando

echo $?
cd $!
neofetch - ver tu hardware
## problemas Grub
listar discos = fdisk -l


mount {disco} /mnt
cd /mnt
disk free command= df

## COMBINACIONES
ctrl + shift + enter        | DIVIDIR KITTY
ctrl + shift  + r              | REDIMENSIONAR KITTY
ctrl + shift  + t              | ABRIR VENTANA EN EL MISMO SITIO KITTY
ctrl + shift  + alt + t      | CAMBIAR NOMBRE VENTANA KITTY
ctrl + shift  + flechas    | MOVERSE VENTANA KITTY


ctrl + shift  + n              | NUEVA VENTANA KITTY
ctrl + shift  + w              | CERRAR VENTANA KITTY

Además también hay comandos como:
F1 y F3 copiar
F2, F4 pegar
pueder verlo en: **~/.config/kitty/kitty.conf**



### BORRAR ARCHIVOS SIN QUE SE PUEDA ANALISIS FORENSE
Puedes borrar archivos, de forma que sean prácticamente irrecuperable con analisis forense.
```
sudo apt install scrub
```
Ejemplo:
1. scrub -p dod archvo
2. shred -zun 10 -v archivo
(NO TENGO NI IDEA DE ESTO MIRAR EN OTRO MOMENTO)



### INFO SISTEMA

```
uname
uname -r
```
