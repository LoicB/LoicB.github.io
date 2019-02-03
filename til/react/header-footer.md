Creating a Header and a Footer in React is very simple:

Create a file for the Header:

```react.js
import React, { Component } from 'react';

class Header extends Component {
  render() {
    return(
    );
  }
}

export default Header;
```

And one for the Footer:
```react.js
import React, { Component } from 'react';

class Footer extends Component {
  render() {
    return(
    );
  }
}

export default Footer;
```

Then in the main component, includes the two tags:
```react.jsimport Header from './HeaderComponent';
import Footer from './FooterComponent';
. . .
class Footer extends Component {
  render() {
    return(
      <Header />
      . . .
      <Footer />
    );
  }
}
```
