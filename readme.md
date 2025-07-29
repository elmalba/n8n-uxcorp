## Pasos para comenzar

 **Ingresa al sitio oficial**  
   Abre tu navegador y ve al siguiente enlace:  
   👉 [https://n8n.io/](https://n8n.io/)

 **Crea una cuenta nueva**  
   Haz clic en el botón `Get started` ubicado en la página principal.
   ![1](n8n_inicio.png)  

 **Regístrate**  
   Llena el formulario de registro con tus datos. Asegúrate de definir un **nombre de usuario** que utilizarás para ingresar posteriormente.
![1](n8n_formulario.PNG)
 ![1](n8n-usuario.PNG)  

 ## Crear un nuevo flujo en n8n

Haz clic en el botón **"New Workflow"** 

 ![1](nuevo_flujo.png)  


Haz clic en el ícono **`+`** ubicado en la parte superior izquierda para agregar un nuevo nodo.

![1](+.png)  


## 🔧 Pasos para construir el flujo

### 1. Crear el nodo From 

- Agrega un nodo **On form submission**.

- Selecciona: "Workflows Finishes".
- Path: cambiar el path por que necesitemos

![Paso 1 - Webhook](1.png)

---

### 2. Agrega un nodo **Sheet**

Este nodo se debe configurar  :

- Las credenciales
- Las hoja
- Las columnas

![Paso 2 - 2](2.png)
![Paso 3 - 3](3.png)

### 2. Agrega un nodo **Gmail**

Este nodo se debe configurar  :

- Las credenciales
- El destinatario 
- El asunto 
- El mensaje

![Paso 4 - 4](4.png)


## Si todo esta bien deberia ver se asi

![Paso 5 - 5](5.png)

## Siguiente caso obtener datos desde google sheet



### 1. Agrega un nodo **Sheet**

Este nodo se debe configurar  :

- Las ya estan agregadas
- Las hoja
- Las columnas
- El filtro

![Paso 1 ](7.png)

### 2. Agrega un nodo **Code**

Este nodo genera:
- Un numero aleatorio

```javascript
for (const item of $input.all()) {
  item.json.RandomPokemon = Math.floor(Math.random() * 1025) + 1;
}
return $input.all();
```
![Paso 2 ](8.png)

### 3. Nodo HTTP Request - Consultar PokéAPI

- **Método:** `GET`  
- **URL:**

```bash
https://pokeapi.co/api/v2/pokemon/{{ $json.RandomPokemon }}
```
⚙️ Este paso permite obtener los datos del Pokémon generado aleatoriamente.

![Paso 3 ](9.png)



### 2. Agrega un nodo **Gmail**

Este nodo se debe configurar  :

- Las credenciales
- El destinatario 
- El asunto 
- El mensaje

![Paso 4 ](10.png)



### Bonus track ###

Agregar ia ?
![Paso 4 ](faq.png)