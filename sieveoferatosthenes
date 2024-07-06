#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    vector<int>arr(n);
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
    vector<bool>isprime(n+1,true);
    //segmented seive 
   for(int i=2;i*i<=n;i++){
    if(isprime[i]){
        for(int j=i*i;j<=n;j+=i)isprime[j]=false;
    }
   }

}
