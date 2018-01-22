# js-questions
Collected JS questions


### Call vs Apply
#### call()
It is used to call a function with a given this value and 
arguments provided individually.
#### apply()
It is used to call a function with a given this value and 
arguments provided as an array.

```javascript
var MyNumber = {
  getTypeOfNumber : function(number){
    var type = (number % 2 === 0) ? "Even" : "Odd"; return type;
  },
  getTypeOfAllNumber : function (){
    var result = [],
        i=0;
    
    for (; i < arguments.length; i++){
      var type = MyNumber.getTypeOfNumber.call(null,arguments[i]);
      result.push(type);
    }
    return result;
  }
};

var typeOfNumber = MyNumber.getTypeOfNumber.call(null,21); 
console.log(typeOfNumber);

var typeOfAllNumber = MyNumber.getTypeOfAllNumber.apply(null,[2,4,5,78,21]);
console.log(typeOfAllNumber);

```
Odd
[ 'Even', 'Even', 'Odd', 'Even', 'Odd' ]
```
