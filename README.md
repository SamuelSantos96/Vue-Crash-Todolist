# Vue Crash Todolist

Vue JS Crash Course

Source: [Traversy Media at Youtube](https://www.youtube.com/watch?v=Wy9q22isx3U)

## Setup

```shell
npm i -g @vue/cli
```

### VS Code Plugin

Vetur by Pine Wu

## Create Project CLI Version

```shell
vue create app
```

## Run Project CLI Version

```shell
npm run serve
```

## Create Project UI Version

```shell
vue ui
```

## Run Project UI Version

Go to the left nav bar and click 'Tasks' -> Choose 'serve' -> Click 'Run task' -> After running click 'Open app' on the right side

## Turn Off SnoreToast Notifications

While developing the web applications a pop up keeps appearing saying 'Build failed' or 'Build fixed'.

Turn it off on OS Notifications.

## Difference betwen v-on:click and @Click

They are basically the same, the difference is that one is more verbose than the other. [stackoverflow](https://stackoverflow.com/questions/45369553/difference-between-click-and-v-onclick-vuejs)

Full Syntax

```vue
<a v-on:click="doSomething"></a>
```

Shorthand

```vue
<a @click="doSomething"></a>
```

### Other Examples of Long Form and Shorthand

```vue
<a v-on:keyup="doSomething"></a>
```

```vue
<a @keyup="doSomething"></a>
```

and

```vue
<a v-bind:href="doSomething"></a>
```

```vue
<a :href="doSomething"></a>
```
