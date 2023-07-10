# DSAAssign2

# Q1

```
function arrayPairSum(nums) {
    nums.sort((a, b) => a - b);
    let sum = 0;
    
    for (let i = 0; i < nums.length; i += 2) {
        sum += nums[i];
    }
    
    return sum;
}


```

# Q2

```
function distributeCandies(candyType) {
    const uniqueCandies = new Set(candyType);
    const maxCandies = candyType.length / 2;
    
    return Math.min(uniqueCandies.size, maxCandies);
}

```

# Q3

```

function findLHS(nums) {
    const frequencyMap = new Map();
    let longestSubsequenceLength = 0;
    
    for (let num of nums) {
        frequencyMap.set(num, (frequencyMap.get(num) || 0) + 1);
    }
    
    for (let [num, frequency] of frequencyMap) {
        if (frequencyMap.has(num + 1)) {
            longestSubsequenceLength = Math.max(
                longestSubsequenceLength,
                frequency + frequencyMap.get(num + 1)
            );
        }
    }
    
    return longestSubsequenceLength;
}

```

# Q4

```
function canPlaceFlowers(flowerbed, n) {
    let count = 0;
    let i = 0;
    
    while (i < flowerbed.length) {
        if (
            flowerbed[i] === 0 &&
            (i === 0 || flowerbed[i - 1] === 0) &&
            (i === flowerbed.length - 1 || flowerbed[i + 1] === 0)
        ) {
            flowerbed[i] = 1;
            count++;
        }
        
        if (count >= n) {
            return true;
        }
        
        i++;
    }
    
    return false;
}

```

# Q5

```
function maximumProduct(nums) {
    nums.sort((a, b) => a - b);
    
    const n = nums.length;
    const product1 = nums[n - 1] * nums[n - 2] * nums[n - 3];
    const product2 = nums[0] * nums[1] * nums[n - 1];
    
    return Math.max(product1, product2);
}

```

# Q6

```
function search(nums, target) {
    let left = 0;
    let right = nums.length - 1;
    
    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        
        if (nums[mid] === target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    
    return -1;
}


```


# Q7

```
function isMonotonic(nums) {
    let increasing = true;
    let decreasing = true;
    
    for (let i = 1; i < nums.length; i++) {
        if (nums[i] > nums[i - 1]) {
            decreasing = false;
        }
        
        if (nums[i] < nums[i - 1]) {
            increasing = false;
        }
    }
    
    return increasing || decreasing;
}

```

# Q8

```
function minDifference(nums, k) {
    if (nums.length <= 1) {
        return 0;
    }
    
    nums.sort((a, b) => a - b);
    const n = nums.length;
    
    const score1 = nums[n - 1] - nums[0];
    const score2 = nums[n - 2] - nums[1];
    const score3 = nums[n - 3] - nums[2];
    const score4 = nums[n - 4] - nums[3];
    
    return Math.min(score1, score2, score3, score4);
}


```






