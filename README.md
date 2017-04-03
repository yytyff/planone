### 1.过滤如下数组，只保留正数
```
var arr = [3,1,0,-1,-3,2,-5]
function filter(arr){
   for (var i = 0; i < arr.length; i++){
      if ( arr[i] <= 0 ) {
        arr.splice(i, 1);
        filter(arr);
      }
  }
}
filter(arr)
console.log(arr) // [3,1,2]
```
### 2.过滤如下数组，只保留正数，原数组不变，生成新数组
```
var arr = [3,1,0,-1,-3,2,-5]
function filter(arr){
     var newArr = [];
     for (var i = 0; i < arr.length; i++){
         if ( arr[i] > 0 ) {
              newArr.push(arr[i]);
         }
     }
    return newArr;
}
var arr2 = filter(arr)
console.log(arr2) // [3,1,2]
console.log(arr)  // [3,1,0,-1,-2,2,-5]
```
### 3.深拷贝函数，两种实现方式
```
第一种：
function copy(obj){
	var newObj = {};
	for (var key in obj){
		if(obj.hasOwnProperty(key)){
			if(typeof obj[key] ==='number' || typeof obj[key] ==='boolean'
                        || typeof obj[key] ==='string'|| obj[key] === undefined||
                         obj[key] === null){
			newObj[key] = obj[key];
		}else{
			newObj[key] = copy(obj[key]);
		}
	}	
}
	return newObj;
}
第二种：
JSON.stringify(obj)
JSON.parse()
JSON.parse(JSON.stringify(obj))
function copy(obj){
        var newObj = JSON.parse(JSON.stringify(obj));
        return newObj;
 }
 ```
