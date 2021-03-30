#  Multi-view Website with React 

Technologies: HTML, CSS, JS, React, react-router, react context.

![Preview](https://github.com/breatheco-de/exercise-multi-view-react-collaborative-website/blob/master/preview.gif?raw=true)

Enough with the landing pages and single view projects, it is time to build our first web app. 

This is a collaborative project, the class will be separated in groups and each will create a piece of a multi-view website.

## 🌱  How to start this project

Do not clone this repository.

1. The first step to start coding is cloning the [react.js boilerplate](https://github.com/4GeeksAcademy/react-hello) on your local computer or opening it using gitpod.

a) If using Gitpod you can clone the boilerplate by [clicking here](https://gitpod.io#https://github.com/4GeeksAcademy/react-hello).

b) If working locally type the following command from your command line: `git clone https://github.com/4GeeksAcademy/react-hello`.

💡 Remember to create a new repository, update the remote (`git remote set-url origin <your new url>`), and upload the code to your new repository using `add`, `commit` and `push`.

2. Invite the other students as collaborators.

3. All the students clone the repository.

4. Divide the project workload in pieces and each group start working on its piece, 2 or max 3 people per group.

5. Install the dependencies `$ npm install`

6. Start the WebPack development server: `$ npm run start`


Done!

### Pieces/Groups:

- NavBar/Footer/Login View (Session) |
https://getbootstrap.com/docs/4.1/examples/carousel/ & https://getbootstrap.com/docs/4.1/examples/sign-in/
- Landing Page with Carousel (Products and Posts) | 
https://getbootstrap.com/docs/4.1/examples/carousel/
- Blog/Post View (Posts) | 
https://getbootstrap.com/docs/4.1/examples/blog/
- Store/Checkout (Products) | 
https://getbootstrap.com/docs/4.1/examples/product/ & https://getbootstrap.com/docs/4.1/examples/checkout/

### This project is meant to be done in two phases

#### Phase 1: set the views. React Router.

Each group will have to create the corresponding ***view component*** with dummy content (initially) and as many "smaller" components as needed.

Note: Think DRY (Don't repeat yourself) and declare only ***one*** component and use `props` to handle different content.

#### Phase 2: make the app dynamic. React Context.

Each group must use the Consumer given by the instructor in order to ***use the store to fill the content*** of the pieces:

- Navbar: must show the user's username and picture (assume the user is logged in).
- Login: show the login form.
- Landing Page: must show 3 posts in the carousel, 3 posts in a grid and 3 products in the products section.
- Blog: must show 6 blog posts
- Post View: must show clicked post details.

##### Using the Context

The `store` structure:

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

In order to have access to the global data, you'll have to import the context's main file: 

```jsx
import {Context} from '/path/to/store/appContext.jsx';

const MyView = () => {
    const { actions, store } = useContext(Context);
    //Then use the Consumer anywhere on the component
    return (<span> hello, {store.session.username} </span>);
}
```

Hint: you can see an example of the `Context.Consumer` in action at: 

```txt
demo.jsx
 - demoList.jsx
 - demoProducts.jsx
```


