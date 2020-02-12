# vue-ui-delay

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

## How to make user actions async
First we need to have the mutation `removeLink` that does main data operation
```
 mutations: {
    REMOVE_ALL: state => {
      state.links = [];
    }
  },
```
then we declare action `removeAll` that will be used with `setTimeout`
```
actions: {
    removeAll({ commit }) {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          commit("REMOVE_ALL");
          resolve();
        }, 3000);
      });
    }
  }
  ```