# vue-essentials

## How to install Vue.js

npm install -g @vue/cli

## How to **create** Vue project

- First, we must initialize a vue project, so run the following command on your terminal:

npm init vue@latest

- Once the project is created, follow the instructions in order to install dependencies and start the dev server:

cd <your-project-name>
npm install

https://vuejs.org/guide/quick-start.html

## How to **Run** Vue Project

- Once the project has all their dependencies installed in order to run the server just run:

npm run dev

## Vue File structure

<script>
  ... Logic Goes here
</script>

<template>
  ...Structure defined in HTML code goes here  
</template>

<style scoped>
  ...Styles defined in CSS goes here
</style>

## Vue has two approaches in order to build an app Vue 2 - Option Api and Vue 3 - Composition Api.

## Option API

Problems with bigger apps:

- Code that belongs together logically is split up across multiple options (data, methods, computed)

- Re-using logic across components can be tricky or cumbersome.

-

## Composition API`

Changes

- data(), methods, computed, watch [OPTION-API] => setup() [COMPOSITION-API]

- LifeCircle Methods changes in the composition API

Comparison between both approaches

Option API approach:

{
data() {
return { name: 'Mr. 🥔' };
},
methods: { beingFried() { ... }}
}

Composition API approach

{
setup() {
const name = ref('Mr. 🥔');
function beingFried() { ... };
return { name, beingFried}
}
}

Note: data and methods are replaced by
