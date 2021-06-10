# Black Jack
Juego de Black Jack sencillo como ejemplo de funcionamiento de JavaScript 

Este juego utiliza de forma asincrónica llamados a una API que se llama 
[Deck of Cards](https://deckofcardsapi.com/). En esa página encontrara la documentación de la misma.

### Ejemplo de traer el mazo
Para traer el código del mazo, utilizamos una función asincrónica de JavaScript

```JavaScript 
async function traerMaso(){
  const response = await fetch('https://deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1', 
    {
        method: 'GET',
    });
    const res = await response.json();
    return res;       
}

```

```JavaScript
traerMaso().then(dato => {
    maso = dato.deck_id;
	});
```

### Ejemplo de traer carta
```JavaScript
async function darCarta(cant){
  const response = await fetch('https://deckofcardsapi.com/api/deck/'+maso+'/draw/?count='+cant, 
    {
        method: 'GET',
    });
    const res = await response.json();
    return res;       
}
```
La variable maso, es una variable global donde guardamos previamante el código del mazo



