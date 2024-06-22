# REACT BETTER STATE DEMO

- Open [Live Demo](https://batazo.github.io/react-betterstate-demo-builded/)


```
import { useBetterState } from "react";
import './App.css';

function App() {

  const defaults = {
    counter: { 
      decrease: 1,
      base: 0,
      increase: 1
    }
  }

  const states = { 
    counter: useBetterState(defaults.counter.base) 
  };

  const actions = {
    click: {
      counter: {
        decrease: ()=>states.counter.set(prev=>prev-defaults.counter.decrease),
        reset: ()=>states.counter.set(defaults.counter.base),
        increase: ()=>states.counter.set(prev=>prev+defaults.counter.increase),
      }
    }
  }

  return (
    <div className="App">
       <div>STATE: {states.counter.get}</div>
       <div>
          <button onClick={actions.click.counter.decrease}>DECREASE</button>
          <button onClick={actions.click.counter.reset}>RESET</button>
          <button onClick={actions.click.counter.increase}>INCREASE</button>
        </div>
    </div>
  );
}

export default App;
```
