---
order: 0
version: 4.20.0
title:
  zh-CN: 动态数据
  en-US: Dynamic
---

## zh-CN

动态加载数据。

## en-US

Load `options` dynamically.

```tsx
import React, { useState } from 'react';
import { Segmented, Button } from 'antd';

const defaultOptions = ['Daily', 'Weekly', 'Monthly'];

const Demo: React.FC = () => {
  const [options, setOptions] = useState(defaultOptions);
  const [moreLoaded, setMoreLoaded] = useState(false);

  const handleLoadOptions = () => {
    setOptions([...defaultOptions, 'Quarterly', 'Yearly']);
    setMoreLoaded(true);
  };

  return (
    <>
      <Segmented options={options} />
      <br />
      <Button type="primary" disabled={moreLoaded} onClick={handleLoadOptions}>
        Load more options
      </Button>
    </>
  );
};

ReactDOM.render(<Demo />, mountNode);
```

```css
.code-box-demo {
  overflow-x: auto;
}

.code-box-demo .ant-segmented {
  margin-bottom: 10px;
}
```