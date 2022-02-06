# how to merge two arrays on javascript

First, this method to merge two lists is expecting you have an array of
objects like this

```javascript
const arr1 = [
  {id:1,name:"sai"},
  {id:2,name: "King"}
];
const arr2 = [
    {id:1,age:23},
    {id:2,age:24}
];
```

The function implementation is quite simple and use functional
properties of javascript itself.

This function implementation is using `id` property to merge, but you
can change as you please.

```javascript
function mergeArrayObjects(arr1,arr2){
  return arr1.map((item,i)=>{
     if(item.id === arr2[i].id){
         //merging two objects
       return Object.assign({},item,arr2[i])
     }
  })
}

console.log(mergeArrayObjects(arr1,arr2));

/* output
     [
      {id: 1, name: "sai", age: 23},
      {id: 2, name: "King", age: 24}
     ]
*/
```
