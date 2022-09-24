# @jetvil/types

[![Bundle size](https://img.shields.io/bundlephobia/min/@jetvil/types/latest?label=Bundle%20Size&style=for-the-badge)](https://bundlephobia.com/package/@jetvil/types@latest)
[![Version](https://img.shields.io/npm/v/@jetvil/types?style=for-the-badge&color=cb3837&logo=npm)](https://www.npmjs.com/package/@jetvil/types)&nbsp;
![Downloads](https://img.shields.io/npm/dt/@jetvil/types?style=for-the-badge)&nbsp;
[![GitHub](https://img.shields.io/github/license/jetvil/types?style=for-the-badge)](https://github.com/jetvil/types/blob/main/LICENSE)&nbsp;
[![GitHub Repo stars](https://img.shields.io/github/stars/jetvil/types?color=E9E9E9&logo=Github&style=for-the-badge)](https://www.github.com/jetvil/types)&nbsp;
[![GitHub issues](https://img.shields.io/github/issues-raw/jetvil/types?label=issues&style=for-the-badge)](https://github.com/jetvil/types/issues)&nbsp;

Type related validation library for ES6+ and Typescript projects✅.

Also available in [@jetvil/core](https://npmjs.com/package/@jetvil/core)

# Features

- 🚀 **Easy to use**: Easy to install in your project.
- ✅ **ES6+ && TS**: TypeScript and ES6+ support(JS).
- 🐭 **Small footprint**: With less then 10kb, you won't even notice.
- 📦 **No dependencies**: You don't depend on anything else.
- 💵 **Free**: It's free and always will be, the beauty of open source.

# Getting Started

## Installation

To use this package, **install** using `npm`, `yarn` or `pnpm`📥:

```bash
# npm
npm install @jetvil/types
# yarn
yarn add @jetvil/types
# pnpm
pnpm install @jetvil/types
```

## Usage

```js
// ES6+ JavaScript CommonsJs
const types = require("@jetvil/types");
// TypeScript || ES6+ JavaScript module
import * as types from "@jetvil/types";
```

### Documentation

- [types](#types)
  - [isFalsy](#isfalsy)
  - [isFalsyExtended](#isfalsyextended)
  - [isTruthy](#istruthy)
  - [isTruthyExtended](#istruthyextended)
  - [isString](#isstring)
  - [isNumber](#isnumber)
  - [isBoolean](#isboolean)
  - [isExtendable](#isextendable)
  - [isRegExp](#isregexp)
  - [isDate](#isdate)

### Types

Type checking can be difficult, but with `@jetvil/types`, it's easy.

#### **isFalsy**:

Made from ['Falsy MDN defenition'](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).

```js
const { isFalsy } = require("@jetvil/types");
isFalsy(0); // true
isFalsy(1); // false
```

#### **isFalsyExtended**:

Made from ['Falsy MDN defenition'](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).</br>
Also includes Array and object checking.

```js
const { isFalsyExtended } = require("@jetvil/types");
isFalsyExtended(1); // false
isFalsyExtended(0); // true
isFalsyExtended([]); // true
isFalsyExtended({}); // true
```

#### **isTruthy**:

Everything not falsy is truthy. </br>
Made from ['Truthy MDN defenition'](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)

```js
const { isTruthy } = require("@jetvil/types");
isTruthy(1); // true
isTruthy(0); // false
```

#### **isTruthyExtended**:

Everything not falsy is truthy. </br>
Made from ['Truthy MDN defenition'](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
Also includes Array and object checking.

```js
const { isTruthyExtended } = require("@jetvil/types");
isTruthyExtended(1); // true
isTruthyExtended(0); // false
isTruthyExtended([]); // false
isTruthyExtended({}); // false
```

#### **isNullish**:

Check if value is null or undefined.

```js
const { isNullish } = require("@jetvil/types");
isNullish(null); // true
isNullish(undefined); // true
isNullish(0); // false
```

#### **isString**:

Check if value is a string.

```js
const { isString } = require("@jetvil/types");
isString("string"); // true
isString(1); // false
```

#### **isNumber**:

Check if value is a number.

```js
const { isNumber } = require("@jetvil/types");
isNumber(1); // true
isNumber(Infinity); // true
isNumber("string"); // false
```

#### **isBoolean**:

Check if value is a boolean.

```js
const { isBoolean } = require("@jetvil/types");
isBoolean(true); // true
isBoolean(false); // true
isBoolean("1"); // false
```

#### **isDate**:

Check if value is a date.

```js
const { isDate } = require("@jetvil/types");
isDate(new Date()); // true
isDate("1"); // false
```

#### **isRegExp**:

Check if value is a regular expression.

```js
const { isRegExp } = require("@jetvil/types");
isRegExp(/test/); // true
isRegExp(new RegExp("test")); // true
isRegExp("1"); // false
```

#### **isExtendable**:

Check if value is extendable for modification.

```js
const { isExtendable } = require("@jetvil/types");
isExtendable({}); // true
isExtendable([]); // true

const prevent = {};
Object.preventExtensions(prevent);
isExtendable(obj); // false

const sealed = {};
Object.seal(sealed);
isExtendable(sealed); // false

const frozen = {};
Object.freeze(frozen);
isExtendable(frozen); // false

const frozenArray = [];
Object.freeze(frozenArray);
isExtendable(frozenArray); // false

isExtendable(1 /**anything else then object or array */); // throws error
```
