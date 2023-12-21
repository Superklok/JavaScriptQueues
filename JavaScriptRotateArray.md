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

## Explanation:

I've written a function called `rotate` which takes in an array `nums` and a number `k` as parameters. The function is used to rotate the elements of the array `nums` to the right by `k` positions.
<br/>

This function consists of two `for` loops. The first `for` loop starts from the last index of the array `nums` and iterates backwards until it reaches the first index. Inside this loop, each element at index `i` is assigned to the element at index `i + k` in the array `nums`. This effectively shifts the elements to the right by `k` positions.
<br/>

After the first `for` loop, the elements of the array `nums` have been shifted to the right, but the first `k` elements are duplicates of the original elements.
<br/>

The second `for` loop starts from `k - 1` and iterates backwards until it reaches `0`. Inside this loop, the last element of the array `nums` is removed using the `pop` method, and the removed element is assigned to the current element at index `j` in the array `nums`. This effectively replaces the duplicate elements at the beginning of the array with the original elements.
<br/>

Once the second `for` loop completes, the array `nums` will contain the elements rotated to the right by `k` positions.
<br/>

It's important to note that this function modifies the original array `nums` in place and does not return a new array.
<br/>
<br/>