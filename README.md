# README
API MockサーバのResponseJsonファイルを格納しています。

# Quick Start
```
git clone https://github.com/Sugi275/qicoo-api-mock.git ~/qicoo-api-mock
docker run --name apimock --rm -d -p 80:80 -v ~/qicoo-api-mock/api_responses/:/data/ sugimount/qicoo-apimock:0.0.1
```

API Curl
```
# create a question
curl -s -v -H "Content-Type: application/json" -X POST http://localhost/v1/questions -d '
{
  "event": "jkd1812",
  "program": "1",
  "comment": "kubernetesの〇〇について教えてください！"
}
'

# Retrieve a Question
curl -s -v -H "Content-Type: application/json" -X GET http://localhost/v1/questions/BosWT9EsdzgjPn

# Delete a Question
curl -s -v -H "Content-Type: application/json" -X DELETE http://localhost/v1/questions/BosWT9EsdzgjPn

# list all questions
curl -s -v -H "Content-Type: application/json" -X GET http://localhost/v1/questions

# like a question
curl -s -v -H "Content-Type: application/json" -X PUT http://localhost/v1/questions/BosWT9EsdzgjPn/like

# create a user
curl -s -v -H "Content-Type: application/json" -X POST http://localhost/v1/users -d '
{
  "username": "sugimount",
  "type": "twitter",
  "user_url": "https://twitter.com/sugimount"
}
'

# Retrieve a user
curl -s -v -H "Content-Type: application/json" -X GET http://localhost/v1/users/IOodngp39890ba

# Delete a User
curl -s -v -H "Content-Type: application/json" -X DELETE http://localhost/v1/users/IOodngp39890ba

# List all Users
curl -s -v -H "Content-Type: application/json" -X GET http://localhost/v1/users
```
