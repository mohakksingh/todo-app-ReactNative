# Todo App (React Native + Expo)

A simple, example Todo application built with Expo and TypeScript. It demonstrates a modern React Native app structure using the Expo Router, a shared theme system, and a Convex backend for realtime data and server functions.

## Features

- Add, persist, and list todos (Convex-backed).
- Themed UI with an easy-to-use `useTheme` hook.
- File-based routing with the `app/` directory (Expo Router).
- TypeScript throughout, with generated Convex client code in `convex/_generated`.

## Tech stack

- React Native (Expo)
- Expo Router
- TypeScript
- Convex (serverless backend)
- `expo-linear-gradient`, `@expo/vector-icons` for UI polish

## Quick Start

Prerequisites

- Node.js (16+ recommended)
- Yarn or npm
- Expo CLI (optional): `npm install -g expo-cli`

Clone and install

```bash
git clone <your-repo-url>
cd todo-app
# Using npm
npm install
# or using yarn
yarn
```

Start the dev server

```bash
# Start Expo dev tools
npx expo start
# or
yarn start
```

Open the app

- Press `i` to open in iOS Simulator (macOS + Xcode)
- Press `a` to open in Android emulator
- Scan the QR code with Expo Go on a real device

If you prefer explicit scripts (add these to `package.json` if not present):

```json
{
  "scripts": {
    "start": "expo start",
    "android": "expo start --android",
    "ios": "expo start --ios",
    "web": "expo start --web"
  }
}
```

## Convex backend

This project uses Convex for realtime persistence and server functions. Look in the `convex/` folder for the schema (`schema.ts`) and server-side function definitions (for example, `todos.ts`). The client-side generated bindings are in `convex/_generated` and are imported via `convex/_generated/api`.

To run and use Convex with this project:

1. Create a Convex project at <https://www.convex.dev> and follow their setup guide.
2. Deploy or start a local Convex dev server according to Convex docs.
3. Ensure the app has access to the Convex project URL / keys — follow Convex docs to wire environment variables (or the method you prefer).

Note: exact Convex setup can change; refer to Convex documentation for the latest instructions.

## Project structure

Main folders and files (high level):

- `app/` — Expo Router pages and layouts (`_layout.tsx`, `index.tsx`, etc.)
- `assets/` — images and style helpers (`assets/styles/*.ts`)
- `components/` — shared UI components like `TodoInput.tsx`, `Header.tsx` and `ProgressStats.tsx`
- `convex/` — Convex functions, schema, and generated client
- `hooks/` — custom hooks such as `useTheme.tsx`
- `tsconfig.json`, `package.json` — TypeScript and dependency configs

Open `components/TodoInput.tsx` to see how a new todo is added; it calls the generated Convex mutation at `api.todos.addTodo`.

## Theming and styles

The app uses a `useTheme` hook (in `hooks/useTheme.tsx`) which provides a `colors` object consumed by style creators in `assets/styles/` (for example, `home.styles.ts`). This makes it easy to maintain a consistent look and switch themes if needed.

## Development notes

- The project is written in TypeScript — keep types consistent and run the TypeScript compiler when making structural changes.
- Generated Convex client files live in `convex/_generated`. Do not edit generated files directly; update your Convex schema or server functions and regenerate if needed.

## Contributing

Contributions are welcome. Suggested workflow:

1. Fork the repository and create a feature branch.
2. Implement your change and include tests if appropriate.
3. Ensure the app still builds: `npm run build` / `yarn build` or run the TypeScript checker.
4. Open a pull request with a clear description of the change.

## License

No license file is included by default. Add a `LICENSE` file (for example, MIT) if you intend to publish or share this project publicly.

## Contact

If you have questions or need help, open an issue in the repository or reach out to the maintainer.

---

Happy hacking! 🚀

# Welcome to your Expo app 👋

This is an [Expo](https://expo.dev) project created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## Get started

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
   npx expo start
   ```

In the output, you'll find options to open the app in a

- [development build](https://docs.expo.dev/develop/development-builds/introduction/)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Expo Go](https://expo.dev/go), a limited sandbox for trying out app development with Expo

You can start developing by editing the files inside the **app** directory. This project uses [file-based routing](https://docs.expo.dev/router/introduction).

## Get a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the **app-example** directory and create a blank **app** directory where you can start developing.

## Learn more

To learn more about developing your project with Expo, look at the following resources:

- [Expo documentation](https://docs.expo.dev/): Learn fundamentals, or go into advanced topics with our [guides](https://docs.expo.dev/guides).
- [Learn Expo tutorial](https://docs.expo.dev/tutorial/introduction/): Follow a step-by-step tutorial where you'll create a project that runs on Android, iOS, and the web.

## Join the community

Join our community of developers creating universal apps.

- [Expo on GitHub](https://github.com/expo/expo): View our open source platform and contribute.
- [Discord community](https://chat.expo.dev): Chat with Expo users and ask questions.
