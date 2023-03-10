### [typescript github issue 15300](https://github.com/microsoft/TypeScript/issues/15300#issuecomment-371353444)

关于 typescript 中 type 和 interface 定义和引用的讨论，参考下面的例子：

```ts
function fnA1<T extends Record<string, any>>() {}
function fnA2<T extends Record<string, string | number | boolean>>() {}

interface IA1 {
  a: string;
  b: number;
}

type IA2 = {
  a: string;
  b: number;
};

fnA1<IA1>(); // work
fnA2<IA1>(); // not work
fnA1<IA2>(); // work
fnA2<IA2>(); // work
```
