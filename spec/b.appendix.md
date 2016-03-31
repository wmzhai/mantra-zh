# B. 附录: 服务端目录结构

服务端目录结构不是Mantra的核心内容，不过它类似客户端的目录结构，有一个main目录以及一个 `main.js` 的js文件。

```
* methods
* publications
* libs
* configs
* main.js
```


## methods

应用程序的Method放在这个目录下，文件结构如下：

```
* posts.js
* index.js
* tests
  - posts.js
```

这里有一个`posts.js`文件，实现了应用程序里关于`posts`特性的一些method。这里有一个默认的导出函数，Meteor的Method就定义在这个函数里。

命名method名称的时候，需要一个前缀，前缀是文件名和一个点，比如 `posts.`

项目是一些 `posts.js` 内定义的method的例子：

```js
import {Posts, Comments} from '/lib/collections';
import {Meteor} from 'meteor/meteor';
import {check} from 'meteor/check';

export default function() {
  Meteor.methods({
    'posts.create'(_id, title, content) {
      //  method body
    }
  });

  Meteor.methods({
    'posts.createComment'(_id, postId, text) {
      //  method body
    }
  });
}
```

最后，需要一个 `index.js` 文件， 它可以导入目录下的其它模块并在默认导出里调用。 所以当导入方法时，我们可以用单个导入实现。

下面是一个`index.js`的例子：

```js
import posts from './posts';
import admin from './admin';

export default function () {
  posts();
  admin();
}
```

### 测试

我们可以为tests目录下的method编写测试，这时最好使用集成测试而不是单元测试。

具体内容可参考[Gagarin](https://github.com/anticoders/gagarin).

## publications

这个目录和`methods`一致，我们写发布而不是method。

## libs

这个目录包含一些在服务端使用的工具函数。

## configs

我们在这里写用用程序的配置信息，这些配置需要一个默认的导出函数，可以被导入和调用，配置代码需要在这个函数里编写。

下面是一个示例：

```js
export default function() {
  //  invoke the configuration here
}
```

## main.js

这里是整个应用程序启动的入口点，我们在这里导入method，发布和配置代码。

下面是一个`main.js`的示例：

```js
import publications from './publications';
import methods from './methods';
import addInitialData from './configs/initial_adds.js';

publications();
methods();
addInitialData();
```

注意： 可以看这个[样例代码](https://github.com/mantrajs/mantra-sample-blog-app/tree/master/server)来学习具体的实现方式。
