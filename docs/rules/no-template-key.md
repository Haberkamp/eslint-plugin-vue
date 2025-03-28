---
pageClass: rule-details
sidebarDepth: 0
title: vue/no-template-key
description: disallow `key` attribute on `<template>`
since: v3.4.0
---

# vue/no-template-key

> disallow `key` attribute on `<template>`

- :gear: This rule is included in all of `"plugin:vue/essential"`, `*.configs["flat/essential"]`, `"plugin:vue/vue2-essential"`, `*.configs["flat/vue2-essential"]`, `"plugin:vue/strongly-recommended"`, `*.configs["flat/strongly-recommended"]`, `"plugin:vue/vue2-strongly-recommended"`, `*.configs["flat/vue2-strongly-recommended"]`, `"plugin:vue/recommended"`, `*.configs["flat/recommended"]`, `"plugin:vue/vue2-recommended"` and `*.configs["flat/vue2-recommended"]`.

Vue.js disallows `key` attribute on `<template>` elements.

## :book: Rule Details

This rule reports the `<template>` elements which have `key` attribute.

<eslint-code-block :rules="{'vue/no-template-key': ['error']}">

```vue
<template>
  <!-- ✓ GOOD -->
  <div key="foo"> ... </div>
  <template> ... </template>

  <!-- It's valid for Vue.js 3.x -->
  <template v-for="item in list" :key="item.id"> ... </template>

  <!-- ✗ BAD -->
  <template key="foo"> ... </template>
  <template v-bind:key="bar"> ... </template>
  <template :key="baz"> ... </template>
</template>
```

</eslint-code-block>

::: tip Note
This rule does not report keys placed on `<template v-for>`. It's valid for Vue.js 3.x. If you want to report keys placed on `<template v-for>` invalid for Vue.js 2.x, use [vue/no-v-for-template-key] rule.
:::

## :wrench: Options

Nothing.

## :couple: Related Rules

- [vue/no-v-for-template-key]

[vue/no-v-for-template-key]: ./no-v-for-template-key.md

## :books: Further Reading

- [API - Special Attributes - key](https://vuejs.org/api/built-in-special-attributes.html#key)

## :rocket: Version

This rule was introduced in eslint-plugin-vue v3.4.0

## :mag: Implementation

- [Rule source](https://github.com/vuejs/eslint-plugin-vue/blob/master/lib/rules/no-template-key.js)
- [Test source](https://github.com/vuejs/eslint-plugin-vue/blob/master/tests/lib/rules/no-template-key.js)
