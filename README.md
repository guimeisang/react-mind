# react-mind
[![npm downloads](https://img.shields.io/npm/dt/react-mind.svg?maxAge=2592000)](http://npmjs.com/package/react-mind)

react-mind is a JavaScript library for building mind, not only in react, also in angular, any web framwork

* **what:** react-mind only for building mind for react user

## 如何用

先引入npm包 ：    

`npm install react-mind`   

然后在你的react模块中： 

`import { Minder } from 'react-mind';`

在componentDidMout钩子函数中：

`var mind = Mind.show(options, mind);`

### params
```js
// options
var options = {
    container:'mind_container',   // 容器
    editable:true,  // 是否编辑
    theme:'primary' // theme 主题
}
```

```js
// mind
var mind = {
    "meta":{
        "name":"demo",  // 名称
        "author":"792300489@qq.com",  // 作者
        "version":"0.2",  // 版本
    },
    "format":"node_tree",  // 类型 
    "data":{"id":"root","topic":"mind","children":[
            {"id":"easy","topic":"Easy","direction":"left","expanded":false,"children":[
                {"id":"easy1","topic":"Easy to show"},
            ]},
    ]}   // 数据来源
};

```

* `format`
> `node_tree`代表是树形的结构  `node_array` 代表数组的结构；

* `expanded`:
> 判断是否展开

* `direction`:
> 判断该节点是在左侧还是右侧；

* `editable`
> 是否可以编辑，true为可以，false为不可以；

* `theme`
> 皮肤   
> 值：

### API
- `mind.get_data()`
> 获取数据

- `mind.set_readonly()`
> 设置为只读

- `mind.add_node("sub2","sub23", "new node", {"background-color":"red"});`
> 增加节点

- `mind.set_node_color('sub21', 'green', '#ccc');`
> 设置节点颜色

## Examples

We have several examples  Here is the first one to get you started:

[on the website](https://guimeisang.github.io/react-mind/example/demo1.html)

[on the website](https://guimeisang.github.io/react-mind/example/demo2.html)

[on the website](https://guimeisang.github.io/react-mind/example/demo3.html)


![普通思维导图](http://oi9n0t0p1.bkt.clouddn.com/mind_demo2.png)

![组织结构图](http://oi9n0t0p1.bkt.clouddn.com/react-mind/downMind.png)

```js
import { Minder } from 'react-mind';

var mind = {
    "meta":{
        "name":"demo",
        "author":"792300489@qq.com",
        "version":"0.2",
    },
    "format":"node_tree",
    "data":{"id":"root","topic":"mind","children":[
            {"id":"easy","topic":"Easy","direction":"left","expanded":false,"children":[
                {"id":"easy1","topic":"Easy to show"},
                {"id":"easy2","topic":"Easy to edit"},
                {"id":"easy3","topic":"Easy to store"},
                {"id":"easy4","topic":"Easy to embed","children":[
                    {"id":"easy41","topic":"Easy to show"},
                    {"id":"easy42","topic":"Easy to edit"},
                    {"id":"easy43","topic":"Easy to store"},
                    {"id":"open44","topic":"BSD License","children":[
                        {"id":"open441","topic":"on GitHub"},
                        {"id":"open442","topic":"BSD License"}
                    ]},
                    {"id":"easy45","topic":"Easy to embed"}
                ]}
            ]},
            {"id":"open","topic":"Open Source","direction":"right","children":[
                {"id":"open1","topic":"on GitHub"},
                {"id":"open2","topic":"BSD License","children":[
                    {"id":"open21","topic":"on GitHub"},
                    {"id":"open22","topic":"BSD License","children":[
                        {"id":"open221","topic":"on GitHub"},
                        {"id":"open222","topic":"BSD License"}
                    ]}
                ]}
            ]},
            {"id":"powerful","topic":"Powerful","direction":"right","expanded":false,"children":[
                {"id":"powerful1","topic":"Base on Javascript"},
                {"id":"powerful2","topic":"Base on HTML5"},
                {"id":"powerful3","topic":"Depends on you","expanded":false,"children":[
                    {"id":"powerful31","topic":"Base on Javascript"},
                    {"id":"powerful32","topic":"Base on HTML5"},
                    {"id":"powerful33","topic":"Depends on you"}
                ]}
            ]},
            {"id":"other","topic":"test node","direction":"left","children":[
                {"id":"other1","topic":"I'm from ajax"},
                {"id":"other2","topic":"I can do everything"}
            ]}
        ]}
};
var options = {
    container:'mind_container',
    editable:true,
    theme:'primary'
}
var mind = Mind.show(options,mind);
```

## TODO

- [x] 实现组织结构图，实现鱼骨图等多种效果，用字段`type`控制 --> 已经实现组织结构图，鱼骨图还未实现；
- [x] 添加在渲染前，渲染后，展开，收起等事件的回调函数；
- [x] 完善内部的事件系统；
- [x] 实现转为react组件化的形式，让引入更加便捷；
- [ ] 有什么想法的可以联系 792300489@qq.com;


## Installation

React-mind is available as the `react-mind` package on [npm](https://www.npmjs.com/).

## Contributing
this rope base on https://github.com/hizzgdev/jsmind @hizzgdev

### License

React-mind is [BSD licensed](./LICENSE). We also provide an additional [patent grant](./PATENTS).

React-mind documentation is [Creative Commons licensed](./LICENSE-docs).

Examples provided in this repository and in the documentation are [separately licensed](./LICENSE-examples).
