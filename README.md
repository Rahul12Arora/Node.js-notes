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
