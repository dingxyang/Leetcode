# 2数之和

```js
var twoSum = function(nums, target) {
    for(let i=0;i<nums.length;i+=1) {
        for(let j=0;j<nums.length;j+=1) {
            if (nums[i] + nums[j] === target)  return [i, j]
        }
    }
};
```


```js
var twoSum = function(nums, target) {
    const cacheMap = new Map();
    for(let i=0;i<nums.length;i+=1) {
       const diff = target - nums[i];
       if(cacheMap.has(diff)) return [cacheMap.get(diff), i];
       cacheMap.set(nums[i], i);
    }
};
```

```js
var twoSum = function(nums, target) {
    let obj = {};
    for(let i=0;i<nums.length;i+=1) {
       const diff = target - nums[i];
       if(obj[diff]) return [obj[diff]-1, i];
       obj[nums[i]] = i+1;
    }
};
```
