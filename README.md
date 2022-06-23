# most-imp-interview-q.

// import { useState } from "react";
// const Count=()=>{
//     const[count, setCount] = useState(0);
//     return(
//         <div>
//             <h1>Functional component</h1>
//             <p1>{count}</p1>
//             <button onClick={()=>setCount(count+1)}>Hit Me!</button>
//         </div>
//     )
// }


// export default Count;


// class --------------------
 
// import React from "react";
// class Example extends React.Component{
//     constructor(props){
//         super(props);
//         this.state={
//             count:0
//         };
//     }
 
//     render(){
//         return(
//             <div>
//                 <h1>{this.state.count}</h1>
//                 <button onClick={()=>this.setState({count:this.state.count+1})}>Hit me!</button>
//             </div>
//         );
 
//     }
// }
// export default Example;
 
//useeffect-----------------
// import React, { useState, useEffect } from 'react';
 
// const App = () => {
//   const [message, setMessage] = useState('Hi there, how are you?');
 
//   useEffect(() => {
//     console.log('trigger use effect hook');
 
//     setTimeout(() => {
//       setMessage("I'm fine, thanks for asking.");
//     }, 1000)
//   })
 
//   return <h1>{message}</h1>
// };
 
// export default App;


//useMemo-------------
 
// import React, { useMemo, useRef, useState } from "react";
// const Count = () => {
//   const [count, setCount] = useState(0);
//   const [item, setItem] = useState(10);
//   // function multiCount() {
//       const memo=useMemo(function multiCount(){
//         return count*5;
//       },[count] )                        //   console.log("multiCount");// in this case count to hamara increase hoga pr jb hm item pr click krenge
//                                // to tb bhi hamari state unwantly update hoti hai..isko rokne ke liye use memo use krte hn
//   // return count * 5
//     // }
//   return (
//     <div>
//       <h1>Use memo</h1>
//       <h2>count is:{count}</h2>
//       <h2>item is:{item}</h2>
//       <h2>Multicount is:{memo}</h2>
//       <button onClick={() => setCount(count + 1)}>Count</button>
//       <button onClick={() => setItem(item * 10)}>Item</button>
//     </div>
//   );
// }
// export default Count;

//useRef
 
import React,{useRef} from 'react'
const Count=()=>{
 
  const inputRef=useRef(null)
  function handleInput(){
    inputRef.current.value="100";
    inputRef.current.style.color="red";
    inputRef.current.focus();
    inputRef.current.style.display="none";
 
  }
  return(
    <div>
      <h1>Use Ref</h1>
      <input type="text" ref={inputRef}/>
      <button onClick={handleInput}>handle This!</button>
    </div>
  )
}
export default Count;




-----------------------------------------------

//synchronously
 
// console.log("Program Starts");
// function f1(a,b){
//     const sum = (a+b);
//     console.log(sum)
// }
// f1(2,3);
// console.log("Program Ends");

//asynchronously---
// console.log("starts...");
// setTimeout(()=>{
//     console.log("miliseconds programs")
 
// },2000);
 
// console.log("finishs...");

//callback hell------------->>
 
// getData(function(a){
//     getMoreData(a, function(b){
//         getMoreData(b,function(c){
//             getMoreData(c,function(d){
//                 getMoreData(d,function(e){
 
//                 });
 
//             });
 
//         });
//     });
 
// });

//call----------
 
// var person1={
//     firstName:"jon",
//     lastName:"bob"
 
// };
// var person2={
//     firstName:"sammy",
//     lastName:"sinha"
// };
// function myfun(greeting){
//     console.log(greeting+ ' ' + this.firstName + ' '+ this.lastName);
// }
//  myfun.call(person1,'hello');
//  myfun.call(person2,'hello');
 
 //apply=============
 
// const person1={
//     firstName:"anoop",
//     lastName:"saini"
// };
 
// const person2={
//     firstName:"Himanshu",
//     lastName:"chauhan"
// };
 
// function say(greeting){
//     console.log(greeting+ ' ' +this.firstName+ ' '+this.lastName);
// }
// say.apply(person1,['hello']);
// say.apply(person2,['hello']);

//bind---------
const person1={
    firstName:"anoop",
    lastName:"saini"
};
 
const person2={
    firstName:"Himanshu",
    lastName:"chauhan"
};
 
function say(){
    console.log('hi'+ ' ' +this.firstName+ ' '+this.lastName);
}
var hello1=say.bind(person1);
var hello2=say.bind(person2);
 
hello1();
hello2();
 
---------------------
//ASync call
        //isme Redirecting phle ho rha h .this is not right way...
        //isko solve krne ke liye callback function aya..
 
        //callback-------------------
 
       function login(callback){
           setTimeout(()=>{
               console.log('login..');
               callback();
 
           },1000)
       }
 
login((callback)=>{
    console.log('redirecting');
 
});
 
//this is not right way her baar hme callback function pass krana pdta tha...
//iske resolve ke liye Promises aya..
 
//promises(resolve,reject);
//resolve ke saath---.then
//reject ke saath--.error
 
//promise---------------------
 
function login(){
    return new Promise((resolve,reject)=>{
        setTimeout(()=> {
        console.log('login...');
        resolve();
        //reject();
    },4000);
 
    });
}
login().then(()=>{
    console.log('redirecting');
 
})
.catch((err)=>{
   console.log('error...');
});
 
//async await----------------
let promise = new Promise((resolve,reject)=>{
    setTimeout(()=>{
        resolve("promise resolved...");
 
    },2000);
 
});
 
async func f(){
    let result= await promise;
    console.log(result);
    console.log("hello");
 
}
 
f();
 
//callback---
 
function hello1(callback){
    console.log("hii there");
    callback();
}
function hello2(){
    console.log("hello node");
}
 
hello1(hello2);
 
//currying 
const sum= (a)=>(b)=>(c)=>(d)=>a+b+c+d;
 const res = sum(2)(7)(9)(4);
 console.log(res);

 //closure//nested function--
 
 //inner function  access the out side function variable 
    //and  access the own local variable..and also access the global variable,,
    //but outsider function variable cant access the inner function variable 
    //it has 3 scope...
//     1- local Sope
// 2- outer function scope
// 3- global scope
// }
 
// 1 eg---//  var i=10;
//  function show(){
//     var j= 20;
//     console.log(i);
//     console.log(j);
//  }
//  show();

// 2-eg---//
 
function show (){
    var j= "j is a outer function variable.."
    console.log(j);
    function innerfunc(){
        var k="k is a inner function.."
        console.log(k);
        console.log(j);
    }
    innerfunc();
    //console.log(k);
 
show();
