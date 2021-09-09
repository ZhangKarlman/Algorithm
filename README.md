# Algorithm
题目描述：在一个长度为 n 的数组里的所有数字都在 0 到 n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字是重复的。也不知道每个数字重复几次。请找出数组中任意一个重复的数字。例如，如果输入长度为 7 的数组 {2, 3, 1, 0, 2, 5, 3}，那么对应的输出是第一个重复的数字 2
解题思路
代码：首先给定数组arr[] = {2, 3, 0, 1, 3}。因为数组中最大的数是n-1，那就一个萝卜一颗坑。从0号下标位置开始，0号元素为2，不等于0，交换0号和2号位置，数组变为：{0, 3, 2, 1, 3}。再比较0号位置，下标和值相等，往后走到1号下标元素为3，不等于1，交换1号和3号，变成：{0, 1, 2, 3, 3}。再继续，下标来到4号位置，发现元素下标与值不相等，比较4号和3号下标位置，发现元素相等，返回3即可
#include <iostream>
#include<vector>
using namespace std;
int Chongfu(vector<int> &nums){
    int n = nums.size();
    if (n <= 1) return 0;
    for(int i = 0; i < n; ++i){
        while(nums[i] != i){
            if(nums[i] == nums[nums[i]]){
                return nums[i];
            }
            swap(nums[i],nums[nums[i]]);
        }
    }
    return -1;
}
int main(){
    vector<int> nums = {2,3,1,0,2,5};
    int a = Chongfu(nums);
    cout << a << endl;
    return 0;
}
给定一个含有数字和运算符的字符串，为表达式添加括号，改变其运算优先级以求出不同的结果。
