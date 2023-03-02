# JavaScript Rotate Array

## Challenge:

Given an integer array `nums`, rotate the array to the right by `k` steps, where `k` is non-negative.

### 1<sup>st</sup> Example:

`Input: nums = [1,2,3,4,5,6,7], k = 3`
<br/>
`Output: [5,6,7,1,2,3,4]`
<br/>
`Explanation: rotate 1 steps to the right: [7,1,2,3,4,5,6]`
<br/>
`rotate 2 steps to the right: [6,7,1,2,3,4,5]`
<br/>
`rotate 3 steps to the right: [5,6,7,1,2,3,4]`

### 2<sup>nd</sup> Example:

`Input: nums = [-1,-100,3,99], k = 2`
<br/>
`Output: [3,99,-1,-100]`
<br/>
`Explanation: rotate 1 steps to the right: [99,-1,-100,3]`
<br/>
`rotate 2 steps to the right: [3,99,-1,-100]`

### Constraints:

`1 <= nums.length <= 10⁵`
<br/>
`-2³¹ <= nums[i] <= 2³¹ - 1`
<br/>
`0 <= k <= 10⁵`

## Solution:

`const rotate = (nums, k) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`for(let i = nums.length - 1; i >= 0; i--) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`nums[i + k] = nums[i];`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`for(let j = k - 1; j >= 0; j--) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`nums[j] = nums.pop();`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
`};`
<br/>
<br/>