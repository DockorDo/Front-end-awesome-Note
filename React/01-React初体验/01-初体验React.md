# React

## 构建小型React应用程序

可以输入**React.new**进入一个React项目的在线的codesandbox。

进入后，可以看到一个完成的初始化react项目；

课程代码：

``` js

import { useEffect, useState } from "react";

export default function App() {
  const [advice, setAdvice] = useState("");
  const [count, setCount] = useState(0);

  async function getAdvice() {
    const res = await fetch("https://api.adviceslip.com/advice");
    const data = await res.json();
    setAdvice(data.slip.advice);
    setCount((c) => c + 1);
  }

  useEffect(function () {
    getAdvice();
  }, []);

  return (
    <div>
      <h1>{advice}</h1>
      <button onClick={getAdvice}>GEt advice</button>
      <Message count={count} />
    </div>
  );
}

function Message({ count }) {
  return <p>你已经阅读了{count}条建议</p>;
}
```
课外学习连接：
- https://codingheroes.io/resources/
- https://github.com/jonasschmedtmann/ultimate-react-course
