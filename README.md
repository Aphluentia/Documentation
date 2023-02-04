# Documentation  
Dissertation Documentation   
This repository contains diagrams and more information about the solution   

## Architecture  
The Solution has 3 main modules:   
- The External Services (Aphluentia Mobile App, What a Nice Gesture, Mobihealth etc):   
    - These services can connect directly to the database to retrieve the necessary information  
    - These services need to communicate with the WebPlatform to notify of changes, pairing operations and heartbeat  

- The Aphluentia Platform Services (the to-be-developed web platform):     
    - Can connect directly to the database's CRUD methods  
    - Needs to communicate with the External Services to notify of changes, pairing operations and heartbeat  
    - Must be responsive to changes in the External Services

- The Database System (Solution's Database):   
    - A REST API which allows for CRUD Operations over the database  

![Architecture](diagrams//arch/arch.png)


Furthermore, some services have to be developed to allow for the communicate between the external services and the Aphluentia++ Platform Services
- Broker:
    - Allows for the notification of each service when a change has taken place    
- CommunicationAPI:    
    - External REST API which offers a standardized way of each service to connect to the Broker   
    - Sends to the broker change notifications, heartbeat requests and responses and pairing operation details  