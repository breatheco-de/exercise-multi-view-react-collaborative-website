# Sitio Web con multiples vistas con React 

Tecnologías: HTML, CSS, JS, React, react-router, react context.

![Preview](https://github.com/breatheco-de/exercise-multi-view-react-collaborative-website/blob/master/preview.gif?raw=true)

Basta con las páginas de destino y los proyectos de vista única, es hora de crear nuestra primera aplicación web.

Este es un proyecto colaborativo, la clase se dividirá en grupos y cada uno creará una parte de un sitio web de vistas múltiples.

## 🌱  Cómo iniciar este proyecto

No clones este repositorio.

1. El primer paso para comenzar a codificar es clonar el [react.js boilerplate](https://github.com/4GeeksAcademy/react-hello) en tu compjutador local o con Gitpod.

a) Si usas Gitpod puedes clonar el boilerplate [clic aquí](https://gitpod.io#https://github.com/4GeeksAcademy/react-hello).

b) Si trabajas localmente, escribe el siguiente comando en tu terminal: `git clone https://github.com/4GeeksAcademy/react-hello`.

💡 Importante: Recuerda crear un nuevo repositorio, actualiza el remoto (`git remote set-url origin <your new url>`), y guarda tu código en tu nuevo repositorio usando `add`, `commit` y `push`.

2. Invita a otros estudiantes como colaboradores.

3. All the students clone the repository.

4. Divide el trabajo del proyecto en partes y cada grupo puede empezar a trabajar en su pieza, 2 o 3 personas máximo por grupo.

5. Instala las dependencias `$ npm install`

6. Inicia el servidor WebPack development: `$ npm run start`

¡Hecho!

### Partes/Grupos:

- NavBar/Footer/Login View (Session) |
https://getbootstrap.com/docs/4.1/examples/carousel/ & https://getbootstrap.com/docs/4.1/examples/sign-in/
- Landing Page with Carousel (Products and Posts) | 
https://getbootstrap.com/docs/4.1/examples/carousel/
- Blog/Post View (Posts) | 
https://getbootstrap.com/docs/4.1/examples/blog/
- Store/Checkout (Products) | 
https://getbootstrap.com/docs/4.1/examples/product/ & https://getbootstrap.com/docs/4.1/examples/checkout/

### Este proyecto está destinado a realizarse en dos fases.

#### Fase 1: configurar las vistas. Reaccionar enrutador.

Cada grupo tendrá que crear el **componente vista**  correspondiente con contenido ficticio (inicialmente) y tantos componentes "más pequeños" como sea necesario.

Nota: Piensa DRY (Don't repeat yourself), declara solo **un** componente con contenidoy usa ```props``` para manejar contenido diferente.

#### Fase 2: Dinamizar la aplicación: React Context.

Cada grupo usa el Consumer dado por el profesor para **para usar el store para ponerle el contenido** a las partes:

- Navbar: debe mostrar el nombre de usuario y la imagen del usuario (suponga que el usuario está conectado).
- Login: Mostrar el formulario de inicio de sesión.
- Landing Page: debe mostrar 3 publicaciones en el carrusel, 3 publicaciones en una cuadrícula y 3 productos en la sección de productos.
- Blog: debe mostrar 6 entradas de blog
- Post View: debe mostrar los detalles de la publicación pulsada.

##### Usando el Context

Estructura de `store`:

```javascript
store = {
    posts:[
        {
            title: 'This is a World Post',
            content: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32. The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from "de Finibus Bonorum et Malorum" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.',
            date: 'Oct 15',
            tags: ['World'],
            author: 'Denise A',
            image: 'https://venturebeat.com/wp-content/uploads/2015/09/Screen-Shot-2015-09-03-at-13.43.14-e1441259794560.png',
            thumbnail: 'https://media.takealot.com/covers_tsins/50045787/50045787-1-listgrid.jpg'
        },
        ...
    ],
    
    products:[
        {
            name: 'Vintage Phone',
            image: 'https://images.pexels.com/photos/9165/hand-top-white-old.jpg?auto=compress&cs=tinysrgb&h=500&w=500',
            price: 300.67,
            description: 'Embrace nostagia with a brand new flip phone'
        },
        ...
    ],
    
    session:{
        username:'Rigo',
        email: 'rigocodes@gmail.com',
        loggedIn: false
    },
    
    cart:[
        {
            name: 'Polaroid Camera',
            image: 'https://images.pexels.com/photos/191160/pexels-photo-191160.jpeg?auto=compress&cs=tinysrgb&h=500&w=500',
            price: 129.99,
            description: 'Get instant photos'
        },
        ...
    ]
};
```

Para tener acceso a los datos globales, deberás importar el archivo principal del contexto:


```jsx

// importando app context
import {Context} from '/path/to/store/appContext.jsx';


const MyView = () => {
    const { actions, store } = useContext(Context);
    //Luego usa el Consumer en cualquier parte del componente
    return (<span> hello, {store.session.username} </span>);
}
```

Sugerencia: puede ver un ejemplo de ```Context.Consumer``` en acción en:

```
demo.jsx
 - demoList.jsx
 - demoProducts.jsx
```

