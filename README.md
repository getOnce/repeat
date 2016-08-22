# repeat
求数组内重复次数最多的元素，并返回次数
var arr = [2, 2, 2, 2, 4, 5, 4, 4];
	function countRepeatMax(arr){
		var arr = arr,
			temp = {},
			max = 0,
			v = [];
		if(arr.length == 0){
			max = 0;
		}
		else if(arr.length == 1){
			max = 1;
			v = arr[0];
		}else{
			arr.forEach(function(value, index, array){
				if(!temp[value]){
					temp[value] = 1;
				}else{
					temp[value]++;
				}
				if(max == temp[value]){
					v.push(value);
				}else if(max < temp[value]){
					max = temp[value];
					v = [value];
				}

			})
		}
		return {
			count: max,
			key: v 
		}
	}
	countRepeatMax(arr);
