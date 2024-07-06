//sum using square root decomposition 
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    vector<int>arr(n);
    for(int i=0;i<n;i++)cin>>arr[i];
    int t=sqrt(n)+1;
    vector<int>b(t,0);
    for(int i=0;i<n;i++){
        b[i/t]+=arr[i];
    }
    int q;
    cin>>q;
    while(q--){
        int l,r;
        cin>>l>>r;
        int ans=0;
        for(int i=l;i<=r;){
            if(i%t==0 && i+t-1<=r){
                ans+=b[i/t];
                i+=t;
            }
            else{
                ans+=arr[i];
                i++;
            }
        }
        cout<<ans<<"\n";
    }
    return 0;
}
