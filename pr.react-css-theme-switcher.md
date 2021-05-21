---
id: e15dec78-fdbb-4563-b589-dc6acbb3cfad
title: React CSS Theme Switcher
desc: ''
updated: 1621296925327
created: 1621296807875
---

## Summary
- source: [^1]
<!-- -->

[^1]: https://www.npmjs.com/package/react-css-theme-switcher


```sh
yarn add react-css-theme-switcher
lerna add react-css-theme-switcher  --scope @dendronhq/webapp
```

```ts
import React from "react";

import ReactDOM from "react-dom";

import "./index.css";
import App from "./App";
import { ThemeSwitcherProvider } from "react-css-theme-switcher";

const themes = {
  dark: `${process.env.PUBLIC_URL}/dark-theme.css`,
  light: `${process.env.PUBLIC_URL}/light-theme.css`,
};

ReactDOM.render(
  <React.StrictMode>
    <ThemeSwitcherProvider themeMap={themes} defaultTheme="light">
      <App />
    </ThemeSwitcherProvider>
  </React.StrictMode>,
  document.getElementById("root")
);
```

- toggle
```ts
import { useThemeSwitcher } from 'react-css-theme-switcher';

const Component = () => {
  const { switcher, themes, currentTheme, status } = useThemeSwitcher();
  const [isDarkMode, setIsDarkMode] = React.useState(false);

  if (status === 'loading') {
    return <div>Loading styles...</div>;
  }

  const toggleDarkMode = () => {
    setIsDarkMode(previous => {
      switcher({ theme: previous ? themes.light : themes.dark });
      return !previous;
    });
  };

  return (
    <div>
      <h2>Current theme: {currentTheme}</h2>
      <button onClick={toggleDarkMode} />
    </div>
  );
};

```