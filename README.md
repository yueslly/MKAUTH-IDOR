# MKAUTH-IDOR
An idor was found at a brazilian ISP system.

##Mk-Auth IDOR in Central/Suporte on GET method parameter

##Product Description:
Mk-Auth is a Brazilian Management System for Internet Service Providers used to control client access and permissions via a web interface panel.

##Vulnerability Description:
It is possible to see and send support calls of others users just changing the value of parameter "chamado" by GET method

##Additional Information:
Is possible for an authenticated user to change the value of parameter "chamado" and get control of support page of another users.
https://{{HOST}}/central/suporte.hhvm?page=mensagens&chamado={{IDOR}}

Note: the value of "chamado" is DDMMYY{{+8 numbers}} easy to FUZZ.

![mkauth-idor](https://user-images.githubusercontent.com/47789115/222015803-d4a78f99-9599-428e-be2d-22adabef3048.gif)

##Vulnerability Type:
portswigger: https://portswigger.net/web-security/access-control/idor
CWE-639: Authorization Bypass Through User-Controlled Key | Alternate terms: Insecure Direct Object Reference (IDOR)

##Vendor:
Mk-Auth

##Affected Product:
MK-AUTH 23.01K4.9
Probably previous are also affected

##Affected Component:
Central: Suporte: Chamados Técnicos

##Attack Vector:
Remote

##Code Execution:
No

##Attack Vector:
An authenticated user must access a authenticated support web page then change the parameter to another one.

##Reference:
	http://mk-auth.com.br/

##Discoverer:
Yueslly Lisboa (0xC4CTU$) | yuesllylisboa[at]gmail.com

##Thanks to:
Alan Lacerda (alacerda) | alacerda@intruderlabs.com.br
Filipe Cordeiro (SK) | fsantos@intruderlabs.com.br
All members of intruderLabs <3
