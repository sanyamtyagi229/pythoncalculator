// package.json
{
  "name": "calculator-app",
  "version": "1.0.0",
  "private": true,
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-scripts": "5.0.1"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  }
}
// src/index.js
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
// src/App.js
import React from "react";
import Calculator from "./Calculator";

function App() {
  return (
    <div>
      <h1 style={{ textAlign: "center", color: "#333" }}>React Calculator</h1>
      <Calculator />
    </div>
  );
}
// src/Calculator.js
import React, { useState } from "react";
import "./Calculator.css";

function Calculator() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const clearInput = () => {
    setInput("");
  };

  const calculate = () => {
    try {
      setInput(eval(input).toString()); // ⚠️ eval is fine for demo
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator">
      <div className="display">{input || "0"}</div>
      <div className="buttons">
        <button onClick={clearInput} className="clear">C</button>
        <button onClick={() => handleClick("/")}>÷</button>
        <button onClick={() => handleClick("*")}>×</button>
        <button onClick={() => handleClick("-")}>−</button>

        <button onClick={() => handleClick("7")}>7</button>
        <button onClick={() => handleClick("8")}>8</button>
        <button onClick={() => handleClick("9")}>9</button>
        <button onClick={() => handleClick("+")}>+</button>

        <button onClick={() => handleClick("4")}>4</button>
        <button onClick={() => handleClick("5")}>5</button>
        <button onClick={() => handleClick("6")}>6</button>
        <button onClick={calculate} className="equals">=</button>

        <button onClick={() => handleClick("1")}>1</button>
        <button onClick={() => handleClick("2")}>2</button>
        <button onClick={() => handleClick("3")}>3</button>
        <button onClick={() => handleClick("0")} className="zero">0</button>
        <button onClick={() => handleClick(".")}>.</button>
      </div>
    </div>
  );
}

export default Calculator;
// src/Calculator.js
import React, { useState } from "react";
import "./Calculator.css";

function Calculator() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const clearInput = () => {
    setInput("");
  };

  const calculate = () => {
    try {
      setInput(eval(input).toString()); // ⚠️ eval is fine for demo
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator">
      <div className="display">{input || "0"}</div>
      <div className="buttons">
        <button onClick={clearInput} className="clear">C</button>
        <button onClick={() => handleClick("/")}>÷</button>
        <button onClick={() => handleClick("*")}>×</button>
        <button onClick={() => handleClick("-")}>−</button>

        <button onClick={() => handleClick("7")}>7</button>
        <button onClick={() => handleClick("8")}>8</button>
        <button onClick={() => handleClick("9")}>9</button>
        <button onClick={() => handleClick("+")}>+</button>

        <button onClick={() => handleClick("4")}>4</button>
        <button onClick={() => handleClick("5")}>5</button>
        <button onClick={() => handleClick("6")}>6</button>
        <button onClick={calculate} className="equals">=</button>

        <button onClick={() => handleClick("1")}>1</button>
        <button onClick={() => handleClick("2")}>2</button>
        <button onClick={() => handleClick("3")}>3</button>
        <button onClick={() => handleClick("0")} className="zero">0</button>
        <button onClick={() => handleClick(".")}>.</button>
      </div>
    </div>
  );
}

export default Calculator;
/* src/Calculator.css */
.calculator {
  width: 260px;
  margin: 50px auto;
  padding: 20px;
  background: #222;
  border-radius: 12px;
  box-shadow: 0 0 20px rgba(0,0,0,0.5);
}

.display {
  background: #000;
  color: #0f0;
  font-size: 2em;
  padding: 10px;
  margin-bottom: 15px;
  text-align: right;
  border-radius: 6px;
  min-height: 40px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 8px;
}

button {
  height: 50px;
  font-size: 1.2em;
  border: none;
  border-radius: 8px;
  background: #444;
  color: #fff;
  cursor: pointer;
  transition: background 0.2s;
}

button:hover {
  background: #666;
}

.clear {
  background: #d9534f;
}

.equals {
  background: #5cb85c;
}

.zero {
  grid-column: span 2;
}


export default App;
