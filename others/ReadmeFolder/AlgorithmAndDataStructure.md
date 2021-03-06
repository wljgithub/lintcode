# 排序

### 冒泡排序

时间复杂度:O(n^2)

冒泡排序每次从第一个元素开始，比较相邻的两个元素，在比较一轮后即可将最大的元素上浮到最右边。

假设一共有n个数，当n-1个数排序完成后，剩下的一个数自然就不用排序了。

所以一共需要比较n-1趟，每次移动到第n-i个元素,套两层循环即可实现

```go
func bubbleSort(arr []int) []int {
	for i := 0; i < len(arr); i++ {    				//外层循环为比较的趟数 
		for j := 1; j < len(arr)-i; j++ {			// 内存循环为每次移动到第几个元素
			if arr[j] < arr[j-1] {
				arr[j], arr[j-1] = arr[j-1], arr[j]
			}
		}
	}
	return arr
}
```
解释一下内循环为什么每次只需要移动到第j个元素，而不是每次都移动到最后一个元素。因为每次循环一趟后，就将一个元素排序就位了，来张图更直观一些

![123](https://github.com/wljgithub/leetcode-/blob/master/resource/bubbleSort.jpg)

### 归并排序

时间复杂度:O(n^2)
