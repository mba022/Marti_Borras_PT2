  # Demostració del funcionament # 
  ---
  ## Creació d’usuaris ##
  
  1 Primer clica les tres barres de dalt a la dreta, en el menu desplegable buscas "Cuentas".
  
  ---
<img width="800" height="800" alt="Captura desde 2025-11-18 14-24-31" src="https://github.com/user-attachments/assets/3b2f3722-0fc7-42f0-8f29-80590fb62e66" />

---
  2 Despres clica el boto de "nuevo usuario"/"Cuenta nueva" omple els parametres com necesitis.(un admin amb acces a TOT),(un visualitzador),(Un editor)

---
<img width="766" height="1001" alt="Captura desde 2025-11-18 14-24-43" src="https://github.com/user-attachments/assets/bd86c32e-343c-44d6-a60f-bbdec9dbcd0c" />

---
 3 Finalment, ja creats els tres comptes els assignarem permisos.

---
<img width="1854" height="1001" alt="Captura desde 2025-11-18 14-33-56" src="https://github.com/user-attachments/assets/f1284291-7bfc-4de1-91c8-4a3551aeb9b6" />

--- 
## Assignació de rols i permisos ##
### Permisos i creacio d'arxius compartits amb jerarquia ###
- 1 crear la carpeta, en la paguina principal despres d'iniciar nextcloud, el boto (+nuevo), crear carpeta i posar el nom.
---
 <img width="927" height="1001" alt="Captura desde 2025-11-18 14-11-50" src="https://github.com/user-attachments/assets/7c50636f-ae38-4117-8e26-0fde50157464" />
 
---
 
<img width="927" height="1001" alt="Captura desde 2025-11-18 14-14-33" src="https://github.com/user-attachments/assets/321b3b9d-d859-4440-b5e2-4763344087cb" />

---
  2 Ara hem d'afegir a el usuaris per poder assignar que permisos tenen, un cop estem dintre la carpeta li donem al simbol de +persona, li anem posant en el buscador a qui volem.
  
<img width="927" height="1001" alt="Captura desde 2025-11-18 14-15-43" src="https://github.com/user-attachments/assets/c9323674-ca16-47a8-8752-f35edeb63e8f" />

 ---
 3 posa un arxiu dintre de la carpeta i assigna (del arxiu concret) els permisos clicant amb la dreta.
 <img width="927" height="1001" alt="Captura desde 2025-11-18 14-13-47" src="https://github.com/user-attachments/assets/5724322b-2fcc-4efa-9341-2b980278be4c" />

 ---
   # Administració d’arxius #
  1 assignacio de permisos (rols) en la carpeta compartida. "al assignar-ho en la carpeta ens permet configuraro 1 vegada només, si despres vols pots cambiar els permisos de cert arxiu o cert usuari.
  
  ---
<img width="1787" height="967" alt="Captura desde 2025-11-25 14-22-15" src="https://github.com/user-attachments/assets/ba7cefce-a74b-4c2d-bfb6-08543ef7a78a" />

<img width="1787" height="967" alt="Captura desde 2025-11-25 14-22-54" src="https://github.com/user-attachments/assets/4500d743-dc5a-4f73-ad55-6f1224b3776e" />

<img width="1787" height="967" alt="Captura desde 2025-11-25 14-22-43" src="https://github.com/user-attachments/assets/d7a24aa5-b506-4e16-a908-f040fe67ecb9" />

   ## Accés des d’una màquina qualsevol de la xarxa ##
  1 Per a configurar l’accés remot a ownCloud des d’un altre dispositiu, pots enviarte un correu electronic amb un link compartit de la carpeta.
   <img width="1787" height="967" alt="Captura desde 2025-11-25 14-24-57" src="https://github.com/user-attachments/assets/f8ebbcd2-18ee-479a-ad5f-043b0402870b" />

---
2 obres el terminal de la maquina virtual, poses (ip -c a) et mostra la ip i mascara, les trajes de "red".

2.1 busca la ip (esta en color lila), copiala i gardala per despres.

2.2 posa el comando (sudo mkdir -p /var/www/domini.local), es un que ja hauries de tenir.

2.3 posa aquest altre comando (sudo nano /etc/apache2/sites-available/domini.local.conf), t'ha dobrir una pantalla nova la qual ha de (A estar omplerta, la qual cosa mira el punt 3A) (B estar buida, mirar punt 3B)

3 Ara configurarem que poguem accedir a (NEXTCLOUD) de manera remota sempre que tinguem la IP del (nextcloud) objectiu.

3A Hauries de veure una cosa similar a aquesta. 

<img width="861" height="700" alt="imatge" src="https://github.com/user-attachments/assets/b45fc63a-eb85-4134-9bb1-e9b817388f07" />

En la linea que posa "ServerName" o en la de "ServerAlias" (preferiblement en la primera) cambies el 'www.domini.local' a la IP guardada previaent **la IP de on obres el terminal/la maquina Virtual**

3.1.A Hauries de veure una cosa similar a aquesta.

<img width="1788" height="445" alt="imatge" src="https://github.com/user-attachments/assets/06a12b16-8a51-45e6-8062-9007ba9e4f58" />

En l'apartat "trusted_domains" poses ('www.domini.local', 'IP' de la maquina DESTINATARIA) no la maquina en la qual esta el terminal.

---

3B Si no tens res o l'acabes de crear despres de un reset, pots simplement copiar tal qual les imatges **asegurante de que poses les IP's correctes en el teu cas** **recorda que el "ServerAdmin" és el nom del ordinador posa el teu**

---

I ja finalment pots posar la Ip en cualsevol navegador i entrar a la paguina (de inici) de NextCloud.

**pots registrarte de nou o posar la teva altre compte**
