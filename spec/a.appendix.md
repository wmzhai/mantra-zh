# A. 附录: 预备知识

下面这些资源有助于您更加清晰地了解Mantra.

## ES2015

ES2015是2015年最新版的JavaScript语言标准，由于Meteor已经内置了ES2015支持，所以您不需要做任何额外的工作就可以直接使用。

ES2015是JavaScript世界最激动人心的事件，它引入了很多新特性，并解决了很多公共问题。

* [Learn ES2015: Say Hello to ES2015](https://tutor.mantrajs.com/say-hello-to-ES2015/introduction)

## React

React是一个基于JavaScript的UI框架。您可以在JavaScript里创建基于HTML内容，这个特性一开始看起来比较奇怪，不过适应以后会发现非常有用。下面是一些必要的资源：

* [官方教程](https://facebook.github.io/react/docs/tutorial.html)
* [Scotch.io的入门教程](https://scotch.io/tutorials/learning-react-getting-started-and-concepts)
* [React Components, Elements, and Instances](https://medium.com/@dan_abramov/react-components-elements-and-instances-90800811f8ca)

## React容器

我们目前很少使用React组件的状态，而是通过props获取数据，React的[无状态组件](https://medium.com/@joshblack/stateless-components-in-react-0-14-f9798f8b992d)使这项工作非常容易。

我们使用React容器从不同的数据源获取数据并加载到UI组件时，[react-komposer](https://github.com/kadirahq/react-komposer)使这项工作更加容易，下面这篇文章可以让您获取更多知识。

* [Let’s Compose Some React Containers](https://voice.kadira.io/let-s-compose-some-react-containers-3b91b6d9b7c8#.my9ynz9e2)

## Meteor基础

您需要对Meteor有一个相对深入的了解。可以遵循Meteor的[官方教程](https://www.meteor.com/tutorials/react/creating-an-app).

** Mantra在使用上述技术时略有不同，比如Meteor的React教程建议使用mixin获取Mongo集合数据。但是Mantra使用容器这种更加时髦的方式来使用React。**
