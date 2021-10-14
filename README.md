# Detect-cycle-in-a-graph

 bool checkForCycle(int s,int v,vector<int> adj[] ,vector<int> &vis){
        queue<pair<int,int>> q;
        vis[s]=1;
        q.push({s,-1});
        while(!q.empty()){
            int node = q.front().first;
            int prev = q.front().second;
            q.pop();
            for(auto it : adj[node]){
                if(!vis[it]){
                    vis[it]=1;
                    q.push({it,node});
                }
                else if(prev!=it){
                    return true;
                }
            }
        }
        return false;
        
    }
	bool isCycle(int V, vector<int>adj[])
	{
	    vector<int> vis(V,0);
	    for(int i = 0;i < V;i++){
	        if(!vis[i]){
	            if(checkForCycle(i,V,adj,vis)) return true;
	            
	        }
	    }
	    return false;
	}
