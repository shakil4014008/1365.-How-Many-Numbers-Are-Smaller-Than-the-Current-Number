# 1365.-How-Many-Numbers-Are-Smaller-Than-the-Current-Number
easy leetcode with efficient solution

````py
class Solution:
     
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:


        """
        algorithm: count algorithm 
        1. initialize count array with 0 with top element size
        2. update count of each number of those index
        3. sum of all previous numbers of that array
        4. append the previous numbers to the ans array 
        T = O(n), S = O(1)  
        """

        count = [0] * (max(nums) + 1) #---1
        ans  = []

        for item in nums: #---2
            count[item] +=  1
        
        for i in range(1, len(nums)): # ---3
            count[i] += count[i-1]

        for i in range(len(count)): 
            if i == 0: ans.append(0)
            else: ans.append(count[i-1])

        return ans




Brute force: 
def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:
        dict  = {}
        ans = []
        for i in range(len(nums)):
            temp  = 0 
            for j in range(len(nums)):
                if nums[i] > nums[j] and i != j:                   
                    temp += 1
            ans.append(temp)   
        return ans 
````
