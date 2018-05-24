# 快速排序 \(Quick Sort\)

它采用了一种分治的策略。

分治法的基本思想是：将原问题分解为若干个规模更小但结构与原问题相似的子问题。递归地解这些子问题，然后将这些子问题的解组合为原问题的解。

利用分治法可将快速排序的分为三步：

1. 在数据集之中，选择一个元素作为”基准”（pivot）。
2. 所有小于”基准”的元素，都移到”基准”的左边；所有大于”基准”的元素，都移到”基准”的右边。这个操作称为
   [分区 \(partition\) 操作](http://en.wikipedia.org/wiki/Quicksort)
   ，分区操作结束后，基准元素所处的位置就是最终排序后它的位置。
3. 对”基准”左边和右边的两个子集，不断重复第一步和第二步，直到所有子集只剩下一个元素为止。

![](http://bubkoo.qiniudn.com/Sorting_quicksort_anim.gif)

图片来自维基百科

分区是快速排序的主要内容，用伪代码可以表示如下：

```
function partition(a, left, right, pivotIndex)
     pivotValue := a[pivotIndex]
     swap(a[pivotIndex], a[right]) // 把 pivot 移到結尾
     storeIndex := left
     for i from left to right-1
         if a[i] < pivotValue
             swap(a[storeIndex], a[i])
             storeIndex := storeIndex + 1
     swap(a[right], a[storeIndex]) // 把 pivot 移到它最後的地方
     return storeIndex // 返回 pivot 的最终位置
```

首先，把基准元素移到結尾（如果直接选择最后一个元素为基准元素，那就不用移动），然后从左到右（除了最后的基准元素），循环移动小于等于基准元素的元素到数组的开头，每次移动 storeIndex 自增 1，表示下一个小于基准元素将要移动到的位置。循环结束后 storeIndex 所代表的的位置就是基准元素的所有摆放的位置。所以最后将基准元素所在位置（这里是 right）与 storeIndex 所代表的的位置的元素交换位置。要注意的是，一个元素在到达它的最后位置前，可能会被交换很多次。

一旦我们有了这个分区算法，要写快速排列本身就很容易：

## 实例分析

现有数组 arr = \[3,7,8,5,2,1,9,5,4\]，分区可以分解成以下步骤：

1.首先选定一个基准元素，这里我们元素 5 为基准元素（基准元素可以任意选择）：

![](/assets/屏幕快照 2018-05-24 下午8.31.06.png)

2.将基准元素与数组中最后一个元素交换位置，如果选择最后一个元素为基准元素可以省略该步：

![](/assets/屏幕快照 2018-05-24 下午8.31.39.png)

3.从左到右（除了最后的基准元素），循环移动小于基准元素 5 的所有元素到数组开头，留下大于等于基准元素的元素接在后面。在这个过程它也为基准元素找寻最后摆放的位置。循环流程如下：

循环 i == 0 时，storeIndex == 0，找到一个小于基准元素的元素 3，那么将其与 storeIndex 所在位置的元素交换位置，这里是 3 自身，交换后将 storeIndex 自增 1，storeIndex == 1：

![](/assets/屏幕快照 2018-05-24 下午8.32.21.png)

循环 i == 3 时，storeIndex == 1，找到一个小于基准元素的元素 4：

![](/assets/屏幕快照 2018-05-24 下午8.32.50.png)  
交换位置后，storeIndex 自增 1，storeIndex == 2：

![](/assets/屏幕快照 2018-05-24 下午8.33.22.png)

循环 i == 4 时，storeIndex == 2，找到一个小于基准元素的元素 2：

![](/assets/屏幕快照 2018-05-24 下午8.33.57.png)

交换位置后，storeIndex 自增 1，storeIndex == 3：

![](/assets/屏幕快照 2018-05-24 下午8.34.34.png)

循环 i == 5 时，storeIndex == 3，找到一个小于基准元素的元素 1：

![](/assets/屏幕快照 2018-05-24 下午8.35.35.png)

交换后位置后，storeIndex 自增 1，storeIndex == 4：

![](/assets/屏幕快照 2018-05-24 下午8.36.05.png)

循环 i == 7 时，storeIndex == 4，找到一个小于等于基准元素的元素 5：

![](/assets/屏幕快照 2018-05-24 下午8.36.44.png)

交换后位置后，storeIndex 自增 1，storeIndex == 5：

![](/assets/屏幕快照 2018-05-24 下午8.37.13.png)

3.循环结束后交换基准元素和 storeIndex 位置的元素的位置：

![](/assets/屏幕快照 2018-05-24 下午8.37.45.png)

引用[维基百科](http://en.wikipedia.org/wiki/Quicksort)上的一张图片：

![](http://bubkoo.qiniudn.com/Partition_example.svg.png)

## JavaScript 语言实现

```
function quickSort(arr) {　　
    if (arr.length <= 1) {
        return arr;
    }　　
    var pivotIndex = Math.floor(arr.length / 2);　　
    var pivot = arr.splice(pivotIndex, 1)[0];　　
    var left = [];　　
    var right = [];　　
    for (var i = 0; i < arr.length; i++) {　　　　
        if (arr[i] < pivot) {　　　　　　
            left.push(arr[i]);　　　　
        } else {　　　　　　
            right.push(arr[i]);　　　　
        }　　
    }　　
    return quickSort(left).concat([pivot], quickSort(right));
}
```

> 上面简单版本的缺点是，它需要Ω\(n\)的额外存储空间，也就跟归并排序一样不好。额外需要的存储器空间配置，在实际上的实现，也会极度影响速度和高速缓存的性能。
>
>                               摘自[维基百科](http://en.wikipedia.org/wiki/Quicksort)

按照[维基百科](http://en.wikipedia.org/wiki/Quicksort)中的原地\(in-place\)分区版本，实现快速排序方法如下：

```
function quickSort(array) {
	// 交换元素位置
	function swap(array, i, k) {
		var temp = array[i];
		array[i] = array[k];
		array[k] = temp;
	}
	// 数组分区，左小右大
	function partition(array, left, right) {
		var storeIndex = left;        
		var pivot = array[right]; // 直接选最右边的元素为基准元素
		for (var i = left; i < right; i++) {
			if (array[i] < pivot) {
				swap(array, storeIndex, i);
				storeIndex++; // 交换位置后，storeIndex 自增 1，代表下一个可能要交换的位置
			}
		}
		swap(array, right, storeIndex); // 将基准元素放置到最后的正确位置上
		return storeIndex;
	}
	function sort(array, left, right) {
		if (left > right) {
			return;
		}
		var storeIndex = partition(array, left, right);
		sort(array, left, storeIndex - 1);
		sort(array, storeIndex + 1, right);
	}
	sort(array, 0, array.length - 1);
	return array;
}
```



## 参考文章

[https://zh.wikipedia.org/wiki/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F](https://zh.wikipedia.org/wiki/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F)

[http://bubkoo.com/2014/01/12/sort-algorithm/quick-sort/](http://bubkoo.com/2014/01/12/sort-algorithm/quick-sort/)

[http://www.ruanyifeng.com/blog/2011/04/quicksort\_in\_javascript.html](http://www.ruanyifeng.com/blog/2011/04/quicksort_in_javascript.html)





