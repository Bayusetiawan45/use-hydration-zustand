# @codebayu/use-hydration-zustand

A React Custom Hook for Zustand state management library to simplify hydration handling.

## Installation

```bash
# npm
npm install @codebayu/use-hydration-zustand

# yarn
yarn add @codebayu/use-hydration-zustand
```

## Usage

```tsx
import { useHydrationZustand } from '@codebayu/use-hydration-zustand';
import create from 'zustand';

// Your Zustand store
const useStore = create((set) => ({
  // Your store definition here
}));

function MyComponent() {
  // Use the useHydrationZustand hook
  const isHydrated = useHydrationZustand(useStore);

  return (
    <div>
      {isHydrated ? (
        items.map((item) => <Card {...item} key={item.id} />)
      ) : (
        <Loading />
      )}
    </div>
  );
}

export default MyComponent;
```

## API

`useHydrationZustand(store)`
A hook for Zustand that simplifies hydration handling.

Parameters

- `store (UseBoundStore<any>)`: The Zustand store.

Returns

- `boolean`: true if the store has finished hydration, false otherwise.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the [LICENSE](LICENSE) file for details.
