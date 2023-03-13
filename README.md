
# About 
This project is a GraphQL demonstration using Go.

It shows the interaction between two entities, <i>Course and Category</i>, where there's a nested relationship in which a category has many courses.

# GraphQL
<a href="https://graphql.org/" target="_blank">GraphQL</a> is a query language for APIs created by Facebook (Meta), allowing clients to request precisely what they need to obtain as a response.

It can be very useful in multiple cenarios, including integrating with BFF (backend for frontend) solutions.

# Project technologies
* Go
* GraphQL using a library called <a href="https://gqlgen.com/" target="_blank">gqlgen</a>
* SQLite

# Project structure
<b>cmd</b> - main package<br />
<b>graph</b> - all graphql configuration <br />
&nbsp; | <b> model </b> - model structs <br />
<b>internal</b> <br />
&nbsp; | <b>internal/database</b> - services responsible to interact with database<br />
<b>db.sqlite</b> - in memory relational database


# SQLite commands
Two tables must be created:
```
create table categories (id string, name string, description string);
```

```
create table courses (id string, name string, description string, category_id string)
```

# GraphQL playground
After running the project using command below, GraphQL playground will open usually on port http://localhost:8080/
```
go run .\cmd\server\server.go  
```
<u>Example of GraphQL playground use</u>

<b>Query</b>: All query we need <br />
<b>Mutation</b>: All intention types of change

queryCategories
<div align="center">
<img src="/screenshots/queryCategories.png" width="1400" height="283"/>
</div> 

queryCategories without description
<div align="center">
<img src="/screenshots/queryCategoriesWithoutDesc.png"  width="1400" height="283" />
</div> 

### Useful commands

To initiate a project
```
go mod init projectName
```

To run the project
```
go run .\cmd\server\server.go  
```

 Command that synchronizes the go mod file with the actual dependencies used in the codebase
```
go mod tidy
```

Initialize gqlgen lib
```
go run github.com/99designs/gqlgen init 
```

To generate a new schema
```
go run github.com/99designs/gqlgen generate  
```

Running SQLIte (it depends on SQLite is installed and configured on your OS). I used command below on Windows.
```
C:\sqlite\sqlite3.exe db.sqlite
```

<br />
This project was built and inspired during course on the <a href="https://github.com/devfullcycle/13-GraphQL" target="_blank">Fullcycle platform.</a>
