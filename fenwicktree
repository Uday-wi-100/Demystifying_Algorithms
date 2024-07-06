#include<bits/stdc++.h>
using namespace std;
int mod =(int)1e9+7;
vector<long long int>bit;
int n;
long long int query(long long int idx){
    long long int ans=0;
    while(idx>0){
        ans+=bit[idx];
        idx-=idx&(-idx);
    }
    return ans;
}
void update(long long int idx, long long int val){
    while(idx<=n){
        bit[idx]+=val;
        idx+=idx&(-idx);
    }
}
int main(){
   ios_base::sync_with_stdio(false);
   cin.tie(NULL);
   cout.tie(NULL); 
   cin>>n;
   long long int arr[n];
   vector<vector<long long int>>v;
   for(int i=0;i<n;i++){
       cin>>arr[i];
       v.push_back({arr[i],i});
   }
   sort(v.begin(),v.end());
   for(int i=0;i<n;i++){
       arr[i]=v[i][1]+1;
   }
   bit=vector<long long int>(n+1,0);
   vector<long long int>left(n,0);
   vector<long long int>right(n,0);
   for(int i=0;i<n;i++){
  
       left[i]=query(n)-query(arr[i]);
       update(arr[i], 1);
   }
   for(int i=0;i<=n;i++){
       bit[i]=0;
   }
   for(int i=n-1;i>=0;i--){
       right[i]=query(arr[i]-1);
       update(arr[i],1);
   }
   long long int ans=0;
   for(int i=0;i<n;i++){
       ans+=left[i]*right[i];
   }
   cout<<ans<<"\n";
    return 0;
}
