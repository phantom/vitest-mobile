---
'vitest-mobile': patch
---

Publish type declarations for the root entry point. `exports["."].types` pointed at `./dist/node/index.d.ts`, which `npm run build` never emitted, so importing `vitest-mobile` in `vitest.config.ts` failed type-checking with `TS7016`. The build now emits declarations for the root entry, so `nativePlugin` and the exported types (`NativePluginOptions`, `Platform`, `MetroConfigContext`, `MetroConfigCustomizer`) resolve from `vitest-mobile`.
