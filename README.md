# $q

$q是根据angular源码提取出来的，不敢自专

<h3>使用方式</h3>

>非模块化加载

```javascript
function async(){
	var d = $q().defer();
	var timer = setInterval(function() {
		if (t) {
			d.resolve(t)
		} else {
			d.reject(new Error('出错1'))
		}
		clearInterval(timer)
	}, 500)
	return d.promise;
}
```


> 模块化加载

```javascript
define(['domready', 'zepto', '$q', 'angular'], function(doc, $, $q, angular) {
	doc(function() {
		function async(){
			var d = $q.defer();
			var timer = setInterval(function() {
				if (t) {
					d.resolve(t)
				} else {
					d.reject(new Error('出错1'))
				}
				clearInterval(timer)
			}, 500)
			return d.promise;
		}
	})
})
```