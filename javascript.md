
#### Demonstrate the call back

    const write = (err,data)=>{
     fs.writeFile('./text.txt',"abshadhasgd","utf-8",(err,data)=>
    console.log("file is written"),
      fs.readFile('./text.txt', 'utf-8',(err,data)=>{
          console.log(data);
      })
    );
    }

#### Demonstrate promises
A promise can have following state:
pending, fullfilled, rejected
   
    let write = ()=>{
    return new Promise((resolve, reject)=>{
        fs.readFile('text2.txt', 'utf-8', (err,data)=>{
          if(err){
            reject(err);
          }
            resolve(data);
        })

    })
    }


#### Demonstarte async await
    let test = async()=>{
    
        let data = await write();
    
        console.log(data);
    
        }
    
    test();
    console.log("here");

#### Promise.all
    var p1 = Promise.resolve(3);
    var p2 = 1337;
    var p3 = new Promise((resolve, reject) => {
    setTimeout(() => {
    resolve("foo");
     }, 100);
    }); 

    Promise.all([p1, p2, p3]).then(values => { 
     console.log(values); // [3, 1337, "foo"] 
    });


#### Demonstrate arrays

    spread operators
    let array1 = [1,2,3,4];
    let array2 = [...array1,5,6,7];

    rest operators
    let func = (...args) =()=>P{}  //takes one or multiple arguments

    map
    let array3 = array2.map((ele)=>{
    return ele*2;
    });

    push and pop
    let pop1 = array2.pop();
    array2.pop();
    array2.push(7);

    filter
    let filt1= array1.filter((ele)=>ele<3);
    console.log(filt1);

    includes
    let inc1=  array1.includes(3);
    console.log(inc1);

    reduce (single output value)
    let arr2 = [3,5,6,9,11] 
    let red1= arr2.reduce((accumulator, currentvalue)=>{
    return accumulator+currentvalue;
    },18)

    let arr3 = ["cat", "dog","camel"]; 
    let red2= arr3.reduce((accumulator, currentvalue)=>{
    return accumulator+currentvalue;
    })



#### var and let

    var is function scope
    let is block scope
    hoisting - the process where all declaration of var are made ta the top.
    
    for(var i=0; i<=100; i++){
        //does something
    }
    console.log(i);//i = 101
    
    for(let i=0; i<=100; i++){
        //does something
    }
    console.log(i); //there is an error


#### event loop

    To state it bluntly, an event loop is that entity which pulls first elemnet in the event loop and places it on the 
    function execution stack whenever the function stack becomes empty.
    take SetTimeout for example-> when time out is called it is placed in to the stack-> set Time out calls the web Api provided to us
    by the browser, set the timer. Once completed, the callback function is placed on to the event queue. Once the function call stack 
    is empty, event loop takes the first element on the queue to the stack. This is event loop.


#### map in javascript

    let map = new Map();
    map.set("bob", 2);
    map.set("charlie", 4);
    map.set("alice", 5);
    
    for(let [key,value] of map){
    console.log(`${key} is the key and ${value} is the value.`)
    }
    
    for(let value of map.values()){
        console.log(`${value} is the value.`)
    }
    
    let ele = map.get("bob");
    console.log(ele);
    console.log(map.has("bob"));


#### RESTful API'S
    client and server are independent of each other.
    no client data is stored in server.- stateless.
    cacheable- clients can cache response to improve performance


#### == and ===  
    both are comparison operators
    == compares value and not types
    === compare value and types


#### let and const
    to define variables
    cannot reassign for const
    if it an object we can add or delete elements but cannot reassign

#### undefined and null
    undeifned-> when u define a variable and not assign a value
    null -> we assign to clean up
    typeof(undefined) is undefined but typeof(null) is object

#### arrow functions
    resolves ambuiguity of this keyword. Instead of assigning to window object, assigns to the current scope.

#### prototypal inheritance
    every object has a property called protoype, which can be used to add methods. When we create other object with these object.
    The newly created object automitically inherits the property of the parent but not by inluding in itself but by accessing the parent method.
    This makes the obejcts lighter

#### function declaration and function expression
    function declaration is a function , whereas function expression is an anonymous function saved in a varibale.


#### closure and how to use it
    Closures are nothing but functions with preserved data.
    simple example is a function that uses varibale declared outside is accessible inside.
    simple example:::
    var add = (first)=>{
        var addSecond = (second)=>{
            return first+second;
        }
        return addSecond;
    }
    var addClosure = add(1);
    
    console.log(addClosure(4)); //prserves one ad adds 4 to it



#### debugging
    in vs code we have to add configuration in launch.json and give path to the file.
    unit testing and integration test
    test single unit  in isolation.
    anything which is not in isolaion is integration test. (two or more modules).


#### Questions asked to me in interviews

1. Promises and Async await, lets say I have a promise add which return a promise, how to handle     in async await.
2. Const
3. Event loop - Explain how it works
4. Have you worked on any event handling in node.js -> my answer "No".
5. 




