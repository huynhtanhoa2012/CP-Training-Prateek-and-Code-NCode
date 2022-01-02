# Graphs

# 7.2 Graph Representation

## Adjacency Lists

```c++
vector <int> adj[10];

int nodes, edges;
cin >> nodes;      
cin >> edges;       
for(int i = 0;i < edges;++i)
{
    int x, y;
    cin >> x >> y;
    adj[x].push_back(y);
    adj[y].push_back(x);        
}
```


## Adjacency Matrix

```c++
bool A[10][10];

void initialize()
{
    for(int i = 0;i < 10;++i)
        for(int j = 0;j < 10;++j)
            A[i][j] = false;
}

int x, y, nodes, edges;
initialize();     
cin >> nodes;     
cin >> edges;    
for(int i = 0;i < edges;++i)
{
    cin >> x >> y;
    A[x][y] = true;     
}
```

# Depth First Search



## Breadth First Search

```c++
visited[x] = true;
distances[x] = 0;
q.push(x);

while(!q.empty()){
    int s = q.front(); q.pop();
    // process node s
    for (auto u : adj[s]) {
        if (visited[u]) continue;
        visited[u] = true;
        distance[u] = distance[s]+1;
        q.push(u);
    }
}
```

# Shortest Path
BFS helps to find shortest path in undirected graph.
