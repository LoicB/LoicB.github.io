# Functional Stateless Components

When a component does not need to store data, normally resulting with an empty constructor, it is possible to use a Functional Stateless Components.

So instead for writing:
```javascript
class Book extends Component {
  render() {
    return (
      <div>The book title is: {this.props.book.title}</p>
      );
  }
}
```

you can write:
```javascript
function Book({book}) {
  return (
    <div>The book title is: {this.props.book.title}</p>
  );
}
```

or:
```javascript
const Book = (props) => {
  return (
    <div>The book title is: {props.book.title}</p>
  );
}
```
