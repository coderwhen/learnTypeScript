# TypeScript命名空间

## 说明
```
命名空间：增强对内部模块的兼容性（闭包）
注意：不要命名空间与模块混用
```

## 代码
```ts
// a.ts
namespace Shape {
    export function square(x: number) {
        return x ** 2
    }
}
// b.ts
// 引用部分ts文件
/// <reference path="a.ts" />

/**
 * Shape命名空间
 */
namespace Shape {
    const pi = Math.PI
    /**
     * 求圆的面积
     * @param r 半径
     */
    export function cricle(r: number) {
        return pi * r ** 2
    }
}

// 类型别名
import square = Shape.square
import cricle = Shape.cricle
// 调用命名空间的方法
console.log(square(3))
console.log(cricle(3))

```