## Funzioni
Da qui in poi si diverte a spiegare le funzioni 
#### Esempio boh 
non ricordo cosa voleva sottolineare però !
```python
def iscontained(stringname, target):
	i = 0
	while(stringname[i] != target and i < len(stringname)):
		i++
	if(stringname[i] == target):
		return true
	else:
		return false
```

Sottolinea che in **iscontained(*stringname*, *target*)** 
I parametri sono parametri formali, una volta chiamata la funzione i parametri passati al loro posto saranno i parametri attuali, che saranno assegnati alla funzione

### Esempio boh 2 
Vuole sostituire un carattere in una stringa con un altro, le stringhe sono immutabili quindi è necessario crearne un'altra
```python
def modify(stringx,position,newchar):
	result= ''
	if(position < len(stringx)):
		result = result + stringx[:position] + newchar + stringx[position+1:]
	return result
```

Ok ora con una lista si nota che non essendo immutabile  è piuttosto easy! 
```python
def modify_list(mylist,position,item):
	if(position < len(stringx)):
		mylist[index] = item
	return mylist
```

## Moduli!
I moduli sono belli e li importi i n più modi, o con import, devondo però  usare il nome del modulo o con from potendo semplicemente utilizzare il nome del metodo importato dal modulo, esempi!
### Random
```python
import random
print(random.random())
```
Questo metodo è sicuro nel non creare confusione nei nomi dovessero esserci sovrapposizioni
## Math
```python
from math import sqrt
print(sqrt(49))
```
```python
from math import cos,sin
print(cos(1))
print(sin(1))
```
## Networkx
Il best modulo per quello che piace a lui