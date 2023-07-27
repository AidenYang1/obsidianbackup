# 整体代码实现

```powershell
<section style="display: block; overflow: scroll hidden; perspective: 1px;" data-mpa-powered-by="yiban.io">

    <svg viewBox="0 0 1500 900" style="display: block;max-width: none !important;transform:rotate(0);" width="300%"
        opacity="1">
        <foreignObject x="0" y="0" width="500" height="900">
            <svg height="900"
                style="display: block;background-image: url(&quot;<https://mmbiz.qpic.cn/mmbiz_png/LAhzuclLxJVTmp321tu66em9KauQmJQ966ktNZQrnEF5yRR5UR10LxCicg2T81jibQw1ncyPR1p0OVNJLibdf0AnQ/640?wx_fmt=png>);background-size: cover;"
                width="500">
            </svg>
        </foreignObject>
        <foreignObject x="499" y="0" width="500" height="900">
            <svg height="900"
                style="display: block;background-image: url(&quot;<https://mmbiz.qpic.cn/mmbiz_png/LAhzuclLxJUseb8VCyUkiaOSXFAP94OgibGHr1uwc5LsASDGrelvb3Rf9xvcPFMTqmpHVxNpkYcefibmZtwlEUAuQ/640?wx_fmt=png>);background-size: cover;"
                width="500">
            </svg>
        </foreignObject>
        <foreignObject x="998" y="0" width="500" height="900">
            <svg height="900"
                style="display: block;background-image: url(&quot;<https://mmbiz.qpic.cn/mmbiz_png/LAhzuclLxJUseb8VCyUkiaOSXFAP94OgibGHr1uwc5LsASDGrelvb3Rf9xvcPFMTqmpHVxNpkYcefibmZtwlEUAuQ/640?wx_fmt=png>);background-size: cover;"
                width="500">
            </svg>
        </foreignObject>

    </svg>
</section>
<p style="display: none;">
    <mp-style-type data-value="3">
    </mp-style-type>
</p>
```

# 分析

## 代码块1—幕布

```powershell
<svg viewBox="0 0 1500 900" style="display: block;max-width: none !important;transform:rotate(0);" width="300%"
        opacity="1">
```

-   这一条代码是指的幕布的大小，viewBox="0 0 1500 900"是设置幕布的长度和宽度。
-   style="display: block;max-width: none !important;transform:rotate(0);" 是设置风格样式
-   width="300%"，其中的width理解为在屏幕中显示这块幕布几分之几的内容。

## 代码块2—盒子

```powershell
<foreignObject x="0" y="0" width="500" height="900">
           
        </foreignObject>
```

-   foreignObject是这块幕布里面的每个的单独的盒子；
-   x="0" y="0" 指的是这个盒子在幕布中的xy轴定位；
-   width="500" height="900"表示盒子宽高。

## 代码块3—图片

```powershell
<svg height="900"
                style="display: block;background-image: url(&quot;<https://mmbiz.qpic.cn/mmbiz_png/LAhzuclLxJVTmp321tu66em9KauQmJQ966ktNZQrnEF5yRR5UR10LxCicg2T81jibQw1ncyPR1p0OVNJLibdf0AnQ/640?wx_fmt=png>);background-size: cover;"
                width="500">
            </svg>
```

-   height="900"，width="500"是图片的宽高；
-   style="display: block;是显示风格；
-   background-image: url("[https://mmbiz.qpic.cn/mmbiz_png/LAhzuclLxJVTmp321tu66em9KauQmJQ966ktNZQrnEF5yRR5UR10LxCicg2T81jibQw1ncyPR1p0OVNJLibdf0AnQ/640?wx_fmt=png](https://mmbiz.qpic.cn/mmbiz_png/LAhzuclLxJVTmp321tu66em9KauQmJQ966ktNZQrnEF5yRR5UR10LxCicg2T81jibQw1ncyPR1p0OVNJLibdf0AnQ/640?wx_fmt=png));图片链接；
-   background-size: cover;是按照图片的比例放大或者缩小至充满容器（盒子）；不缩放；

# 使用注意

-   幕布的宽要等于三张图像的宽；
-   幕布的高保持不变；
-   盒子的定位，需要每多一个减少1px，想要在500px的图像后紧跟第二张图，受盒子因素。需要设置第二个盒子的x轴定位在499.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/164c1add-4b51-4ec5-aab9-aef437f6d53f/Untitled.png)

-   可以假设图像是贴盒子左边的，但是盒子会留一个内缝隙，1px的。