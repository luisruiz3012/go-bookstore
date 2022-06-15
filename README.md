# Golang bookstore API
---

This is a basic REST API built with the Go/Golang programming language to practice backend development with Go/Golang and relational SQL databases (in this case MySQL).

**Technologies used**

- gorilla/mux: Routing module
- jinzhu/gorm: ORM used in Go/Golang to handle SQL databases requests and connections
- jinzhu/gorm/dialects/mysql: MySQL driver to work with the jinzhu/gorm module
- net/http: Native module to create backend server and handle requests and responses
- encodig/json: Native module that allows you to work with json
- fmt: Native module that allows you to print command-line messages
- strconv: Native module used to handle data parsing
- io/ioutil: Native module that provides I/O utility functions


**Project Requirements**

- You must have Golang installed on your computer (Use this link to check the original installation guide https://go.dev/dl/)
- If possible, try to use Golang version 1.18 or greater to ensure the code will work correctly since this is the version that was used in this project
- You should also have docker and docker-compose installed on your machine in order to use the docker-compose file to enable the MySQL database (If you already have MySQL installed on your computer you can skip this requirement)
- You should also have Git installed on your machine in order to clone the github repo


## Cloning the project

Enter this command on your command-line:

```
git clone https://github.com/luisruiz3012/go-bookstore.git
cd go-bookstore
go mod download
```


## Project config

After cloning the project and installing the dependencies, it is important to make some changes to ensure the project will work as intended, please make sure to follow this steps:

1. If you are using docker-compose to use MySQL, you must edit the docker-compose.yml file on the root folder of the project and add a value to the MYSQL_ROOT_PASSWORD field

```
MYSQL_ROOT_PASSWORD: your_mysql_password
```

2. Go to the pkg/config/app.go file and edit the gorm.Open() (line 13) connection URL by replacing user by your MySQL user and password by your MySQL password

```
  d, err := gorm.Open("mysql", "user:password@/simplerest?charset=utf8&parseTime=True&loc=Local")
```


## Compiling and running the server

Once you complete the project setup you are ready to compile the code and run it, in order to do this you must follow this steps:

1. Go to the cmd/main/ folder on your command-line
2. Enter the follorwing command:
```
go run build
```
3. If you are using mac or linux you can do ./main. If you are using use Windows you can open the project folder on your File Manager and execute the main.exe file on the cmd/main/ folder inside of the project
4. Test the API using any HTTP client like insomnia or postman (The server is running on port 3000 but you can change the port on the main.go file inside cmd/main/main.go)


**References**
Original code written by  AkhilSharma90 https://github.com/AkhilSharma90/Golang-MySQL-CRUD-Bookstore-Management-API
Youtube freeCodeCamp video https://www.youtube.com/watch?v=jFfo23yIWac&t=5784s
