---
layout: docs
title: Options
description: Options for 6to5 transpiling.
permalink: /docs/usage/options/
---

## Usage

```js
to5.transform(code, options);
```

```sh
$ 6to5 --name=value
```

## Options

| Option                   | Default              | Description                     |
| ------------------------ | -------------------- | ------------------------------- |
| `filename`               | `"unknown"`          | Filename for use in errors etc. |
| `filenameRelative`       | `(filename)`         | Filename relative to `sourceRoot`. |
| `blacklist`              | `[]`                 | Array of transformers to **exclude**. Run `6to5 --help` to see a full list of transformers. |
| `whitelist`              | `[]`                 | Array of transformers to **only** use. Run `6to5 --help` to see a full list of transformers. |
| `loose`                  | `[]`                 | Array of transformers to enable [loose mode](/docs/usage/loose) on. |
| `optional`               | `[]`                 | Array of transformers to [optionally](/docs/usage/transformers#optional) use. Run `6to5 --help` to see a full list of transformers. Optional transformers displayed inside square brackets. |
| `modules`                | `"common"`           | Which module formatter to use. Run `6to5 --help` to see a full list of module formatters. |
| `sourceMap`              | `false`              | If truthy, adds a `map` property to returned output. If set to `"inline"`, a comment with a sourceMappingURL directive is added to the bottom of the returned code. |
| `sourceMapName`          | `(filenameRelative)` | Set `file` on returned source map. |
| `sourceFileName`         | `(filenameRelative)` | Set `sources[0]` on returned source map. |
| `sourceRoot`             | `(moduleRoot)`       | The root from which all sources are relative. |
| `moduleRoot`             | `(sourceRoot)`       | Optional prefix for the AMD module formatter that will be prepend to the filename on module definitions. |
| `moduleIds`              | `false`              | If truthy, insert an explicit id for modules. By default, all modules are anonymous. (Not available for `common` modules) |
| `comments`               | `true`               | Output comments in generated output. |
| `reactCompat`            | `false`              | Makes the `react` transformer produce pre-v0.12 code |
| `keepModuleIdExtensions` | `false`              | Keep extensions in module ids |
| `runtime`                | `false`              | Uses a reference to `to5Runtime` instead of placing helpers at the top of your code. Meant to be used in conjunction with the [optional runtime](/docs/usage/runtime). |
| `code`                   | `true`               | Enable code generation |
| `ast`                    | `true`               | Include the ÅST in the returned object |
| `format`                 | [(See Formatting Options)](#formatting-options) | Formatting options for code generation |
| `playground`             | `false`              | Enable [playground](/docs/usage/playground) support. |
| `experimental`           | `false`              | Enable support for [experimental](/docs/usage/experimental) ES7 features. |

## Formatting Options

**Usage**

```js
to5.transform(code, { format: formattingOptions });
```

| Option                          | Default              | Description                     |
| ------------------------------- | -------------------- | ------------------------------- |
| `parentheses`                   | `true`               | Preserve parentheses in new expressions that have no arguments |
| `comments`                      | `true`               | Output comments in generated output |
| `compact`                       | `false`              | Do not include superfluous whitespace characters and line terminators |
| `indent`                        | `{...}`              | Indent options |
| `indent.adjustMultilineComment` | `true`               | Adjust the indentation of multiline comments to keep asterisks vertically aligned |
| `indent.style`                  | `'  '`               | Indent string |
| `indent.base`                   | `0`                  | Base indent level |
