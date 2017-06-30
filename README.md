####洗牌算法(打乱原数组)

#####Fisher-Yates-shuffle
时间复杂度:O(n^2);
思想:随机取出原数组中的一个数字,push进新数组同时把随机的数字从原数组中删除

- Math.random();
-  返回值:0~1的随机数 [0,1) 包括0不包括1
-  Math.floor(); 向下取整

```
function shuffle(arr){
	var result = [],
		random;
	while(arr.length > 0){
		random = Math.floor(Math.random() * arr.length);
		result.push(arr[random]);
		arr.splice(random,1);
	}
	return result;
}
```

#####Knuth-Durstenfeld Shuffle
时间复杂度:O(n);
思想:第i次随机取出原数组中的一个数字,与数组的第n-i+1个元素调换

```
function shuffle(arr){
	var length = arr.length,
		temp,
		random;
	while(length > 1){
		random = Math.floor(Math.random() * length);
		length --;
		temp = arr[length];
		arr[length] = arr[random];
		arr[random] = temp;
	}
	return arr;
}
```