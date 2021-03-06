# styled-css-modules-component

[![NPM version][npm-image]][npm-url]
[![Build Status][travis-image]][travis-url]
[![Dependency Status][david_img]][david_site]

> Build styled component with css-modules

`styled-component` forces developers use clearer way to add styles to the components which looks great to me, but there are still some difficult unsolved issues in CSS-in-JS area, even after `radium`, `aphrodite` and a lot of libraries involved.

`css-modules` is a good choice for getting modularization without being as cutting-edge as the CSS-in-JS approaches. You can just write css and get full superpower from PostCSS ecosystem!

## Install

```sh
$ npm install styled-css-modules-component
```

> Note: You have to setup your own css-modules environment.

## Usage

### Basic

`styles.css`:

```css
.title {
  font-size: 1.5em;
  text-align: center;
  color: palevioletred;
}

.wrapper {
  padding: 4em;
  background: papayawhip;
}
```

This creates two react components, `<Title>` and `<Wrapper>`:

```js
import React from 'react';
import styled from 'styled-css-module-components';

import styles from './styles.css';

// Create a <Title> react component that renders an <h1> which is
// centered, palevioletred and sized at 1.5em
const Title = styled.h1(styles.title);

// Create a <Wrapper> react component that renders a <section> with
// some padding and a papayawhip background
const Wrapper = styled.section(styles.wrapper);
```

You render them like so:

```jsx
// Use them like any other React component – except they're styled!
<Wrapper>
  <Title>Hello World, this is my first styled css modules component!</Title>
</Wrapper>
```

![screencapture-localhost-3000-1486314996688](https://cloud.githubusercontent.com/assets/3382565/22628156/1581950e-ec0a-11e6-9a15-4ed2b7d3d816.png)

Checkout full examples [here](https://github.com/chentsulin/styled-css-modules-component/blob/master/examples/basic/components/App.js).


### Passed props

`styles.css`:

```css
.input {
  font-size: 1.25em;
  padding: 0.5em;
  margin: 0.5em;
  color: palevioletred;
  background: papayawhip;
  border: none;
  border-radius: 3px;
}
```

Styled components pass on all their props. This is a styled `<input>`:

```js
import React from 'react';
import styled from 'styled-css-modules-components';

import styles from './styles.css';

// Create an <Input> component that'll render an <input> tag with some styles
const Input = styled.input(styles.input);
```

You can just pass a `placeholder` prop into the `styled-css-modules-component`. It will pass it on to the DOM node like any other react component:

```jsx
// Render a styled input with a placeholder of "@chentsulin"
<Input placeholder="@chentsulin" type="text" />
```

![2017-02-06 1 23 26](https://cloud.githubusercontent.com/assets/3382565/22628206/f20db8fe-ec0a-11e6-9980-36a6090cb3e1.png)

Checkout full examples [here](https://github.com/chentsulin/styled-css-modules-component/blob/master/examples/passed-props/components/App.js).


## Third-party components

`styles.css`:

```css
.link {
  color: palevioletred;
  display: block;
  margin: 0.5em 0;
  font-family: Helvetica, Arial, sans-serif;
}
```

The above also works perfectly for styling third-party components, like a `react-router` `<Link />`!

```js
import styled from 'styled-components';
import { Link } from 'react-router';

const StyledLink = styled(Link)(styles.link);
```

```jsx
<Link to="/">Standard, unstyled Link</Link>
<StyledLink to="/">This Link is styled!</StyledLink>
```

![2017-02-07 1 50 27](https://cloud.githubusercontent.com/assets/3382565/22679409/e86ab850-ed3c-11e6-81cf-3d06dfb36aab.png)

Checkout full examples [here](https://github.com/chentsulin/styled-css-modules-component/blob/master/examples/third-party-components/components/App.js).


## Animations

Directly supported by CSS.


## Overriding component styles & Theming

See the long discusses at [css-modules #147](https://github.com/css-modules/css-modules/issues/147).


## React Native

Not supported.


## Relevant Projects

- [styled-component](https://github.com/styled-components/styled-components)
- [css-literal-loader](https://github.com/4Catalyzer/css-literal-loader)


## License

MIT © [C.T. Lin](https://github.com/chentsulin/styled-css-modules-component)

[npm-image]: https://badge.fury.io/js/styled-css-modules-component.svg
[npm-url]: https://npmjs.org/package/styled-css-modules-component
[travis-image]: https://travis-ci.org/chentsulin/styled-css-modules-component.svg
[travis-url]: https://travis-ci.org/chentsulin/styled-css-modules-component
[coveralls-image]: https://coveralls.io/repos/chentsulin/styled-css-modules-component/badge.svg?branch=master&service=github
[coveralls-url]: https://coveralls.io/r/chentsulin/styled-css-modules-component?branch=master
[david_img]: https://david-dm.org/chentsulin/styled-css-modules-component.svg
[david_site]: https://david-dm.org/chentsulin/styled-css-modules-component

