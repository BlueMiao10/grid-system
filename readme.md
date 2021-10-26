# grid-system
## 栅格系统 ## 

> 官方定义是：
> Bootstrap 包含了一个响应式的、移动设备优先的、不固定的网格系统，可以随着设备或视口大小的增加而适当地扩展到 12 列。

通俗来讲，在我们做页面时，如果想要实现响应式的效果，比如在不同屏幕宽度下展现不同的效果，就可以使用它。

具体做法：把页面分成12份，然后利用媒体查询，设置在什么界面占几份，从而实现一个切换。

先看HTML代码

```html
</div>
<div class="container">
  <div class="row">
    <div class="col-xs-12 col-sm-3">1</div>
    <div class="col-xs-12 col-sm-3">2</div>
    <div class="col-xs-12 col-sm-3">3</div>
    <div class="col-xs-12 col-sm-3">4</div>    
  </div>
</div>
```

当我们的页面比较小（比如手机上）时，我们希望它们占满十二格，而当我们屏幕拉大，比如在pc端上时，我们希望它们四个在同一行上均匀分布，即每个元素占四格。

因此我们将他们分类col-xs-12和col-sm-3。

css代码如下：

1. 首先我们将主页面container设置居中。

2. 接下来利用媒体查询将我们的主页面宽度分为以下几种情况：

- 页面宽度大于等于768px时，我们的主页面为750px

- 页面宽度大于等于992px时，我们的主页面为970px

- 页面宽度大于等于1200px时，我们的主页面为1170px

  

  大家会注意到，这样的话岂不是定义重合了嘛，但实际上后边的会覆盖前边的，比如当页面1300px时，虽然他三个条件都满足，但最后边的定义会覆盖前边的，即我们的主页面是1170px.

3. 再然后，我们先将我们的页面分成12份，确定每一份所需要占的空间是多少，其实就是将空间进行一个十二等分。
4. 接下来，我们需要根据不同的界面大小情况分别设置十二等分，并且这里有个需要注意的是：在我们页面变大的过程中，我们是希望他们在屏幕上横排的，所以在这里我们要将他们浮动起来，才可以实现这个效果，当然也不要忘记给他的父级元素消除浮动。
5. 最后就是设置一下他们的背景色啊边框字号这些就好了。

```css
{
box-sizing: border-box;
}

.container {
  background: yellow;
  padding-left: 10px;
  padding-right: 10px;
  margin-right: auto;
  margin-left: auto;
}


.container::after{
  content: '';
  display: block;
  clear: both;
}

.row {
  margin-left: -10px;
  margin-right: -10px;
}

@media (min-width: 768px) {
  .container {
    width: 750px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 970px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1170px;
  }
}


.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}



@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }

}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }

}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }

}



.row > * {
  border: 1px solid;
  text-align: center;
}

.aside {
  min-height: 200px;
  background: pink;
}

.main {
  min-height: 300px;
  background: grey;
}
}
```

