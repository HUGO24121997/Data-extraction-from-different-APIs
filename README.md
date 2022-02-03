# Extraction des données a partir de différents Api
--------------------------------------------------------------------------------------
## API REST OpenSky
L'API vous permet de récupérer des informations sur l'espace aérien en direct à des fins de recherche et à des fins non commerciales.  
Les informations sont fournies sous la forme de vecteurs d'état, Il existe également une documentation un peu plus spécifique disponible pour API REST  
Y a une liaison de langage Python et une liaison de langage Java pour l'API REST.  
  
Les avions vus par le réseau OpenSky sont associés à des informations sur l'état du vol dérivées des messages ADS-B et Mode S. L'état d'un avion est un résumé de toutes les informations de suivi (principalement la position, la vitesse et l'identité) à un certain moment. Ces états d'aéronefs peuvent être récupérés sous forme de vecteurs d'état sous la forme d'un objet JSON.
  
  Dans l'ADS-B , chaque avion (en fait chaque transpondeur) est identifié par une adresse unique, l'adresse OACI 24 bits . Habituellement, cette adresse est affichée dans sa représentation hexadécimale à 6  caractères.  
Dès qu'un message ADS-B d'un avion arrive sur  les  serveurs,ils créent un enregistrement pour l'avion - le soi-disant vecteur d'état. Toutes les informations nécessaires au suivi de l'avion, y compris son identité (adresse OACI + indicatif d'appel), les informations temporelles ( timestamps Unix ), et les informations spatiales (position, vitesse, cap, ...) seront représentées dans ce vecteur d'état.  

  --------------------------------------------------------------------------------------------------------  
  ## CovidTracker API
  CovidTracker est un outil qui permet de suivre l'évolution de l'épidémie du Coronavirus en France et dans le monde. La plateforme propose diverses visualisations de données, des     articles afin de décrypter l'évolution de l'épidémie.  
  L'API de données publiques donne accès à toutes les données au niveau national et étatique. ils fournissons des données aux formats JSON et CSV.  
  
  --------------------------------------------------------------------------------------------------------
  ## Explication
  Pour commencer, nous avons récupérer des données des deux api en grâce aux Requêtes HTTP en Python en utilisant les adresses URL respectives des deux APIs. Et ce, grâce au module "requests", plus particulièrement la méthode 'get()'. Cette méthode est communément appellée 'Web Scraping'. 
''' EXEMPLE code résultat '''  


Une fois les données récupérés, on les encode sous format 'JSON' en utilisant la méthode 'json()' du module "json" pour les rendre plus facilement utilisables.
''' EXEMPLE code résultat '''  


Ensuite, On les place dans un DataFrame Pandas pour les visualiser, les structurer et les nettoyer
''' EXEMPLE code résultat '''  


On supprime les attributs non essentielle à notre utilisation prévue de ces données
''' EXEMPLE code résultat '''

Et pour finir, on les injecte dans une base de données sqllite, avec le module 'sqllite3' 
''' EXEMPLE code résultat '''  

