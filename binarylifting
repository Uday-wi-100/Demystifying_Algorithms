#include <bits/stdc++.h>
using namespace std;
vector<int>lvl;
vector<vector<int>>mat; // size nlogn
int logn;
vector<vector<int>>adj;
void dfs(int node, int par){
    lvl[node]=lvl[par]+1;
    mat[node][0]=par;
    for(int i=1;i<logn;i++){
        mat[node][i]=mat[mat[node][i-1]][i-1];
    }
    for(auto x: adj[node]){
      if(x==par)continue;
      dfs(x,node);
    }
}
int lca(int u, int v){
    if(lvl[u]<lvl[v])swap(u,v);
    int diff=lvl[u]-lvl[v];
    for(int i=0;i<logn;i++){
        if(diff&(1<<i))u=mat[u][i];
    }
    if(u==v)return u;
    
    for(int i=logn-1;i>=0;i--){
      if(mat[u][i]!=mat[v][i]){
        u=mat[u][i];
        v=mat[v][i];
      }
    }
    return mat[u][0];
}
int main()
{
    int n;
    cin >> n;
    
}
