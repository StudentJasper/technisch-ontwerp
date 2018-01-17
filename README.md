# Technisch ontwerp 
#### Model, Controllers en View
##Model
##### Bestand: users.py

table users  
class: User.py  
	Attributen: id
  
Functie: login(name, password)  
returned een User of None  
Beschrijving: Gebruiker logt zichzelf in door correcte gebruikersnaam en wachtwoord in te vullen.
  
Functie: register(name, password, password confirmation, email)  
	returned een User of None  
Beschrijving: gebruiker vult zijn gegevens in die worden opgeslagen in een database (users) waardoor deze kan inloggen. 
 
Functie: account(id)  
	returned een User of None  
Beschrijving: gebruiker kan zijn gegevens aanpassen daarna worden deze aangepast in de database users.
  
Functie: profile(id):  
	returned Profile of None  
Beschrijving: bewerken van profiel zoals plaatsen van foto’s en profielfoto wijzigen. 
 
##### Bestand: tinder.py  
find(id)  
Beschrijving: Weergeven van profielen waarbij je kan “liken” of wegklikken om met andere mensen in contact te komen. Wanneer op match wordt geklikt return True en bij het wegklikken returned False.  
returned True of False  

match(id, otherid)  
Beschrijving: Wanneer er op match wordt geklikt (True) wordt eigen id en id van dat profiel opgeslagen in table tinder  

check_match(id, otherid) 
Beschrijving: Check of er wederzijdse match is tussen de twee profielen.  

#####Bestand: helpers.py
apology()    
Voor het correct gebruik van de functies en benodigdheden
  
loginrequired()  
Om ervoor te zorgen dat pagina’s alleen te zien zijn door gebruikers.  

from flask import render_template   
Om een volgende pagina te laden en door te navigeren.  

## Controllers  
#### application.py waaronder de volgende functies vallen:  
#####/main  
GET:  
laat main.html zien
  
#####/register  
GET:  
laat register.html zien  
POST:  
roept register() aan  
sla user_id op in session  
redirect naar workspace.html wanneer succesvol is   geregistreerd, anders apology en redirect naar register.html  

#####/login  
GET:  
laat login.html zien  
POST:  
roept login(name, password) aan   
slaat user_id in session op   
redirect naar workspace.html  

#####/workspace  
GET:  
laat workspace.html zien  

#####/find  
GET:  
laat find.html zien  
GET  
roept find() aan  
wanneer find = True roept hij match(id,   otherid) op en check_match(id, otherid)  
redirect naar find.html  

#####/profile  
GET:  
laat profile.html zien  
POST:  
roept profile(id) aan  
redirect naar workspace.html  

#####/account  
GET:  
laat account.html zien  
POST:  
roept account() aan  
slaat evt. veranderingen in persoonlijke gegevens op  
redirect naar workspace.html  

#####/howitworks  
GET:   
laat howitworks.html zien  		
     
#####/logout  
GET:  
session.clear()  
redirect naar main.html

## View

Zie TistacyView.jpg voor afbeelding Tistacy  
View  

Main.html → login.html of register.html  →  workspace.html → find.html  en profile.html en account.html

##### Plugins en Frameworks
Hieronder enkele frameworks en plugins die wij denken te gaan gebruiken.  

- https://gist.github.com/rtt/10403467  
- https://github.com/fbessez/Tinder
  
Beide bevatten features van het huidige Tinder programma.

- https://github.com/pallets
  
Deze link bevat een flask en jinja framework.  

- https://v4-alpha.getbootstrap.com/examples/  


Voorbeelden van mogelijke opzetten voor onder andere een navigatiebalk en startscherm.
