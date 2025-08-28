![Codefomonyaya](./codefomonyaya.png)

# 🚀 React + TypeScript + Vite Boilerplate Gaul

Yo! Ini template kece buat mulai ngoding React pake TypeScript dan Vite. Udah siap tempur dengan HMR (Hot Module Replacement) dan beberapa aturan ESLint biar ngoding lo makin rapi.

## 🔌 Plugin Resmi yang Bisa Dipakai

Ada dua plugin resmi yang bisa lo pilih, tergantung kebutuhan:

- [`@vitejs/plugin-react`](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) → Pake [Babel](https://babeljs.io/) buat Fast Refresh.
- [`@vitejs/plugin-react-swc`](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) → Pake [SWC](https://swc.rs/) biar makin ngebut.

## 🔧 Upgrade ESLint Biar Lebih Sakti

Kalo lo lagi ngebangun project buat production, disaranin buat upgrade aturan ESLint-nya biar lebih aware sama TypeScript:

```js
export default tseslint.config({
  extends: [
    // Ganti default config sama yang ini
    ...tseslint.configs.recommendedTypeChecked,
    // Atau pake ini kalo mau yang super ketat
    ...tseslint.configs.strictTypeChecked,
    // Tambahan buat gaya penulisan
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
