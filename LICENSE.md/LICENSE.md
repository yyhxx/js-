<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<script>
			//push,pop,unshift,shift
			//sort,concat
			/*var arr = [1,2,3,4,5,6,7,8,9]
			//乱序
			arr.sort(function(){
				return Math.random()>0.5? -1 : 1
			})
			document.write(arr)*/
			
			//快速排序
			var arr=[12,85,4,6981,23,44,7,238,48975,1,896];
			function quicksort(arr){
			//判断输入的是不是数组
				if(Array.isArray(arr)){
					//加结束条件
					if(arr.length <= 1){
						return arr
					}
					var left = []
					var right = []
					var minIndex = Math.floor(arr.length/2)
					//把中间默认为最小的值截取出来
					var minValue = arr.splice(minIndex,1)
					for(var i = 0;i < arr.length;i++){
						if(minValue > arr[i]){
							left.push(arr[i])
						}
						else{
							right.push(arr[i])
						}
					}
					return quicksort(left).concat(minValue,quicksort(right))
					
				}
				else{
					console.log("这不是一个数组")
					}
			}
			//alert(quicksort(arr))
			
			//选择排序
				var arr=[12,85,4,6981,23,44,7,238,48975,1,896];
				var min;
				var tmp;
				for(var i = 0;i < arr.length -1 ;i++){
					min = i;
					for(var j = i + 1;j < arr.length;j++){
						if(arr[j] < arr[min]){
							min = j;
						}
					}
					tmp = arr[i]
					arr[i] = arr[min]
					arr[min] = tmp
				}
			console.log(arr)
			//冒泡排序
			var arr=[12,85,4,6981,23,44,7,238,48975,1,896];
			for(var i = 0;i < arr.length - 1;i++){
				for(var j = 0;j < arr.length - 1 - i;j++){
					if(arr[j] > arr[j + 1]){
						tmp = arr[j] 
						arr[j] = arr[j + 1]
						arr[j + 1] = tmp
					}
				}
			}
			console.log(arr);
			//选择排序
			var arr=[12,85,4,6981,23,44,7,238,48975,1,896];
			var tmp;
			var min;
			for(var i = 0; i < arr.length - 1;i++){
				min = i
				for(var j = i + 1;j < arr.length;j++){
					if(arr[j] < arr[min]){
						min = j
					}
				}
				tmp = arr[min]
				arr[min] = arr[i]
				arr[i] = tmp;
			}
			console.log(arr)
			//数组去重 filter方法
			var arr = [115, 22, 22, 554, 95, 884, 56, 115, 22]
			var newArr = arr.filter(function(item,index){
				return arr.indexOf(item) == index
			})
			console.log(newArr)
			//map()方法
			var arr = [115, 22, 22, 554, 95, 884, 56, 115, 22]
			var newArr= []
			arr.map(function(item,index){
				if(arr.indexOf(item) == index){
					newArr.push(item)
				}
			})
			console.log(newArr)
			//push方法
			var arr = [115, 22, 22, 554, 95, 884, 56, 115, 22]
			var newArr= []
			for(var i = 0;i < arr.length;i++){
				for(var j = 0;j <arr.length;j++){
					if(arr[i] == arr[j]){
						break
					}
				}
					 if(arr[i] != newArr[j]){
						newArr.push(arr[i])
					}
			}
			console.log(newArr)
		</script>
	</body>
</html>
