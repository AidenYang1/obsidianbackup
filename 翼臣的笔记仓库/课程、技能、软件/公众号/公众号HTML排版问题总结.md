### 解决HTML中盒子里面的图像在盒子末尾留缝隙问题

往div盒子里塞图片img标签。img标签是行内元素。行内元素会自动换行，变成块元素即可。

下面的代码会出现盒子留缝隙问题

```powershell
<div class="box2" style="width:100%;height:auto;pointer-events: none;margin:0;padding:0;">
            <img class="pic" style="width:100%;height: auto;"
                src="<https://mmbiz.qpic.cn/mmbiz_gif/LAhzuclLxJUseb8VCyUkiaOSXFAP94OgibMVZAPsZq1tsibpWuk5KsntJ1sHrdtbWSG9qqiaRqYMaURTibsGCicXKkicw/640?wx_fmt=png>">
        </div>
```

像img标签，加style，属性为display：block修改后正常。

```powershell
<div class="box2" style="width:100%;height:auto;pointer-events: none;margin:0;padding:0;">
            <img class="pic" style="width:100%;height: auto;display: block;"
                src="<https://mmbiz.qpic.cn/mmbiz_gif/LAhzuclLxJUseb8VCyUkiaOSXFAP94OgibMVZAPsZq1tsibpWuk5KsntJ1sHrdtbWSG9qqiaRqYMaURTibsGCicXKkicw/640?wx_fmt=png>">
        </div>
```

### 解决微信公众号中div块会自动生成一个间隙。

在每个div盒子里面margin-top设置-9px左右的值。

### 左右滑动图片模块的背景不露馅。

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a57287ba-a3ba-43cd-918e-6c836a77e91b/Untitled.png)

## 为什么需要设置背景图片而不是设置背景颜色？

<aside> <img src="/icons/exclamation-mark_green.svg" alt="/icons/exclamation-mark_green.svg" width="40px" /> 微信公众号在深色模式下黑色会变成和背景一样的灰色。所以需要设置背景图片

</aside>

## 设置方法

```html
<section style="display: block;width:auto;height:auto;background-image:url(放置图片url) ">
           
        </section>
<!--注意：必须设置盒子的宽度和高度，如果不需要固定大小，只需要根据盒子里面的内容进行自动展开-->
<!--style添加下列代码即可-->
width:auto;height:auto;
```

### 盒子模型的理解