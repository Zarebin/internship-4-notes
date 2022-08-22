#session11#
##JS##
- with the release of ES5, JS added strict mode as an opt-in mechanism for encouraging better JS programs
- Most strict mode controls are in the form of early errors
- you shouldnt think about strict mode as restriction . it is a guide that help you to write code better and have a js engines have a chance of running code efficiently

##React##
- we should render listes inside a components.
- A “key” is a special string attribute you need to include when creating lists of elements
- Keys help React identify which items have changed, are added, or are removed
- The best way to pick a key is to use a string that uniquely identifies a list item among its siblings.
- We don’t recommend using indexes for keys if the order of items may change. This can negatively impact performance and may cause issues with component state
**correct Key Usage**
``
function ListItem(props) {
  // Correct! There is no need to specify the key here:  return <li>{props.value}</li>;}

function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    // Correct! Key should be specified inside the array.    <ListItem key={number.toString()} value={number} />  );
  return (
    <ul>
      {listItems}
    </ul>
  );
}
``
**Keys Must Only Be Unique Among Siblings**
``
  const sidebar = (    <ul>
      {props.posts.map((post) =>
        <li key={post.id}>          {post.title}
        </li>
      )}
    </ul>
  );
  const content = props.posts.map((post) =>    <div key={post.id}>      <h3>{post.title}</h3>
      <p>{post.content}</p>
    </div>
  );
  return (
    <div>
      {sidebar}      <hr />
      {content}    </div>
  );
}

const posts = [
  {id: 1, title: 'Hello World', content: 'Welcome to learning React!'},
  {id: 2, title: 'Installation', content: 'You can install React from npm.'}
];
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Blog posts={posts} />)
``
**Embedding map() in JSX**
``
function NumberList(props) {
  const numbers = props.numbers;
  return (
    <ul>
      {numbers.map((number) =>        <ListItem key={number.toString()}                  value={number} />      )}    </ul>
  );
}
``

# css ##
## [:target](https://www.w3schools.com/cssref/sel_target.asp)
The :target CSS pseudo-class represents a unique element (the target element) with an id matching the URL's fragment.


## [:target-within](https://developer.mozilla.org/en-US/docs/Web/CSS/:target-within)

`
/* Selects a <div> when one of its descendants is a target */
div:target-within {
  background: cyan;
}
`

## [:current](https://docs.w3cub.com/css/:current)
The :current CSS pseudo-class selector is a time-dimensional pseudo-class that represents the element, or an ancestor of the element, that is currently being displayed. For example in a video with captions which are being displayed by WebVTT.
## [:past](https://docs.w3cub.com/css/:past)
The :past CSS pseudo-class selector is a time-dimensional pseudo-class that will match for any element which appears entirely before an element that matches :current. For example in a video with captions which are being displayed by WebVTT.

## [:future](https://docs.w3cub.com/css/:future)
The :future CSS pseudo-class selector is a time-dimensional pseudo-class that will match for any element which appears entirely after an element that matches :current. For example in a video with captions which are being displayed by WebVTT.

## [:playin](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing)

## [:paused](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused)


