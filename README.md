# @njmaeff/typescript

This repository is a fork of [typescript](https://github.com/microsoft/TypeScript) with special features added which may not belong in the upstream repository. 

## Usage

The published npm package rebrands the command line scripts from `tsc` to `tsi`.

## Features

### Babel Compiler

Add compiler option `transpiler` such that a user could run the babel toolchain to compiler their source code. With babel-typescript projects, there is a lot of tooling overhead. This feature aims to unify the tools.

```json
{
    "compilerOptions": {
        "transpiler": "babel",
        "outDir": "out"
    }
}
```

The typescript compiler uses `@babel/core`, which you should install as a peer dependency. Babel will look for its configuration using the `rootMode: 'upwards'` setting. To use source maps, you must specify this in your babel configuration. The typescript compiler will add a `sourceRoot` property to the source map determined by the source map location in the `outDir`.
