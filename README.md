# TodoList API Server (Golang/MySQL)

My #001 Mini Project on learning Go.

Based on Mohamad Fadhil's blog [post](https://fadhil-blog.dev/blog/golang-todolist/) and [medium](https://medium.com/better-programming/build-a-simple-todolist-app-in-golang-82297ec25c7d)

## Prerequisites
* Go
* Docker

## Setup
* clone into your chosen folder (eq : `~/works/`)

## Setup and enter to MySQL bash
* docker run -d -p 3306:3306 --name mysql -e MYSQL_ROOT_PASSWORD=root mysql
* docker exec -it mysql mysql -u root -p -e 'CREATE DATABASE todolist'
* docker exec -it mysql bash
* mysql -h localhost -u root -p

## Run the Apps
* $ go run todolist.go

## Hit the endpoints
* $ curl -i localhost:8000/healthz
* $ curl -X POST -d "description=Cook for dinner" localhost:8000/todo
* $ curl -X POST -d "completed=true" localhost:8000/todo/1
* $ curl -X DELETE localhost:8000/todo/1
* $ curl -i localhost:8000/todo-incomplete
* $ curl -i localhost:8000/todo-completed