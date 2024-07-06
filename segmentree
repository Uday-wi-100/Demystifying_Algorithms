#include <bits/stdc++.h>
using namespace std;
int mod =(int)1e9+7;
void build(int s, int e, int node, vector<long long int>&tree, vector<int>&arr){
    if(s==e){
        tree[node]=arr[s];
        return;
    }
    int mid=(s+e)/2;
    build(s,mid,2*node,tree, arr);
    build(mid+1, e, 2*node+1, tree, arr);
    tree[node]=tree[2*node]+tree[2*node+1];
}
void update(int index, int val, int s, int e, int node, vector<int>& arr, vector<long long int>&tree){
    if(s==e){
        arr[s]=val;
        tree[node]=val;
        return;
    }
    int mid=(s+e)/2;
    if(index<=mid){
        update(index,val,s,mid,2*node,arr,tree);
    }
    else{
        update(index,val,mid+1,e,2*node+1,arr,tree);
    }
    tree[node]=tree[2*node]+tree[2*node+1];
    return;
}
long long int query(int qs, int qe, int s, int e, int node, vector<long long int>&tree){
    if(e<qs || s>qe)return 0;
    if(s>=qs && e<=qe)return tree[node];
    int mid=(s+e)/2;
    long long int left=query(qs,qe,s,mid,2*node, tree);
    long long int right=query(qs,qe,mid+1,e,2*node+1,tree);
    return (left+right);
}
int main(){
    int n,m;
    cin>>n>>m;
    vector<int>arr(n,0);
    int x;
    for(int i=0;i<n;i++){cin>>x;arr[i]=x;}
    vector<long long int>tree(4*n,0);
    build(0,n-1,1,tree,arr);
    int op,a,b;
    while(m--){

        cin>>op;
        cin>>a>>b;
        if(op==1){
            update(a,b,0,n-1,1,arr,tree);
        }
        if(op==2){
            cout<<query(a,b-1,0,n-1,1,tree)<<"\n";
        }
    }
    
    return 0;
}
