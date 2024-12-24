# Vue MFE Test App

A test application demonstrating the integration of multiple Vue.js micro-frontends using the `@mknz/vue-mfe-wrapper` framework.

## Features

This app integrates two micro-frontend features:
- 🔢 [@mknz/vue-mfe-feature-a](https://www.npmjs.com/package/@mknz/vue-mfe-feature-a) - A customizable Counter component
- 📝 [@mknz/vue-mfe-feature-b](https://www.npmjs.com/package/@mknz/vue-mfe-feature-b) - A TodoList component with localStorage support

## Quick Start

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

## Usage Example

The app demonstrates how to:
1. Import multiple MFE features
2. Configure the wrapper framework
3. Use components with different themes

```vue
<template>
  <FrameworkWrapper :config="config">
    <TodoList theme="dark" />
    <Counter :initial-count="0" theme="light" />
  </FrameworkWrapper>
</template>

<script setup lang="ts">
import { FrameworkWrapper } from '@mknz/vue-mfe-wrapper'
import type { FrameworkConfig } from '@mknz/vue-mfe-wrapper'
import { TodoList, VueMfeFeatureB } from './features'
import { VueMfeFeatureA, Counter } from '@mknz/vue-mfe-feature-a'
import '@mknz/vue-mfe-feature-b/style.css'
import '@mknz/vue-mfe-feature-a/style.css'

const config: FrameworkConfig = {
  features: [VueMfeFeatureB, VueMfeFeatureA]
}
</script>
```

## Project Structure

```
mfe-test-app/
├── src/
│   ├── App.vue          # Main application component
│   ├── features/        # Feature imports and configuration
│   └── main.ts         # Application entry point
├── package.json
└── vite.config.ts      # Vite configuration
```

## Dependencies

- Vue 3
- TypeScript
- Vite
- [@mknz/vue-mfe-wrapper](https://www.npmjs.com/package/@mknz/vue-mfe-wrapper)
- [@mknz/vue-mfe-feature-a](https://www.npmjs.com/package/@mknz/vue-mfe-feature-a)
- [@mknz/vue-mfe-feature-b](https://www.npmjs.com/package/@mknz/vue-mfe-feature-b)

## License

MIT
