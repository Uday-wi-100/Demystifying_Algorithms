#include <bits/stdc++.h>
using namespace std;
void find(vector< int> &a,  int sum, vector<int> &nums, int s, int e)
{
    if (s > e)
    {
        a.push_back(sum);
        return;
    }
    find(a, sum, nums, s + 1, e);
    find(a, sum + nums[s], nums, s + 1, e);
}
int minAbsDifference(vector<int> &nums, int goal)
{
    vector< int> a;
    vector< int> b;
    int n = nums.size();
    find(a, 0, nums, 0, n / 2);
    find(b, 0, nums, n / 2 + 1, n - 1);
    sort(b.begin(), b.end());
    int ans = INT_MAX;
    for (auto s : a)
    {
        int l = 0;
        int r = b.size() - 1;
        while (l <= r)
        {
            int mid = (l + r) / 2;
            int sum = s + b[mid];
            if (sum == goal)
                return 0;
            ans = min(ans, abs(sum - goal));
            if (sum > goal)
            {
                r = mid - 1;
            }
            else
            {
                l = mid + 1;
            }
        }
    }

    return ans;
}
int main()
{
    int n;
    cin >> n;
    vector<int> arr(n);
    for (int i = 0; i < n; i++)
    {
        cin >> arr[i];
    }
    int goal;
    cin >> goal;
    minAbsDifference(arr, goal);
}
