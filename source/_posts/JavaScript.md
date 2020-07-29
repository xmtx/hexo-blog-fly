---
title: js里数组常用的方法
date: 2020-07-27
author: xiaoming
top: true
cover: true
toc: true
mathjax: false
img:
coverImg: /medias/banner/0.jpg
password:
summary: js里数组的方法非常多，这里我列举出了工作中经常要用到的数组方法。
tags:
  - 前端
  - JavaScript
categories: JavaScript
---

# js 里数组常用的方法

###   concat方法
> **concat方法不会改变原数组，会返回一个拼接后的新数组。**

``` bash
var arr1= [1,2,3];
var arr2=[3,4];
arr1.concat(arr2);
console.log(arr1.length);  //3
console.log(arr1);   // [1,2,3]
console.log(arr2);   // [3,4]
console.log(arr1.concat(arr2));   // [1,2,3,3,4]
```

### join 方法
> **join方法不会改变原数组，join()方法将一个数组（或一个类数组对象）的所有元素根据传入的参数连接成一个字符串，并返回这个字符串。**

``` bash
var arr = [1,2,3,4,5];
arr.join(',');
console.log(arr);     // [1,2,3,4,5]
console.log(arr.join(','));    // '1,2,3,4,5'
```

### push方法和pop方法
> **push方法和pop方法会改变原数组，push方法用于向数组最末尾的位置添加新元素，pop方法用于删除数组最末尾的那个元素。**

``` bash
var arr = [1, 2, 3, 4, 5];
arr.push(6,7);
console.log(arr);   // [1,2,3,4,5,6,7]
console.log(arr.push(6,7));   //9
arr.pop();
console.log(arr);   //[1,2,3,4,5,6,7,6]
console.log(arr.pop());   //6
```

### unshift方法和shift方法
> **unshift方法和shift方法会改变原数组，unshift方法用于在数组第一个元素(下标为0)的前面的位置添加新元素，shift方法用于删除数组第一个元素(下标为0)的位置的元素。**

``` bash
var arr = [1, 2, 3, 4, 5];
arr.shift( );
console.log(arr);   // [2,3,4,5]
console.log(arr.length);   // 4
arr.unshift(6);
console.log(arr);   // [6,2,3,4,5]
console.log(arr.length);   // 5
```

### sort方法
> **sort方法会改变数组，用于对数组元素进行排序。默认采用正排序，即小的数排在前面。sort( )可以接受一个比较函数作为参数，以便我们指定哪个值在哪个值前面。比较函数接受两个参数，如果第一个参数位于第二个参数之前就返回负数，两参数相等返回0，如果第一个参数位于第二个参数之后就返回正数，这个比较函数适用于大多数数据类型，只要将其作为参数传给sort( )即可。**

``` bash
var arr=[0,1,5,10,15];
arr.sort();
console.log(arr);  // [0,1,10,15,5]

//sort接受一个比较函数作为参数
var arr = [21,1,3,45,2];
arr.sort( );
console.log(arr);   // [1,2,21,3,45]
arr.sort(function(a,b){
    if(a<b){
       return -1;
    }else if(a >b){
       return 1;
    }else{
       return 0;
    }
})
console.log(arr);   // [1,2,3,21,45]
```
### reverse 方法
> **reverse方法会改变数组，对数组元素倒置。**

``` bash
var arr=[21,1,3,45,2];
arr.reverse();
console.log(arr);   //[2,45,3,1,21]
```
### slice 方法
> **slice方法不会改变原数组，会返回一个截取后的新数组。一般它有两个参数，slice(A,B)表示从数组的下标为A的地方开始截取，截取到下标为B的元素处为止，截取的元素包含A下标对应的元素但不包含B下标对应的元素。**

``` bash
var arr = [1,2,3,4,5,6];
arr.slice(1,4);  //从数组arr的下标1开始截取到下标4为止，截取的元素包含下标1对应的元素不包含下标4对应的元素
console.log(arr);   // [1, 2, 3, 4, 5, 6]
console.log(arr.length);   // 6
console.log(arr.slice(1,4));   // [2, 3, 4]
```

### splice 方法
> **splice方法可用于删除元素、插入元素、替换元素，它会改变数组。splice方法用于删除时，只需要传入两个参数。比如splice(A,B)表示参数 A是删除第一项的位置，参数B是删除几项，并以数组形式返回被删除的部分。**

``` bash
var arr = [1, 2, 3, 4, 5];
console.log(arr.splice(1,3));  //1表示要删除的第一项是下标为1,删除截止下标为3的位置,返回被删除的部分[2, 3, 4]
console.log(arr);  // [1, 5]
```
> **splice方法用于插入元素时，只需要传入这三个参数:起始位置，0(要删除的项数)，要插入的项，插入时返回空数组。**

``` bash
var arr1 = [1,2,3,4,5];
console.log(arr1.splice(1,0,7,8));   // [] 插入时返回空数组
console.log(arr1);   // [1, 7, 8, 2, 3, 4, 5]
```

> **splice方法用于替换元素时，只需要传入这三个参数:起始位置，要替换的项数，要替换的项，返回被替换掉的数。**

``` bash
var arr2 = [1,2,3,4,5];
console.log(arr2.splice(1,1,7,8));   // [2] 返回被替换掉的数
console.log(arr2);   // [1, 7, 8, 3, 4, 5]
```

### findIndex 方法
> **findIndex方法返回满足条件的元素对应的索引下标值。**

``` bash
var arr = [10,3,4,5];
var a = arr.findIndex(function(item){
   return item == 3;
})
console.log(a);  //1
```

### find 方法
> **find方法不会改变原数组，返回数组中满足提供的测试函数的第一个元素的值。**

``` bash
function big(element){
   return element >= 2;
}
var arr = [1,2,3,2,5];
var arr1 = arr.find(big);
console.log(arr1);  //2
console.log(arr);  // [1,2,3,2,5]
```

### indexOf方法和lastIndexOf方法
> **indexOf是从数组下标为0的地方开始往后查找，lastIndexOf是从数组最后一项往前查找，如果没查找到就返回-1，不会改变数组，返回指定数值的数组下标。**

``` bash
var arr = [1, 2, 3, 2, 5];
console.log(arr.indexOf(2));  // 1 返回值为2的数组的下标
console.log(arr.indexOf(2,2));  // 3 第一个参数表示要查找的数，第二个参数表示查找起点位置的索引
console.log(arr.indexOf(6));  // -1
console.log(arr.lastIndexOf(2));  // 3 从数组的末尾开始向前查找，返回正序下标
console.log(arr.lastIndexOf(2,2));  // 1 从数组的末尾开始向前查找，返回正序下标
```
### forEach 方法
> **数组的forEach方法,回调函数的函数体没有返回值，也就是没有return. foreach的回调会让数组的每个元素都执行回调函数里函数体的东西。**

``` bash
var arr=[1,2,3];
arr.forEach(function(item){
   consolo.log(item);
   consolo.log("————");
}
结果如下:
1
__________

2
__________

3
__________
```

### some 方法
> **数组的some方法:数组的每个元素都会依次执行函数体里的东西，只要有一个满足条件表达式就会返回true，没有满足条件的就返回false。**

``` bash
var ages = [3，10，18，20]；
var ceshi = ages.some(function(age){
   return age>15
});
console.log(ceshi);  // true
```

### every 方法
> **数组的every方法:数组的每个元素都会依次执行函数体里的东西，所有元素全部满足条件表达式就会返回true，只要有一个不满足条件的就返回false。**

``` bash
var ages = [3，10，18，20]；
var ceshi = ages.every(function(age){
   return age>15
});
console.log(ceshi);   // false
```

### filter 方法
> **数组的filter方法:返回符合函数体里条件的新数组，它不会改变原数组。**

``` bash
var arr = [{id:1, flag:true},{id:2,flag:false},{id:3, flag:true}];
var newArr = arr.filter(obj => !obj.flag);  // 筛选出所有的flag为false的对象
console.log(newArr);   // [{id:2,flag:false}]
```

### map 方法
> **数组的map方法:返回一个新数组，新数组中的元素为原始数组中的每个元素调用函数处理后得到的值。看下例，找出下例里，数组对象里含有flag属性且flag值为true的对象。**

``` bash
var arr = [{id:1, flag:true},{id:2,flag:false},{id:3}];
var newArr = arr.map(ob =>{
    return “flag” in ob && ob.flag==true
} );
console.log(newArr);   // [{id:1,flag:true}]
```

### includes 方法
> **includes方法用来判断一个数组是否包含一个指定的值，返回 true或 false。**

``` bash
var arr = [1, 2, 3, 2, 5];
console.log(arr.includes(2));   // true
console.log(arr.includes(6));   // false
```

### toString 方法
> **toString方法不会改变原数组，返回一个字符串，表示指定的数组及其元素。**

``` bash
var arr = [1,2,3];
arr.toString();
console.log(arr.toString());   // '1,2,3'
console.log(arr);   // [1, 2, 3]
```

### reduce 方法
> **reduce方法不会改变原数组，迭代数组的所有项，然后构建一个最终返回的值，从数组的第一项开始，逐个遍历到最后。**

``` bash
var arr = [1, 2, 3, 2, 5];
// reduce方法有两个参数：在每一项上调用的函数和（可选的）作为归并基础的初始值
// reduce方法的函数接收 4 个参数：前一个值、当前值、项的索引和数组对象
// 这个函数返回的任何值都会作为第一个参数自动传给下一项
// 第一次迭代发生在数组的第二项上，因此第一个参数是数组的第一项，第二个参数是数组的第二项
var sum = arr.reduce(function(pre, cur, index, array) {
    return pre + cur;
}, 10)
console.log(arr);   // [1, 2, 3, 2, 5]
console.log(sum);   // 23
```
### reduceRight 方法
> **reduceRight方法不会改变原数组，迭代数组的所有项，从数组的最后一项开始，向前遍历到第一项。**

``` bash
var arr = [1, 2, 3, 2, 5];
var sum = arr.reduceRight(function(pre, cur, index, array) {
   return pre + cur;
}, 10)
console.log(arr);   // [1, 2, 3, 2, 5]
console.log(sum);   // 23
```

### flat 方法
> **数组的flat方法会按照一个可指定的深度递归遍历数组，并将所有元素与遍历到的子数组中的元素合并为一个新数组返回。语法如下：var newArray = arr.flat( [ depth ] ); depth指定要提取嵌套数组的结构深度，默认值为 1。返回值是一个包含将数组与子数组中所有元素的新数组。扁平化数组就是将多维数组转变为一维数组的过程。**

``` bash
var arr1 = [1, 2, [3, 4]];
console.log( arr1.flat());   // [1, 2, 3, 4]

var arr2 = [1, 2, [3, 4, [5, 6]]];
console.log( arr2.flat());   // [1, 2, 3, 4, [5, 6]]

var arr3 = [1, 2, [3, 4, [5, 6]]];
console.log( arr3.flat(2) );    // [1, 2, 3, 4, 5, 6]

//使用 Infinity，可展开任意深度的嵌套数组
var arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
console.log( arr4.flat(Infinity) );   // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```