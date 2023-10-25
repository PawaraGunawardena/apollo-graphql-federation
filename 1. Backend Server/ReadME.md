1. Install dependencies
        
        npm install

2. Start the JSON server
        
        json-server -q db.json

3. Investigate data

        curl --location 'http://localhost:3000/movies'

        curl --location 'http://localhost:3000/movies/1'

        curl --location 'http://localhost:3000/movies/' \
        --header 'Content-Type: application/json' \
        --data '{
                "id": 6,
                "name": "Shelter",
                "duration": 90,
                "genre": "Fantasy",
                "views": 300
        }'

        curl --location --request PATCH 'http://localhost:3000/movies/6' \
        --header 'Content-Type: application/json' \
        --data '{
                "id": 6,
                "name": "Scooby and Scrappy Doo",
                "duration": 90,
                "genre": "Fantasy",
                "views": 300
        }'

        curl --location --request DELETE 'http://localhost:3000/movies/6'