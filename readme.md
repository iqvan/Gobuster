# Gobuster 


## Tabla de contenido

- [Introducción](#Introducción).
- [Gobuster Commands](#Gobuster-Commands).
- [Ejemplos](#Ejemplos).


--------------------------------
### Introducción
-------------------------------

¿Qué es gobuster?

Es una herramienta de fuzzing que nos ayuda a descubrir valiosos directorios si es que existen. 

--------------------------------
### Gobuster Commands
-------------------------------

Admite la adición de extensiones, lo que significa que también puede usar archivos de fuerza bruta.

```
gobuster dir -u http://example.com -w wordlist.txt -x php,txt,html
```

|Original URL   | Item in Wordlist	 | Specified Extension	 | Final URL |
| :---         |     :---:      |          :---:  |          :---:  |
| http://example.com	     | backup       | php       | http://example.com/backup.php                |
| http://example.com	     | backup       | txt       | http://example.com/backup.txt                |
| http://example.com	     | icecream     | html      | http://example.com/icecream.html      |

Detallaremos algunos opciones a continuación:

|Options       | Description	 | 
| :---         |     :---:      | 
| -u		     | Se usa para especificar qué URL enumerar  |
| -w		     | Se utiliza para especificar qué lista de palabras se agrega en la ruta de la URL, es decir, "http://url.com/word1", "http://url.com/word2", "http://url.com/word3.php"       |
| -x		     | Se utiliza para especificar extensiones de archivo, es decir, "php, txt, html"       |


Link de wordlist big: https://github.com/danielmiessler/SecLists/blob/master/Discovery/Web-Content/big.txt

--------------------------------
### Ejemplos
-------------------------------

```
gobuster dir -u http://10.10.56.102:3333 -w /usr/share/wordlists
gobuster dir -u http://10.10.238.180 -w /usr/share/wordlists
gobuster dir -u http://10.10.68.216 -w /usr/share/wordlists
sudo gobuster dir -u 10.10.138.7 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -s "301"
gobuster dir -uhttp://example.com -w wordlist.txt -x php,txt,html
```