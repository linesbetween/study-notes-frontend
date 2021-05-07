1.  [CSS and SCSS Stylesheets](https://www.smashingmagazine.com/2020/05/styling-components-react/#css-and-stylesheets)  
    This involves using separate stylesheets like our conventional way of styling our HTML websites either with CSS or a CSS preprocessor called **SASS**.
2.  [CSS Modules](https://www.smashingmagazine.com/2020/05/styling-components-react/#css-modules)  
    A CSS Module is a CSS file in which all class names and animation names are scoped locally by default.
3.  [`styled-components`](https://www.smashingmagazine.com/2020/05/styling-components-react/#styled-components)  
    styled-components is a library for React and React Native that allows you to use component-level styles in your application that are written with a mixture of JavaScript and CSS using a technique called **CSS-in-JS**.
4.  [JSS](https://www.smashingmagazine.com/2020/05/styling-components-react/#jss)  
    JSS is an authoring tool for CSS which allows you to use JavaScript to describe styles in a declarative, conflict-free and reusable way. It can compile in the browser, server-side or at build time in Node.
	
### 1\. CSS And SASS Stylesheets
```js
import './Box.css';

  <div className="Box">
    <p className="Box_content"> Styling React Components </p>
  </div>
```
Pros
1.  It is **much more popular than the rest** 
2.  **Caching & Performance**  
    Standard CSS files are easy for the browser to optimize for, caching the files locally for repeat visits, and ultimately giving performance wins.
3.  **Un-opinionated and Universal**  
4.  **Quickly Iterate A New Design**  
5.  **CSS** **Frameworks** 
	Bootstrap, Bulma, Semantic UI, Materialize.

Cons
1.  **Readability**  
    If not properly structured, a CSS or SASS stylesheet can become long and difficult to navigate through as the application becomes complex.
2.  **Legacy CSS Can Live On For Years**


### 2. CSS Modules
is a CSS file in which all class names and animation names are scoped locally by default. 
each React component is provided with its own CSS file

```css
//Box.css
 :local(.container) {
   margin: 40px;
   border: 5px dashed pink;
 }
 :local(.content) {
   font-size: 15px;
   text-align: center;
 }
```

`styles` here is an object that contains the styles we created in `Box.css`
```javascript
import React from 'react';
import styles from './Box.css';

const Box = () => (
  <div className={styles.container}>
    <p className={styles.content}> Styling React Components </p>
  </div>
);

export default Box;
```

When using webpack, you can add the loader and also include the module to your `webpack.config.js` in other to make CSS modules work with Webpack.

```javascript
test: /\.css$/,
loader: 'style!css-loader?modules&importLoaders=1&localIdentName=[name]__[local]___[hash:base64:5]' 
}
```

cons
1.  Extra build tools (e.g. webpack).
2.  Mixing CSS Modules and global CSS classes is cumbersome.
3.  When a `Reference` is made to an undefined CSS Module, it resolves to undefined without a warning.
4.  Using the `styles` object whenever constructing a `className` is compulsory.
5.  Only allows usage of `camelCase` **CSS** class names.

### 3. Styled-components
-   First, we need to install `styled-components` library by running `npm install styled-components --save`.
-   We then need to import the styled component library into our component by writing `import styled from 'styled-components';`.
-   Now we can create a variable by selecting a particular HTML element where we store our style keys.
-   Then we use the name of our variable we created as a wrapper around our JSX elements.
```javascript
import React from 'react';
import styled from 'styled-components';

const Box = styled.div`
  margin: 40px;
  border: 5px black;
`;

const Content = styled.p`
  font-size: 16px;
  text-align: center;
`;

const Box = () => (
  <Box>
    <Content> Styling React Components </Content>
  </Box>
);

export default Box;
```

Pros
1.  **Consistency**  
    easy for you to publish a React component to NPM. These components can be customised through props and/or extending via `styled(Component)` and no clashing with CSS selectors.
2.  **Sass Syntax Out-Of-The-Box**  
3.  **Dynamic Styling**  
    You can make use of props to dynamically change the styles
4.  **Theming**  
    Using React’s Context API, styled-components offers a `ThemeContext` that can you can pass a theme object directly to
	
Cons
1.  **Performance**  
    styled-components converts all of the style definitions in your React component into plain CSS at build time and the inject everything into the `<style>` tags in the head of your `index.html` file. This affects performance in the sense that it is not only increasing the size of our HTML file which can have an impact on the load time, but there is also no way to chunk the output CSS either.
	
### 4 JSS
 use JavaScript to describe styles in a declarative, conflict-free and reusable way. It can compile in the browser, server-side or at build time in Node
 
 #### BENEFITS OF JSS

1.  **Local Scoping**  
    JSS supports local scoping, taking it to the next level by automating scoping, which leads to a high level of predictability.
2.  **Encapsulation**  
    Encapsulation facilitates maintenance and eliminates errors, as you can modify all component-related code and style in the same place, without having to worry about unexpectedly changing other parts of the application.
3.  **Reusability**  
    Components are reusable, so you only have to write them once, then you can run them everywhere while maintaining their styling too.
4.  **Dynamic Styling**  
    You can make use of props to dynamically change the styles in any way that feels natural to anyone comfortable with React.

#### SHORTCOMINGS OF JSS

1.  **Learning Curve**  
    Learning JSS can be very tricky especially frontend developers that are already used to writing traditional CSS.
2.  **Extra Layer of Complexity**  
    Putting a CSS-in-JS library into use adds an extra layer to your React application, which can sometimes be unnecessary.
3.  **Code Readability**  
    Custom or Automatically generated selectors can be very difficult to read especially when using your browser devtools to debug.