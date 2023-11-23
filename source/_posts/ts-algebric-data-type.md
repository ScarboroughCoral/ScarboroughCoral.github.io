---
title: 如何利用 Typescript 提高代码质量
date: 2023-11-23 10:53:32
tags:
- Typescript
- Type System
- ADT
---

{% note primary %}
类型也有代数运算，类型也有逻辑。
{% endnote %}

<!-- more -->

---

## 前言

本文适合以下读者：
1. 想了解为什么要使用 Typescript。本文会展示 Typescript 的优势
2. 对类型体操的实际应用有怀疑。本文会展示实际业务中常见类型应用
3. 想了解 ADT（代数数据类型）。类型也有概念上的加减乘除，这并不是类型体操。

## 主要内容

- Typescript 的优势
- 实际业务中常见类型操作应用
  - 代数数据类型
  - 穷尽枚举
- 代数数据类型拓展

### Typescript 的优势

优势是相对而言的，要说优势就是说 Typescript 相对于 Javascript 的优势。那么 Typescript 相对于 Javascript 的优势是什么呢？

最近作者面试一些前端开发人员，都会说 Typescript 是 JavaScript 的超集，提供了静态类型检查，但是仅限于使用 interface 和 type 定义类型，会使用一些简单的 Utility Types。这样回答往往表现的了解不够深入。

有些人可能会说出 interface 和 type 的区别够深入吗、会很多类型体操（例如使用类型进行排序）这样够深入吗、了解distributive conditional types 够深入吗？这确实能体现出你理解的深度，但是这些都是 Typescript 的语法特性，而不是 Typescript 的优势，这些往往在开发一些工具基础库的时候会使用，平常业务开发几乎不会使用到。

让我们先思考这样一个问题，Typescript 提供了静态类型检查，那我们可以通过静态类型检查来帮我做哪些事情呢？

静态类型检查可以让我们在类型出现错误的时候就会出现编译错误，这样就可以把这部分错误过滤掉，不会出现在运行时。往往运行时再去发现修改要比编译时发现修改成本要高的多，甚至需要在测试阶段发现。

既然如此，我们能不能尽可能的将代码错误或者说业务错误拦截在编译阶段呢？使用 Typescript 的一些方法可以帮我们做到这一点。

在说这些方法之前，我们先来思考一下什么是类型，我们可以通过集合的角度来思考类型，把类型当作集合、把值当作集合中的元素。如果了解过类型论就知道三个概念：项（可以先理解为变量）、类型、上下文。这三个概念的关系通常可以描述为在某个上下文中某个项是某个类型。例如下面这段代码：我们可以描述为在外层的作用域上下文中 a 这个项的类型是 number，在内层的作用域上下文中 a 这个项的类型是 string。

```typescript
const a: number = 1
{
    const a: string = 'a'
}
```

把类型当作集合、把值当作集合中的元素，就没办法把不属于这个集合的元素赋值给属于这个集合的变量。那么考虑一下 Typescript 中的这些类型。

```typescript
// boolean 这个集合中有两个元素 true 和 false，没法把不属于这个集合的元素赋值给属于这个集合的变量
const a: boolean = true 
const b: boolean = false
// @ts-ignore
const c: boolean = 1 // Type '1' is not assignable to type 'boolean'
```
