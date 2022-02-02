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
  ## covid 19 worldwide API
