- [Phase 1: App component](#phase-1-app-component)
  - [instruction](#instruction)
- [Phase 2: TodoItem component](#phase-2-todoitem-component)
  - [instruction](#instruction-1)
- [Phase 3: Props](#phase-3-props)
  - [instruction](#instruction-2)
  - [2W1H](#2w1h)
    - [Q1. prop은 상위 컴포넌트에서 하위 컴포넌트로, 하위 컴포넌트에서 더 아래의 하위 컴포넌트로 계속 전달된다. 이렇게 데이터가 전달되는 파이프라인을 고려하면, prop은 어떤 장점이 있는가?](#q1-prop은-상위-컴포넌트에서-하위-컴포넌트로-하위-컴포넌트에서-더-아래의-하위-컴포넌트로-계속-전달된다-이렇게-데이터가-전달되는-파이프라인을-고려하면-prop은-어떤-장점이-있는가)
- [Phase 4: State](#phase-4-state)
  - [instruction](#instruction-3)
- [Phase 5: eventHandler](#phase-5-eventhandler)
  - [instruction](#instruction-4)
  - [2W1H](#2w1h-1)
    - [Q1. `onChange={() => console.log("Changed!")}`에서 onChange property의 value로 함수를 호출했는가 아니면 함수 자체를 전달했는가?](#q1-onchange--consolelogchanged에서-onchange-property의-value로-함수를-호출했는가-아니면-함수-자체를-전달했는가)
    - [Q2. `onChange`의 이벤트 핸들러로 인자(id)를 받아서 처리하는 함수를 전달해야 하면 다음 둘 중 무엇이 맞는가?](#q2-onchange의-이벤트-핸들러로-인자id를-받아서-처리하는-함수를-전달해야-하면-다음-둘-중-무엇이-맞는가)
- [Phase 6: eventHandler props](#phase-6-eventhandler-props)
  - [instruction](#instruction-5)
  - [2W1H](#2w1h-2)
    - [Q1. `<TodoItem handleChange={this.handleChange}>`에서 TodoItem에 정의한 `handleChange` property는 TodoItem 컴포넌트 내에서 무엇으로 사용되는가?](#q1-todoitem-handlechangethishandlechange에서-todoitem에-정의한-handlechange-property는-todoitem-컴포넌트-내에서-무엇으로-사용되는가)

# Phase 1: App component

> Learn how to redner HTML code using React.

## instruction

1. From scratch, initialize the React app
2. Render an `<App />` component
3. Create the `<App />` component from scratch
4. Have the `<App />` component render 3 or 4 checkboxes with paragraphs or spans next to it like below:

```js
<div>
    <input type="checkbox" />
    <p>Placeholder text here</p>
    <hr />
    
    <input type="checkbox" />
    <p>Placeholder text here</p>
    <hr />
    
    <input type="checkbox" />
    <p>Placeholder text here</p>
    <hr />
    
    <input type="checkbox" />
    <p>Placeholder text here</p>
    <hr />
</div>
```

# Phase 2: TodoItem component

> Don't repeat the same code and make it a independent component.

## instruction

1. Change the input/p combo below to be a new component called `<TodoItem />`. `<TodoItem />` (for now) will just have the same displayed data below (every todo item is the same) hardcoded inside of it. (We'll learn soon how to make the TodoItem more flexible)
2. Style up the page however you want! You're welcome to use regular CSS (in the CSS file) or inline styles, or both!

CSS files:

```css
body {
    background-color: whitesmoke;
}

.todo-list {
    background-color: white;
    margin: auto;
    width: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    border: 1px solid #efefef;
    box-shadow:
    /* The top layer shadow */
        0 1px 1px rgba(0,0,0,0.15),
            /* The second layer */
        0 10px 0 -5px #eee,
            /* The second layer shadow */
        0 10px 1px -4px rgba(0,0,0,0.15),
            /* The third layer */
        0 20px 0 -10px #eee,
            /* The third layer shadow */
        0 20px 1px -9px rgba(0,0,0,0.15);
    padding: 30px;
}

.todo-item {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 30px 20px 0;
    width: 70%;
    border-bottom: 1px solid #cecece;
    font-family: Roboto, sans-serif;
    font-weight: 100;
    font-size: 15px;
    color: #333333;
}

input[type=checkbox] {
    margin-right: 10px;
    font-size: 30px;
}

input[type=checkbox]:focus {
    outline: 0;
}
```

# Phase 3: Props 

> Imagine you received data from API response. Learn how you can deliver the data to specific react component using props.

## instruction

Let's practice props and mapping components on our todo list app!

I've created a js file with some todos data in it, which I'm imported into this file. (Normally this data would come from an API call, not a local file). 

1. Using the array map method, render a child component for each todo item in the todosData array and pass the relevant data to it.

## 2W1H

### Q1. prop은 상위 컴포넌트에서 하위 컴포넌트로, 하위 컴포넌트에서 더 아래의 하위 컴포넌트로 계속 전달된다. 이렇게 데이터가 전달되는 파이프라인을 고려하면, prop은 어떤 장점이 있는가?

prop이 변하면 prop이 흐르는 모든 컴포넌트가 알아서 자동적으로 반응하여 바뀐 데이터를 반영한다. 그래서 react는 reactive하다.

# Phase 4: State

> Imagine you received data from API response. But the data can be modified by user interaction or some other reasons. In this case, you should consider using state. Learn how to use state.

## instruction

In the previous iteration of this todo list app, we pulled in todos data from a JSON file and mapped over it to display the todo items.

Eventually we'll want to be able to modify the data, which will only happen if we've "loaded" the data in to the component's state

1. Change the `<App />` component into a stateful class component and load the imported `todosData` into state.

# Phase 5: eventHandler

> Learn how to write eventHandler as a value of property.

## instruction

1. Get rid of our warning about not having an onChange on our input. For now, the function that runs onChange can simply console.log something.

## 2W1H

### Q1. `onChange={() => console.log("Changed!")}`에서 onChange property의 value로 함수를 호출했는가 아니면 함수 자체를 전달했는가?

함수 자체를 전달했다.

### Q2. `onChange`의 이벤트 핸들러로 인자(id)를 받아서 처리하는 함수를 전달해야 하면 다음 둘 중 무엇이 맞는가?

1번: 

```js
onChange={handleChange(id)}
```

2번:

```js
onChange={() => handleChange(id)}
```

2번이 맞다. 왜냐하면 1번은 함수를 호출한 것이지 함수 자체를 전달한 게 아니기 때문이다. 따라서 인자를 받아서 처리해야 하는 함수를 전달해야 하는 경우에는 함수 호출문을 arrow function으로 감싸주면 함수 자체를 전달할 수 있다.

# Phase 6: eventHandler props

> Learn how to deliver eventhandler as props.

## instruction

1. Update state so that the item with the given id flips `completed` from false to true (or vise versa)
2. Remember not to modify prevState directly, but instead to return a new version of state with the change you want included in that update. (Think how you might use the `.map` method to do this)

hint:

```js
class App extends React.Component {
    constructor() {
        super()
        this.state = {
            todos: todosData
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    handleChange(id) {
        // Update state so that the item with the given id flips `completed` from false to true (or vise versa)
        // Remember not to modify prevState directly, but instead to return a new version of state with the change you want included in that update. (Think how you might use the `.map` method to do this)
    }
```

## 2W1H

### Q1. `<TodoItem handleChange={this.handleChange}>`에서 TodoItem에 정의한 `handleChange` property는 TodoItem 컴포넌트 내에서 무엇으로 사용되는가?

TodoItem의 regular html 속성의 value로 사용된다. 리액트 컴포넌트에 정의한 property는 리액트 컴포넌트가 렌더링하는 regular html 속성의 value로 사용된다.

예시:

```js
// App.js

<TodoItem key={item.id} handleChange={this.handleChange} item={item}/> // handleChange "property" 주목
```

```js
// TodoItem.js

function TodoItem(props) {
    return (
        <div className="todo-item">
            <input 
                type="checkbox" 
                checked={props.item.completed} 
                onChange={() => props.handleChange(props.item.id)} // props에 담긴 handlechange가 onChange의 "value"로 쓰인다.
            />
            <p>{props.item.text}</p>
        </div>
    )
}
```

