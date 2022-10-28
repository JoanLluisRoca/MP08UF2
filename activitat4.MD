# Activitat 4:

## Gestió d'usuaris:

Hi ha dos tipus d'usuaris, els admins amb permissos per gestionar Owncloud i els usuaris normals.

On fica resposta afegeix una captura de pantalla on es vegi que has fet l'acció que es demana.

**Aquesta part de la pràctica la feu amb un company/a, li creeu un usuari i li doneu el vostre nom de domini d'Owncloud.**

Per a que pugui accedir necessitarà:

- La MV amb owncloud ha d'estar en mode "adaptador pont".
- El fitxer /etc/hosts del company ha de tenir la IP de la MV i el nom de domini de la MV del company/a.


**4.1.-** Crea un usuari admin que es digui adminXYZ, on XYZ són les inicials del teu nom:

![adminJRS](https://user-images.githubusercontent.com/114162286/198635842-3274b778-2596-4398-8b2f-d61eb75dbb46.png)

**4.2.-** Inicia sessió com a l'usuari adminXYZ.

![inicisesio](https://user-images.githubusercontent.com/114162286/198636444-d381979c-f4f7-404e-894e-40e0f3515c4b.png)

**4.3.-** Crea un usuari XYZ on XYZ son les inicials del company/a i afegeix-lo al grup usuaris, aquest usuari tindrà una quota de 512 MB.

![comptecompany](https://user-images.githubusercontent.com/114162286/198637037-3134a1e1-f003-4625-842a-a39d3292fd8b.png)

![quota](https://user-images.githubusercontent.com/114162286/198637897-35d65275-bdb3-4ecd-b07c-a5bf5901af8f.png)

**4.4.-** Podem crear fitxers d'una mida determinada a Linux amb la comanda:

```
truncate -s 10M file.txt
```

A l'exemple es crea un fitxer de 10MB.

Crea 6 fitxers de 100MB i pujal's a Owncloud un per un.

![documents100](https://user-images.githubusercontent.com/114162286/198639931-db2fe8ae-6ce5-4c35-bef2-142dd9990f13.png)

![espailliure](https://user-images.githubusercontent.com/114162286/198641046-69d40847-d541-411a-a860-440e28f443eb.png)

**4.5.-** Mostra el missatge d'error per haver superat la quota d'usuari.

![missatge](https://user-images.githubusercontent.com/114162286/198641370-ae147f1b-35fc-473d-be4c-85e7b6c1518e.png)

**4.6.-** Busca al teu perfil quin percentatge de quota estas utilitzant.

**RESPOSTA**

**4.7.-** Canvia la quota de l'usuari a 1GB i mostra tots els fitxers pujats.

![meucompte](https://user-images.githubusercontent.com/114162286/198648990-13945e4c-f06a-4ecc-91ac-3330bb78ef9b.png)

**4.8.-** Crea un usuari anomenat usuari2XYZ i fical al grup usuaris.

![usuari2](https://user-images.githubusercontent.com/114162286/198650043-823f2c02-20af-4d11-99c7-6a6f42818da0.png)

**4.9.-** Comparteix un fitxer de usuariXYZ a usuari2XYZ i mostra com l'usuari2XYZ pot veure i descarregar el fitxer.

Compartint el fitxer:
![compart](https://user-images.githubusercontent.com/114162286/198651225-3ba1e614-c4c1-4496-8edd-c8667dcf74e4.png)

Comprovació de compartició:
![compconf](https://user-images.githubusercontent.com/114162286/198651432-9c8857d9-0cd8-4c5b-8cfb-7f82961031c4.png)

**4.10.-** Esborra la carpeta Learn more about owncloud.

Esborrar:
![carpetaesborrada](https://user-images.githubusercontent.com/114162286/198652410-d7bb3c45-27da-4965-b9df-c6a0c87902ee.png)

**4.11.-** Recupera la carpeta Learn more about owncloud.

Recuperar:
![recuperar](https://user-images.githubusercontent.com/114162286/198652551-700c17dc-b6f0-4471-ae00-aa7124f3b43d.png)

**4.12.-** Com a usuariXYZ crea una carpeta nova anomenada shared i comparteix-la amb l'usuari usuari2XYZ.

Crear carpeta:
![shared](https://user-images.githubusercontent.com/114162286/198653964-9f459c60-e9fe-49d3-8dee-639986fa5f0b.png)

Compartir:
![comshared](https://user-images.githubusercontent.com/114162286/198654184-f8c907d0-7ad2-4fcb-8234-b4243e76a49f.png)

Confirmació:
![confirmació](https://user-images.githubusercontent.com/114162286/198654680-8ef4f615-9b45-4507-accc-7c6314d34c1b.png)

**4.13.-** Entra a Market instal·la dues aplicacions que no estiguin ja instal·lades i explica què fan i com funcionen.

![image](https://user-images.githubusercontent.com/110727546/196159706-705ff624-c409-4632-acb4-f43ffcc486d4.png)

1.
![1contact](https://user-images.githubusercontent.com/114162286/198656167-63f01db8-773f-4262-af38-fb1d8606b2da.png)
Aquesta aplicació, i serveix per a tindre una targeta de contactes on pots guardar tota l'informació del contacte que es necessiti.

2.
![2calendari](https://user-images.githubusercontent.com/114162286/198658088-e41fad13-69b3-47d8-bc69-8ebe19793183.png)
Aquesta aplicació i serveix per apuntar els nostres events en un calendari.

**4.14.-** Crearem una carpeta nova per emmagatzematge a Owncloud, la carpeta serà /media/publicXYZ on XYZ són les teves inicials i apareixerà amb el nom de public als usuaris.

Aquesta carpeta haurà de pertànyer a l'usuari www-data.

![PUBLICJRS](https://user-images.githubusercontent.com/114162286/198660362-aea388cf-54ac-4c36-be51-c30330e52098.png)

Compartir:

![compUSU](https://user-images.githubusercontent.com/114162286/198661272-55ec423c-51df-433f-b77e-bd2627e7532f.png)

**4.15.-** Connectarem la carpeta publicXYZ com emmagatzematge local, tal i com s'indica [aquí](https://doc.owncloud.com/server/next/admin_manual/configuration/files/external_storage/local.html). Tots els usuaris tindran accés a la carpeta.

Primer habilitarem l'ematgatzematge extern:
![editar1](https://user-images.githubusercontent.com/114162286/198666865-ddc8f18f-1062-46c4-8d5a-74d1e76c405c.png)

Afegir linea nova:

\\\
'files_external_allow_create_new_local' => 'true',
\\\

![novalinea2](https://user-images.githubusercontent.com/114162286/198670113-a8ef5c3e-668b-4379-99b8-b3a90146a85b.png)

En quest punt al fer tal com diu la pagina no hem carrega per posar l'usuari hi entrar.

**4.16.-** Un usuari normal pujarà un fitxer a la carpeta public.

**RESPOSTA**

**OPCIONAL.-** Aquesta tasca és opcional.

Intenta connectar com a emmagatzematge extern el teu compte de Google Drive de l'Institut. Tens com fer-ho [aquí](https://doc.owncloud.com/server/next/admin_manual/configuration/files/external_storage/google.html).

**RESPOSTA**
