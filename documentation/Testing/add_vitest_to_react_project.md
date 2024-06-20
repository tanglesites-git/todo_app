# Add Vitest to a React project

- [Home](../../README.md)

### Create React Project

```bash
npm vite@latest create [project-name]
```

> From the menu choose react and then the Typescript + SWC variant. 

```bash
npm install
```

Next add these packages to your project:

```bash
npm install vitest jsdom vitest-ui @testing-library/react @testing-library/jest-dom @testing-library/user-event @vitest/coverage-v8 --save-dev
```

> If you are getting errors from typescript, you may need to also install `@types/jest`:

> Added packages:
>- vitest 
>- jsdom 
>- vitest-ui 
>- @testing-library/react 
>- @testing-library/jest-dom 
>- @testing-library/user-event 
>- @vitest/coverage-v8
>- @types/jest

> Of all these packages, `vitest-ui` is optional, but it does offer a nice UI for running tests. Next, add the following scripts to your `package.json`:

```json
{
    ...
    "scripts": {
        ...
        "coverage": "vitest run --coverage",
        "test": "vitest",
        "test:ui": "vitest --ui"
    }
}
```

> Now you can run `npm test` to run your tests, `npm run test:ui` to run your tests with the UI, and `npm run test:coverage` to run your tests with coverage. However, you cannot run tests for any file with a `.jsx` extension. To fix this, create a `vite.config.ts` file and add the following to your `vitest.config.ts`:

```typescript
/// <reference types="vitest" />

...

export default defineConfig({
    ...
    test: {
        environment: 'jsdom',
        globals: true,
        setupFiles: ["./tests/vitest.setup.ts"]
    },
});
```

> Next add the following to your `tsconfig.json`:

```json
{
    ...
    "compilerOptions": {
        ...
        "types": ["vitest/globals", "@testing-library/jest-dom"],
    }
}
```

> If after adding this to your `tsconfig.json` you are still getting errors, you may need to add the package `@types/jest` to your project as mentioned above. Finally, create a `tests` folder in your project and add a `vitest.setup.ts` file with the following:

```typescript
import '@testing-library/jest-dom/vitest'
import { cleanup } from '@testing-library/react'
import { afterEach } from 'vitest'

afterEach(() => {
  cleanup()
})
```

> Now create a test `demo.test.tsx` file in your `tests` folder:

```typescript
describe('Demo test', () => {
    it('should pass', () => {
        expect(1 + 1).toBe(2);
    });
});
```

> You should get a similar result to the following:

```bash
 DEV  v1.6.0 /home/tanglesites/Projects/todo_app/src/react_client

 ✓ tests/demo.test.ts (1)
   ✓ Demo test (1)
     ✓ should pass

 Test Files  1 passed (1)
      Tests  1 passed (1)
   Start at  18:41:33
   Duration  526ms (transform 25ms, setup 103ms, collect 3ms, tests 1ms, environment 231ms, prepare 57ms)


 PASS  Waiting for file changes...
       press h to show help, press q to quit
```
