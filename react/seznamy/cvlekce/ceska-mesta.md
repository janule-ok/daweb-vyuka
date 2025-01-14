---
title: Česká města
demand: 2
---

1. Založte si React projekt podle již známého postupu.
1. Do souboru `index.jsx` vložte mimo komponentu `App` pole s názvy deseti největších českých měst.
   ```js
   const cities = [
     'Praha',
     'Brno',
     'Ostrava',
     'Plzeň',
     'Liberec',
     'Olomouc',
     'České Budějovice',
     'Hradec Králové',
     'Ústí nad Labem',
     'Pardubice',
   ];
   ```
1. Stále mimo hlavní komponentu vezměte pole `cities` a pomocí funkce `map` z něj vyrobte pole JSX elementů. Každý JSX element nechť má následující strukturu.
   ```js
   <div className="city">Název města</div>
   ```
   Výsledné pole uložte do proměnné `cityElements`.
1. Použijte pole `cityElements` uvnitř komponenty `App` a zobrazte jej tak na vaší stránce.
1. Zbavte se proměnné `cityElements` a funkci `map` použijte přímo uvnitř komponenty `App`.
1. V konzoli si React bude stěžovat, že mu chybí `key` prop. Máme však štěstí, jména měst jsou unikátní. Můžeme tak na náš `div` přídat prop `key` a do něj poslat přímo název města.

---solution

```jsx
import React from 'react';
import { createRoot } from 'react-dom/client';
import './style.css';

const cities = [
  'Praha',
  'Brno',
  'Ostrava',
  'Plzeň',
  'Liberec',
  'Olomouc',
  'České Budějovice',
  'Hradec Králové',
  'Ústí nad Labem',
  'Pardubice',
];

const App = () => (
  <div className="container">
    <div className="cities">
      {cities.map((city) => (
        <div key={city} className="city">
          {city}
        </div>
      ))}
    </div>
  </div>
);

createRoot(document.querySelector('#app')).render(<App />);
```
