#include <bits/stdc++.h>
using namespace std;

bool DFSV [1000] = {false};

void DFScan(int node, vector<vector<int>>& graph){
    if(DFSV[node])
        return;
    //  to print each element of the graph:
    //  cout<<node<<endl;
    DFSV[node] = true;
    for(auto child : graph[node]){
        DFScan(child, graph);
    }
}



int main()
{

    ios_base::sync_with_stdio(false);

    //  building the graph:

    int n, m; cin>>n>>m;

    vector<vector<int>> graph(n);
    for(int i=0; i<m; i++){
        int u, v; cin>>u>>v;
        graph[u].push_back(v);
        graph[v].push_back(u);
    }

    //  grouping:

    int groups [n];
    fill(groups, groups + n, -1);

    int c = 0;
    for(int i=0; i<n; i++){
        if(!DFSV[i]){
            DFScan(i, graph);
            for(int j=0; j<n; j++){
                if(groups[j] == -1 && DFSV[j] == 1){
                    groups[j] = c;
                }
            }
            c++;
        }
    }
    
    //  printing results:

    for(int i=0; i<n; i++){
        cout<<i<<"->"<<groups[i]<<endl;
    }

}
