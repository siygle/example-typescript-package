# Example TypeScript Package ready to be published on npm for 2021

[![npm package](https://img.shields.io/badge/npm%20i-example--typescript--package-brightgreen)](https://www.npmjs.com/package/example-typescript-package) [![version number](<![npm](https://img.shields.io/npm/v/example-typescript-package?color=green&label=version)>)](https://github.com/tomchen/example-typescript-package/releases) [![Actions Status](https://github.com/tomchen/example-typescript-package/workflows/Test/badge.svg)](https://github.com/tomchen/example-typescript-package/actions) [![License](https://img.shields.io/github/license/tomchen/example-typescript-package)](https://github.com/tomchen/example-typescript-package/blob/master/LICENSE)

This is an example TypeScript Package ready to be published on npm. It has been set up with automated tests and package publishing workflow using GitHub Actions CI/CD. It is made primarily for GitHub<a href="https://github.com/" title="Github"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/github-icon.svg" alt="Github" width="21px" height="21px"></a> + VS Code<a href="https://code.visualstudio.com/" title="Visual Studio Code"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/visual-studio-code.svg" alt="Visual Studio Code" width="21px" height="21px"></a> (Windows<a href="https://www.microsoft.com/windows" title="Windows"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/microsoft-windows.svg" alt="Windows" width="21px" height="21px"></a> / Mac<a href="https://www.apple.com/macos/" title="Mac OS"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/macOS.svg" alt="Mac OS" width="21px" height="21px"></a> / Linux<a href="https://www.linuxfoundation.org/" title="Linux"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/linux-tux.svg" alt="Linux" width="21px" height="21px"></a>) users who are about to write and publish their first TypeScript npm package. This package could serve as a starter / boilerplate / demo for them.

It uses npm<a href="https://www.npmjs.com/" title="npm"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/npm.svg" alt="npm" width="21px" height="21px"></a>, TypeScript compiler<a href="https://www.typescriptlang.org/" title="Typescript"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/typescript-icon.svg" alt="Typescript" width="21px" height="21px"></a>, Jest<a href="https://jestjs.io/" title="Jest"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/jest.svg" alt="Jest" width="21px" height="21px"></a>, webpack<a href="https://webpack.js.org/" title="webpack"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/webpack.svg" alt="webpack" width="21px" height="21px"></a>, ESLint<a href="https://eslint.org/" title="ESLint"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/eslint.svg" alt="ESLint" width="21px" height="21px"></a>, Prettier<a href="https://prettier.io/" title="Prettier"><img src="https://github.com/tomchen/stack-icons/blob/master/logos/prettier.svg" alt="Prettier" width="21px" height="21px"></a>.

The production files include CommonJS, ES Modules, UMD version and TypeScript declaration files.

## Development

You need to have [Node.js](https://nodejs.org/en/download/) installed. Node includes npm as its default package manager.

Open the whole package folder with a good code editor, preferably [Visual Studio Code](https://code.visualstudio.com/download). Consider installing VS Code extensions [ES Lint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) and [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode).

In the VS Code top menu: **Terminal** -> **New Terminal**

### Install dependencies

Install dependencies with npm:

```bash
npm i
```

### Write your code

Make necessary changes in **package.json** (name, version, description, keywords, author, homepage and other URLs).

Write your code in **src** folder, and unit test in **test** folder, replacing the original files there.

The VS Code shortcuts for formatting of a code file are: <kbd>Shift</kbd> + <kbd>Alt</kbd> + <kbd>F</kbd> (Windows); <kbd>Shift</kbd> + <kbd>Option (Alt)</kbd> + <kbd>F</kbd> (MacOS); <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>I</kbd> (Linux).

Change code linting and formatting settings in **.prettierrc.js** if you want.

### Test

Test your code with Jest framework:

```bash
npm run test
```

### Build

Build production (distribution) files in your **dist** folder:

```bash
npm run build
```

It generates CommonJS (in **dist/cjs** folder), ES Modules (in **dist/esm** folder), bundled and minified UMD (in **dist/umd** folder), as well as TypeScript declaration files (in **dist/types** folder).

### Try it before publishing

Run:

```bash
npm link
```

[npm link](https://docs.npmjs.com/cli/v6/commands/npm-link) will create a symlink in the global folder, which may be **{prefix}/lib/node_modules/example-typescript-package** or **C:\Users\<username>\AppData\Roaming\npm\node_modules\example-typescript-package**.

Create an empty folder elsewhere, you don't even need to `npm init` (to generate **package.json**). Open the folder with VS Code, open a terminal and just run:

```bash
npm link example-typescript-package
```

This will create a symbolic link from globally-installed example-typescript-package to **node_modules/** of the current folder.

You can then create a, for example, **testnum.ts** file with the content:

```ts
import { Num } from 'example-typescript-package'
console.log(new Num(5).add(new Num(6)).val() === 11)
```

If you don't see any linting errors in VS Code, if you put your mouse cursor over `Num` and see its type, then it's all good.

Whenever you want to uninstall the globally-installed example-typescript-package and remove the symlink in the global folder, run:

```bash
npm uninstall example-typescript-package -g
```

### Publish

#### Manual Publishing

...

#### CI Publishing

...

## Notes

- It uses npm but you can easily switch to yarn, of course (remember to change all "npm" in `scripts` in the file **package.json**)
  - Whether you use npm as your package manager ≠ Whether you can publish to the npm registry
- Works fine in VS Code. In my configuration **.eslintrc** and **.prettierrc** cooperate perfectly
- See `scripts`.`build` in **package.json** for other predefined script commands

## References

- [Creating and publishing unscoped public packages - npm docs](https://docs.npmjs.com/creating-and-publishing-unscoped-public-packages)
- [npm-publish - npm docs](https://docs.npmjs.com/cli/v6/commands/npm-publish)
- [Publishing - TypeScript docs](https://www.typescriptlang.org/docs/handbook/declaration-files/publishing.html)
- [Publishing Node.js packages - GitHub Docs](https://docs.github.com/en/free-pro-team@latest/actions/guides/publishing-nodejs-packages)

Btw, if you want to publish Python package, go to [Example PyPI (Python Package Index) Package & Tutorial / Instruction / Workflow for 2021](https://github.com/tomchen/example_pypi_package).