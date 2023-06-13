## Dokumentation

Step 1 - CD ind i frontend mappen og udfør følgende

    docker build -t con-front-v6 .

Step 2 - CD ind i backend mappen og udfør følgende

    docker build -t con-back-v6 .

Step 3 - CD ud i roden til docker-compose.yml og udfør følgende

    docker swarm init

 Step 4 - Opstart swarmen

    docker stack deploy -c docker-compose.yml exam

 Step 5 - Brug følgende kommando for at tjekke om swarmen er oppe og køre

    docker service ls

Step 6 - Skaler op på en af containerne ved at benytte 

    docker service scale exam_backend=6
   
   I dette tilfælde skaleres op på backend. 
		
