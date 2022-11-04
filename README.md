This microservice is a Rest API that uses Flask to store a database of users, along with a list of their favorite cryptocurrencies. The methods used are GET, POST, and PUT. These methods will allow the user to create an account and add coins to their "favorite coins" list.

To use the service, you can run main.py in a local terminal. The port is set to 8000.

GET METHOD: Returns username and list of favorite coins for a user.

    - Example API call:
        GET http://127.0.0.1:8080/users/5632499082330112

    - Body content:
        {
            "username": "oberliej"
        }

    - Returns:

        200 OK

        {
        "favorite_coins": ["Ethereum"],
        "username": "oberliej",
        "id": 5632499082330112,
        "self": "http://127.0.0.1:8080/users/5632499082330112"
        }

POST METHOD [/users]: Creates a user. List of favorite coins will be initialized to an empty list.

    - Example API call:
        POST http://127.0.0.1:8080/users/

    - Body content:
        {
            "name": "Ethereum"
        }

    - Returns:

        201 CREATED

        {
            "username": "oberliej",
            "favorite_coins": [],
            "id": 5632499082330112,
            "self": "http://127.0.0.1:8080/users/5632499082330112"
        }

POST METHOD [/favorite_coins]: Creates a coin. User will be initialized to null.

    - Example API call:
        POST http://127.0.0.1:8080/favorite_coins/

    - Returns:

        201 CREATED

        {
            "name": "Ethereum",
            "user": null,
            "id": 5700433016258560,
            "self":
            "http://127.0.0.1:8080/favorite_coins/5700433016258560"
        }

PUT METHOD: Assigns a favorite_coin to a user. The favorite_coin "user" field will be set to the id of the user, and the favorite_coin "name" field will be added to the user's "favorite_coin" list.

    - Example API call:
        PUT http://127.0.0.1:8080/users/5700433016258560/favorite_coins/5700433016258560

    - Returns:
        204 NO CONTENT

![UML](/Users/joryoberlies/Desktop/UML.png?raw=true "UML")
