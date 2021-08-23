---
title: 我的学习方法论
mathjax: false
copyright: true
comment: true
date: 2020-03-15 12:51:20
tags:
- Method
categories:
- Method
photo: http://img3.333cn.com/img333cn/2017/11/13/1510561438273.jpg
---

{% note success %}
我应该如何高效学习。
{% endnote %}

<!-- more -->

---

## 为什么写这篇文章

毕业之际，入职之际。需要学的东西铺天盖地而来，如何高效的学习，高效的完成个人任务是现在必须要思考的。

我只喜欢做我自己喜欢做的事情（相信大多数人也是）。我这个人比较懒，执行力比较差，只要开始动手做就想做，不做就一点心思没有，这有点像看剧打游戏的我，不想刷剧一刷又停不下来。。。感觉是大学学坏的毛病。

## 如何高效学

如果自己想学点东西如何去学才学得快？读书？看视频？认真记笔记？

### 哪里找资源

从这些网站去找需要哪些资源，而不是资源就在这。

- [谷歌](https://www.google.com/)
- [知乎](https://www.zhihu.com/)


### 快速入手选择视频+文档

比如需要入门新的语言，读厚书无疑很慢，官方文档如果教程很差，你应该怎么办？

- 找一些相关MOOC，**2倍播放~**
- **第三方文档**有没有好点的！

### 快速入手后通过Coding和思考快速提升

快速入手了之后还是有些问题不会解决，或者没接触过，这需要加强练习。
比如入门新的语言，你可以入手之后开始刷题。如果是一个新工程策略，你可以简单的搭建一个demo

- [LeetCode再刷一遍做过的题](https://leetcode-cn.com/)
- [CodeWars刷一刷简单题或者是刷过的题](https://www.codewars.com/)
- [谷歌code实验带你飞](https://codelabs.developers.google.com/)

### 系统学习需要慢慢地来读书

这是需要日积月累的过程！做好计划，每日读书，每周读书。

### 笔记没那么重要！

不用做详细的笔记，太浪费时间！**只做简要的笔记就够了！不会的时候回查就行了！**

## 如何做

学了之后怎么去做？

### High Priority First

{% note primary%}
高优先级第一。
{%endnote%}

执行力差！尽力去做！养好心态！

## 总结

用Promise来描述。用async await感觉语义化不是很强。

```js
let how2Learn=new Promise(resolve=>("需要学东西",resolve()))
  .then(()=>("找资源","这是资源"))
  .then(res=>`learn ${res}(MOOC+文档)`)
  .then(res=>"刷题深刻理解&&开始干活")
let systemLearn=async function(days){
  while(days--){
    await new Promise(r=>setTimeout(86400000,()=>("每日读书",r())))
  }
}
Promise.all([how2Learn,systemLearn()])
  .then(()=>"I have learned it.")
```

**文字描述：**

```
需要学东西=>找资源=>MOOC文档快速入手=>刷刷题案例或者直接开始干活
                ||
                ==> 同时计划系统学习=>读书，简单记笔记
```