# Lecture 8
![](./%D0%91%D0%B5%D0%B7%20%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F%20(2).png)
# Table of content
## 1.Synchronous
## 2.Asynchronous
## 3.New promise
## 4.Try/Catch
## 5.Async/Await
># What is Synchronous in js?
- Most of code is synchronous;
- Synchronous codeo line by line khonda meshavad;
- har iak line muntazir meshavad to lini peshina tamom shavad;
- agar synchronouns codho muntazir snavad block meshavad;
># What is Asynchronous in js?
- Asynchronous codho badi taski mo ba onho medihem bad run meshavad
- Asinchronous coodho block nameshavad
- kori mo muntazir nameshavad to asynchronous codho korashonrotamom kunad bad davom dihad agar asynchronous codho loading doshra boshad codoho davom medihad
- Avval synchronous konho khonda meshavad bad asynchronous codho
># Asynchronous codho in js istifoda meshavad tavasuti
## 1.Callbacks
## 2.promises
## 3.async/aways syntax 
# What is callbcks in asynchronous js:
>## Callback function krhoi hudro to akhir mekunad to vakte ki taski dodagimon dar callbackho asynchronous tamom nashavad
## 1.setTimeout : - dar parametrash callback va millisecund megirad
```
console.log("one");
setTimeout(() => {
    console.log("two");
},3000);
console.log("three");
output : 
one
three
after 3 second : two
```
## 2.setInterval : - ba misli soat kor mekunad takror raftan megirad
```
console.log("one");
setInterval(() => {
    console.log("two");
},2000);
console.log("three");
output  :
one
three 
badi 2 secund iakbori nishon meta namesta;
```
>## Promises in js is a good way to fidn is your asynchronous codho sucsesfull completed or not
## A promises may have on eor three staes
- Pending : loadin graftan
- Fufilled : dar holati khub galtidan
- Rejected : dar holati bad galtidan
## baroi sokhtani promise mo objecti new promise ro istifods mebarem new Promise 2 parametr kabul mekunad resolve , reject;agar khub kor mekunad dar resolve megaltad agar ashbka brora dar rejected
```
function newPromises() {
    return new Promise((resolve, reject) => {
        fetch(url)
        .then(response => response.json())
        .then(data => resolve(data))
        .catch(erorr => reject(erorr))
    })
}
newPromises(url)
.then(data => console.log(data))
.catch(erorr => console.log(erorr))
output 
your url backend object
``` 
>## async awayt niz iakrohi khub baroi ioftani kori shumo in rohi naw meboshad
```
async function fetchData(params) {
    try {
        let response = await fetch(url)
        let data = await response.json()
        console.log(data);
    } catch (error) {
        console.log(error);
    }
}
fetchData(url)
```