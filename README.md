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

### BONUS - Vil du gerne prøve at indsætte data?

Step 1 
Brug `docker ps` til at finde ud af hvad id'et på din database container er

Step 2 - Benyt følgende for at komme ind i containerens terminal

    docker exec -it id-på-container bash

 Step 3 - Benyt følgende til at opdatere APT, samt installerer mysql-client

    apt-get update apt-get install mysql-client -y

Step 4 - Brug mysql-client - password er root

    mysql -u root -p

 Step 5 - Hook ind i databasen

    USE zay_dev

Step 6 - Brug følgende for at indsætte egen data

    INSERT INTO Products (title, price, rating, brand, description, sizes, sku, stock, thumbnail, createdAt, updatedAt) VALUES ('Mads Test Product, 24.00, 3, 'Easy Wear', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod temp incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse. Donec condimentum elementum convallis. Nunc sed orci a diam ultrices aliquet interdum quis nulla.', 'S,M,L,XL', 12345678, 10, '/assets/img/product_single_10.jpg', NOW(), NOW());
