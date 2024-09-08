# React native workshop

## Workshop plan

1. Intro to JS/TS
2. Intro to HTML
3. Intro to React
4. Intro to React Native
5. Develop and ship our app

## Intro to JS/TS

```ts
let a = 1;
a = 2;

const b = 3;

const fac = (x) => {
  if (x <= 1) {
    return 1;
  }
  return x * f(x - 1);
};

const object = {
  a: 1,
  b: 2,
  c: 3,
};

console.log(object.a); // 1
console.log(object["a"]); // 1
```

## Intro to HTML

- I'll explain this by drawing a few boxes
- Layout and spacing is handled by CSS (and dark magic)

## Intro to React

- You describe the HTML you want with some JS and React does some magic to make it work

```tsx
const Component = () => {
  const value = computation(1, 2, 3);
  return <span>The value is {value}</span>;
};
```

- React allows your components to have state

```tsx
const Component = () => {
  const [count, setCount] = useState(1);

  return (
    <button onClick={() => setCount(count + 1)}>
      I was clicked {count} times
    </button>
  );
};
```

- When component functions is executed, it needs to be pure (no side-effects). If you need to trigger some side-effect you need to use `useEffect` binding.

```tsx
const Component = () => {
  const [count, setCount] = useState(1);

  useEffect(() => {
    console.log("count is", count);
  }, [count]);

  return (
    <button onClick={() => setCount(count + 1)}>
      I was clicked {count} times
    </button>
  );
};
```

## Into to React Native

- Tries to look and feel like React on web, but it targets native Android and iOS so it's primitives are more generic.

```tsx
const Component = () => {
  const [count, setCount] = useState(1);

  useEffect(() => {
    console.log("count is", count);
  }, [count]);

  return (
    <Button
      onPress={() => setCount(count + 1)}
      title={`I was clicked ${count} times`}
    />
  );
};
```

## Steps

1. Go to [react native documentation](https://reactnative.dev/docs/environment-setup) and follow installation instructions with expo
   - Run `npx create-expo-app@latest`
2. Install dependencies for our new `npm` project
   - `npm install`
3. Start our freshly bootstrapped app
   - `npm run start`
4. Play around with the app on phone and on web
5. Delete contents of `index.tsx` and replace it with simple counter
6. Look into [Expo docs](https://docs.expo.dev/versions/latest/) and figure out how to add haptics
7. Look into [Expo docs](https://docs.expo.dev/versions/latest/) and figure out how to add simple camera integration
8. Go to [Expo web](https://expo.dev/) and create project for our app
