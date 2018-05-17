## 不依赖relative的绝对定位absolute
在使用absolute定位属性的时候，一直都是会给父元素或者祖先元素设置position:relative定位属性，以及设置absolute定位元素的top/right/bottom/left的方向值，有的时候甚至设置层级关系的z-index属性值。其实它是可以不依赖relative进行使用，可以理解为无依赖的绝对定位。
#### absolute属性是独立的css属性值，其样式和行为表现可以不依赖其他任何css属性完成。
### 1、简单的定义
无依赖的绝对定位：给元素设置absolute定位属性，不通过top/right/bottom/left去控制元素位置，而是通过margin或者transform来控制。
### 2、相对自身的特性
我们通常熟知的一个元素使用了absolute绝对定位的话，它是相对于static定位以外的第一个祖先元素进行定位的。无依赖的绝对定位相对的参考点和我们通常熟知的绝对定位的参考点不一样，它是相对其自身在dom中的位置，可以理解和relative一样！
### 3、不受overflow:hidden的影响
使用无依赖绝对定位的元素是不受父元素overflow:hidden的影响，不会被剪裁。
***
以上来自 掘金 作者：yuanyong 链接：https://juejin.im/post/5afbdc68518825429d1f7a6b
***
没有设置定位值的absolute元素是个普通又不普通的元素，普通之处在于其依旧在DOM tree中，对margin等属性敏感；不普通在于其实际的高宽都丢失了。这非常类似于浮动(float)，浮动的本质就是“包裹与破坏”，破坏高度，浮动元素的实际占据高度为0（具体点这里）；而absolute元素（无定位值）也是“包裹与破坏”，只是其“破坏”比float更加凶猛，不仅实际的高度没有，连实际的宽度也没有。说句不严谨的结论：绝对定位元素就是个比浮动元素更加变态的近亲
### 自适应布局
没有定位值的absolute元素是个更加变态的float元素，所以浮动元素干的某些事情absolute元素也能做，例如自适应布局。absolute绝对定位的非绝对定位应用肯定还有其他，只要记住无定位值的absolute元素就是个连实际宽度也没有的float浮动元素就可以了