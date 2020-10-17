# 10 React

## 第一个React应用

```html
<html>
<head>
    <script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>
<script type="text/babel">

ReactDOM.render(
    <h1>Hello, world!</h1>,
    document.getElementById('root')
);

</script>
</body>
</html>
```

## 元素渲染

```html
<html>
<head>
    <script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>
<script type="text/babel">

const clock = (
    // 一个React DOM元素只能有一个根元素，因此
    // <h1>和<p>必须用一个根元素包起来：
    <div>
        <h1>Clock</h1>
        <p>It is { new Date().toLocaleString() }</p>
    </div>
);

ReactDOM.render(
    clock,
    document.getElementById('root')
);

</script>
</body>
</html>
```



##　组件

```html
<html>
<head>
    <script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>
<script type="text/babel">

function Welcome(props) {
    return <h1>Hello, {props.name}</h1>
}

function App() {
    return (
        <div>
            <Welcome name="Bob"/>
            <Welcome name="Alice"/>
            <Welcome name="Tom"/>
        </div>
    )
}

ReactDOM.render(
    <App/>,
    document.getElementById('root')
);

</script>
</body>
</html>
```

## 组件和状态

```html
<html>
<head>
    <script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>
<script type="text/babel">

class Welcome extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            date: new Date()
        }
    }

    render() {
        const
            hour = this.state.date.getHours(),
            hello = hour < 12 ? "Good morning" : (hour > 18 ? "Good afternoon" : "Good evening"),
            time = this.state.date.toLocaleTimeString();
        return (
            <div>
                <h1>{hello}, {this.props.name}</h1>
                <h2>It is {time}</h2>
            </div>
        );
    }
}

ReactDOM.render(
    <Welcome name="Bob"/>,
    document.getElementById('root')
);

</script>
</body>
</html>
```

