# Breadth-First Search

> [!PDF|note] [[Slide 1.pdf#page=267&selection=0,0,0,20&color=note|Complex Social Network, p.267]]
> > Breadth-First Search
> 
> L'algoritmo permette di partire da un nodo, se questo ha dei vicini, questi verranno messi in una lista provvisoria, viene poi preso un nodo vicino e si fa lo stesso ragionamento, finché non è stato visitato ogni nodo. Il nodo selezionato viene segnato come visitato e si va avanti.

![[Slide 1.pdf#page=267&rect=93,44,262,216&color=note|Complex Social Network, p.267]]
## Implementazione
```python
def bfs(graph, start):
	visited, queue = set(), start[]
	while queue:
		vertex = queue.pop(0)
		if vertex not in visited:
			visited.add(vertex)
			queue.extend(set(graph[vertex]) - visited)
		print("Trovato nodo", vertex, "connesso a", graph[vertex])
	return visited
```

> [!PDF|note] [[Slide 1.pdf#page=309&selection=0,14,0,15&color=note|Complex Social Network, p.309]]
> > Shortest Paths
> 
> La label con lo 0 indica nodo di inizio. Si inizia accedendo a tutti i nodi vicini. Immagino che un nodo senza una distanza avrà l'infinito, successivamente viene aggiornato con la distanza del nodo precedente. Quelli irrangiugibili dal nodo start avrà il simbolo di infinito. Se al solito la somma delle distanze per arrivare ad un nodo si dimostra minore rispetto al percorso principale, con un altro percorso, questo verrà aggiornato. Tutte le distanze dei nodi, sono la somma delle distanze dal nodo 0. Come noti parte tutto dal nodo 0. Comanda lui
> 

![[Slide 1.pdf#page=310&rect=189,59,361,212&color=note|Complex Social Network, p.310]]
Algoritmo di Dijkstra, appartiene agli algoritmi SSSP, Singole Source Shortest Path.

## Implementazione

```python
def dijkstra(graph,src,dest,visited=[],distances={},pred={}):
	if not visited:
		distances[src]=0
	for neighbor in graph{src}:
		if neighbor not in visited:
			new_distance = distances[src] + graph[src][neighbor]
			if new_distance < distances.get(neighbor,float('inf)):
				distances[neighbor] = new_distance
				pred[neighbor] = src
				visited.append(src)
				unvisited={}
				for k in graph:
					if k not in visited:
						unvisited[k] = distances.get(k,float('inf))
					x=min(unvisited,key=unvisited.get)
				dijkstra(graph,x,dest,visited,distances,pred)
```
