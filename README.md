# Simple-Web-Backend-With-DB-ChatGPT

Hello! Welcome to my Simple Web Backend with database experiment with ChatGPT. Feel free to clone the repo and test it out! If you want to know how I built this with ChatGPT, you can read the full blog [here](https://medium.com/@romalms10/building-a-simple-web-backend-with-a-database-using-chatgpt-e9e2e732ad54). This was built on top of a different experiment with ChatGPT: [Repo](https://github.com/RoMalms10/Simple-Web-Backend-ChatGPT) [blog](https://medium.com/@romalms10/how-to-build-a-simple-web-backend-with-chatgpt-784e031a485f)

## Get It Running
Make sure you have sqlite3 installed. You can follow along in the blog OR you can do this on a linux command line:
```
sudo apt update
sudo apt install sqlite3
```

Then, you can run it:
`go run main.go`

## Test that it works
Open a new window in your terminal and try out the following commands:

### See which people are already in memory
```
$ curl http://localhost:8080/people
[]
```
### Add a Person
```
$ curl -X POST -H "Content-Type: application/json" -d '{"name":"Jane","age":30}' http://localhost:8080/people
$
```
### See if your person is now in memory
```
$ curl http://localhost:8080/people
[{"ID":1,"CreatedAt":"2023-04-15T12:18:41.1606938-06:00","UpdatedAt":"2023-04-15T12:18:41.1606938-06:00","DeletedAt":null,"name":"Jane","age":30}]
```

### Get a specific person by name
```
curl http://localhost:8080/people?name=Jane
[{"ID":1,"CreatedAt":"2023-04-15T12:18:41.1606938-06:00","UpdatedAt":"2023-04-15T12:18:41.1606938-06:00","DeletedAt":null,"name":"Jane","age":30}]
```

### Delete a person from database
```
$ curl -X DELETE http://localhost:8080/people/Jane
$
```

### Check which people are left
```
$ curl http://localhost:8080/people
[]
```