There are 2 types of Components

- Functional Component
- Class Component

### Creating a functional component

```jsx
const HeadingComponent = () => {
	return <h1>This is heading</h1>
}

// Can also be written as
const HeadingComponent = () => (
	<h1>This is heading</h1>
)

// Can also be written as
const HeadingComponent = () =>  <h1>This is heading</h1>

// NOTE - It should return a single element/parent

// This wont work
const HeadingComponent = () => (
	<h1>This is heading</h1>
  <h1>Heading 2</h1>
)

// This willwork
const HeadingComponent = () => (
			<div>
				<h1>This is heading</h1>
			  <h1>Heading 2</h1>
			</div>
)
```

### Rendering component

```jsx
const root = ReactDOM.createRoot(document.getElementById('root))

const HeadingComponent = () => (
	<h1>This is heading</h1>
)

root.render(<HeadingComponent/>) // NOTE the syntax
```

### Using a component inside another component

```jsx
const TitleComponent = () => (
	<h1>This is heading</h1>
)
const HeadingComponent = () => (
			<div>
				<TitleComponent/> 
				<TitleComponent></TitleComponent> 
				{ TitleComponent() } 
			  <h1>Heading 2</h1>
			</div>
)
```