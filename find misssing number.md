
class Solution{
    public:
      int missingNumber(vector<int>nums)
      {
        int n = nums.size();
        int zor1 = 0;
        int zor2 = 0;
        for(int i=0;i<n;i++)
        {
            zor1 = zor1^nums[i];
            zor2 = zor2^(i+1);
        }
        zor2^ n;
        return zor1^zor2;
      }
}; 
