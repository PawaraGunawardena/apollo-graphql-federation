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

4. Request movies from the subgraph

        curl --location 'http://localhost:4000/' \
        --header 'Content-Type: application/json' \
        --data '{"query":"    query Movies {\n        movies {\n            id\n            name\n            genre\n            duration\n            views\n        }\n    }","variables":{}}'


4. Request movies from the supergraph

        curl --location 'http://localhost:5000/' \
        --header 'Content-Type: application/json' \
        --data '{"query":"    query Movies {\n        movies {\n            id\n            name\n            genre\n            duration\n            views\n        }\n    }","variables":{}}'
