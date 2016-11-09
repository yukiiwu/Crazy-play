# 数组

## 数组定义
***
 一个存储元素的线形集合collection，元素可以通过索引来任意存取，索引通常是数字，用来计算元素之间存储位置的偏移量
## 数组使用
***
##### 创建数组*（ []操作符被认为效率最高 ）*
	var example0 = [];
	var example1 = ['[]操作符','直接量','new Array()'];
	var example2 = new Array();
	var example3 = new Array(1,2,3);
	var example4 = new Array(3);
##### 字符串生成数组
	var exampleStr = 'guolan wangchao xiaobo';
	var exampleArr = exampleStr.split(' ');
	for(var i = 0;i < exampleArr.length;i++){
		console.log(exampleArr[i]);
	}
## 存取函数
 这些函数返回目标数组的某种变体
***
##### 查找元素
	1. indexOf() 返回第一个与参数相同的元素的索引
	2. lastIndexOf() 返回最后一个与参数相同的元素
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	console.log(exampleArr.indexOf('guolan'));
	console.log(exampleArr.lastIndexOf('guolan'));
	console.log(exampleArr.indexOf('guolanmeizi'));
##### 数组的字符串表示
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	console.log(exampleArr.join('笑'));
	console.log(exampleArr.toString());
##### 已有数组创建新数组
	1. concat() 合并多个数组创建一个新数组
	2. splice() 截取一个数组的子集创建一个新数组 * 还有其它用法 *
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr1 = exampleStr.split(' ');
	var exampleArr2 = ['hehe','haha','heihei'];
	var exampleArrNew1 = exampleArr1.concat(exampleArr2);
	var exampleArrNew2 = exampleArr1.splice(1,2);
	console.log(exampleArrNew1.join('傻'));
	console.log(exampleArrNew2.join('哭'));
## 可变函数
 改变数组内容
***
##### 添加元素
	push() 添加到数组末尾
	unshift() 添加到数组头
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	exampleArr.push(6,7);
	exampleArr.unshift(1,2);
	console.log(exampleArr.join('傻'));
##### 删除元素
	pop() 删除并返回第一个元素
	shift() 删除并返回最后一个元素
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	exampleArr.pop();
	exampleArr.shift();
	console.log(exampleArr.join('傻'));
##### 从中间添加或删除
	splice() 起始位置 元素个数 添加元素
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	exampleArr.splice(1,2,'meizi','hanzi');
	console.log(exampleArr.join('傻'));
	var arr = ['xiaozi'];
	exampleArr.splice(1,0,arr);
	console.log(exampleArr.join('傻'));
##### 数组排序
	reverse() 元素顺序进行翻转
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	console.log(exampleArr.join('傻'));
	exampleArr.reverse();
	console.log(exampleArr.join('傻'));
	sort() 默认按照字典排序，可以传入函数更改排序方式
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	console.log(exampleArr.join('傻'));
	exampleArr.sort();
	console.log(exampleArr.join('傻'));
	var arr = [100,3,1,2];
	console.log(arr.join('傻'));
	arr.sort();
	console.log(arr.join('傻'));
	function compare(num1,num2){
		return num1 - num2;
	}
	arr.sort(compare);
	console.log(arr.join('傻'));
## 迭代器方法
***
##### forEach() 接收一个函数作为参数，对数组中的每一个元素使用该函数
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	var forEachTest = function(item){
		console.log(item + '帅气美丽十足')
	}
	exampleArr.forEach(forEachTest);
##### every() 接收一个返回值为booble类型的函数，如果对于所有的元素，该函数均返回true，则该方法返回true
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	var everyTest = function(item){
		return item.indexOf('o') > -1;
	}
	exampleArr.every(everyTest);
##### some() 接收一个返回值为booble类型的函数，只要有一个元素使用该函数均返回true，则该方法返回true
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	var someTest = function(item){
		return item.indexOf('i') > -1;
	}
	exampleArr.some(someTest);
##### reduce() 接收一个函数，从一个累加值开始，不断对累加值和数组的后续元素调用该函数，直到数组的最后一个元素，最后返回累加值   ** reduceRight() 从右开始执行 **
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	var reduceTest = function(val,item){
		return val +'和 '+ item;
	}
	exampleArr.reduce(reduceTest);
##### map() 和 forEach()有点像，返回一个新的数组
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	var mapTest = function(item){
		return '和'+ item;
	}
	var a = exampleArr.map(mapTest);
	console.log(exampleArr.join('-'));
	console.log(a.join('-'));
##### filter() 接收一个返回值为booble类型的函数，返回一个新数组，新数组包含所有使用该函数后结果为true的元素
	var exampleStr = 'guolan wangchao xiaobo guolan';
	var exampleArr = exampleStr.split(' ');
	var filterTest = function(item){
		return item.indexOf('i') > -1;
	}
	var b = exampleArr.filter(filterTest);
	console.log(b.join('-'));
## 多维数组
	var exampleArr = [[1,2],[1,2,3],[1,2,3,4]];
	for(var i = 0;i < exampleArr.length;i++){
		for(var j = 0;j < exampleArr[i].length;j++){
			console.log(exampleArr[i][j]);
		}
		console.log("\n");
	}
## 对象数组
	var exampleArr = [
		{"a":1,"b":2},
		{"a":3,"b":4},
	];
## 对象中的数组
	var exampleObj = {
		"a":1,
		"b":[1,2]
	}