https://leetcode.cn/problems/binary-search/

给定一个 n 个元素有序的（升序）整型数组 nums 和一个目标值 target  ，写一个函数搜索 nums 中的 target，如果目标值存在返回下标，否则返回 -1。

示例 1:
```
输入: nums = [-1,0,3,5,9,12], target = 9     
输出: 4       
解释: 9 出现在 nums 中并且下标为 4     
```
示例 2:
```
输入: nums = [-1,0,3,5,9,12], target = 2     
输出: -1        
解释: 2 不存在 nums 中因此返回 -1        
```
提示：

你可以假设 nums 中的所有元素是不重复的。
n 将在 [1, 10000]之间。
nums 的每个元素都将在 [-9999, 9999]之间。

### error1: have no return values

### error2: update left index should add 1, same reason, right should deduce 1

### error3: forget to initialize the left and right values

我的代码：
```
class Solution {
public:
    int search(vector<int>& nums, int target) {
	int left =0, right = nums.size() - 1, middle;
     middle = (left + right)/2;
     while(left <= right)
     {
     	if (nums[middle] == target)
         {
         	//cout << target<< "出现在 nums 中并且下标为" << middle << endl;
         	return  middle;
         }
         if (nums[middle] <= target)
         {
         	left = middle + 1;
         }
         if (nums[middle] >= target)
         {
         	 right = middle - 1;
         }
         middle = (left + right)/2;
    }
    
        //cout << target<< "不存在 nums 中因此返回-1" << endl;
        return -1;
        
    }
}; 
```
