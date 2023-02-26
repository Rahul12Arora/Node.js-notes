# Node.js-notes
class notes
// const {name,city,job} = require("./variable.js");
// // import {name,city,job} from "./variable.js"
// console.log("name is",name);
// console.log("city is",city);
// console.log("job is",job);


const http = require("http");

//create server
const server = http.createServer(function(request,response){
    res = {
        name:"hello",
        second:"world"
    }

    response.writeHead(200,{
        // "Content-Type":"text/plain"
        "Content-Type":"application/json"
    })
    // response.end("Hello world");
    response.end(JSON.stringify(res));
})
server.listen(8080)






const http = require("http");
let id=0;
const todos = [];
const server = http.createServer(function(request,response){
    if(request.url==="/todos"){
        if(request.method === "GET"){
            response.writeHead(200,{
                "Content-Type":"application/json"
            });
            response.end(JSON.stringify(todos));
        }
        else if(request.url === "POST"){
            const newtodo = {
                id:id,
                title:`this is todo ${Math.random()}`,
                completed: false
            };
        
        todos.push(newtodo);
        id++;

        response.writeHead(200,{
            "Content-Type":"text/plain"
        });
        response.end("todo was inserted succesfully");
    }

    }
    
    // console.log("Request is", request.url, request.method);
    
    // response.end(JSON.stringify(todos));
})

server.listen(8080,()=>{
    console.log("server started at 8080");
})

