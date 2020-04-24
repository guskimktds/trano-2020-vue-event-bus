# vue-event-bus

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

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

﻿부모 자식 관계 컴포넌트 간의 통신, 이벤트, 그리고 어려운 문제들

자식 컴포넌트에서 부모 컴포넌트의 스코프를 직접 변경할 수 없으므로 변경사항을 이벤트를 이용하여 전파
자식 컴포넌트 $emit 메소드 발생 => 부모 컴포넌트 v-on 지시자로 이벤트 리스닝
자식 컴포넌트가 부모 컴포넌트 스코프에 대한 변경을 진행하게 되면 에러 발생

[Vue warn]: Avoid mutating a prop directly since the value will be overwritten whenever the parent component re-renders. Instead, use a data or computed property based on the prop's value. Prop being mutated: "title


=> 중복되어 값이 쓰여지므로 자식 요소에서 직접 호출하지 말고 특정 데이터 또는 계산된 속성을 사용하라는 경고
따라서 자식 컴포넌트의 변경에 대해 App 컴포넌트까지 이벤트를 전파하여 상태를 변경해야 한다.
App 컴포넌트가 전파된 상태 변경을 위한 ID 값이 필요

예제에서 App.vue 에 선언된 title 변수값을 header 에서 변경하기위해 Eventbus bus.$emit 를 사용해 Footer 에서 props 로 받은 title 을 직접 변경하지말고 bus.$on 을 상위(부모)컴포넌트에서 받아서 title을 변경해줘야 오류가 없다. 

﻿
﻿
