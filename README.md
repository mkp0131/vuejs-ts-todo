# vue-ts

## [vue] vue 타입스크립트 프로젝트 생성

- vue cli 를 통해 생성!

```
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, TS, Router, Vuex, Linter
? Choose a version of Vue.js that you want to start the project with 2.x
? Use class-style component syntax? No
? Use Babel alongside TypeScript (required for modern mode, auto-detected
polyfills, transpiling JSX)? Yes
? Use history mode for router? (Requires proper server setup for index fallback
in production) Yes
? Pick a linter / formatter config: Prettier
? Pick additional lint features: Lint on save
? Where do you prefer placing config for Babel, ESLint, etc.? In dedicated
config files
? Save this as a preset for future projects? (y/N) No
```

### eslint 설정은 그대로 진행한다.

- https://lililli.kr/archives/2877

## [vue] 타입스크립트 생성시 달라진 snippet

- `ts` -> `vbase-ts` 로 뷰의 기본 형식을 생성

## [vuex] 타입스크립트 type interface 정의 

### 참고문서

- https://romeoh.tistory.com/entry/VUE-TYPESCRIPT-Vuex-Interface%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EB%8A%94-Store
- https://vuex.vuejs.org/guide/typescript-support.html


## [typescript] 타입스크립트 타입 지정 예제

### object 예제

```ts
interface ITodo {
  todoTxt: string;
  todos: string[];
}
```

### object 의 값들 중 하나의 타입지정

```ts
{
  todos: [] as Todo
}
```

## [vue] vue css class if

- `:class` 를 활용하여 `computed` 변수를 넣는다.

```js
<span class="item" :class="todoItemClass" @click="toggleItem">{{
      todoItem.title
    }}</span>



export default Vue.extend({
  computed: {
    todoItemClass(): string | null {
      return this.todoItem.done ? "complete" : null;
    }
  },
```

## [typescript] fetch axios ajax 모델화

- json 을 반환하는 반환값에 타입을 지정한다.

```js
fetch(): Todo[] {
    const todoItems = localStorage.getItem(STORAGE_KEY) || "[]";
    const result = JSON.parse(todoItems);
    return result;
  }
```