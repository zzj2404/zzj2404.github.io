---
title: pyecharts的使用
categories: 可视化
---

[效果实例和代码](https://gallery.pyecharts.org/#/README)\
[文档](https://pyecharts.org/#/zh-cn/)
# 安装
```bash
pip install pyecharts
```
# 基本使用
## 单独调用

```python
bar = Bar(init_opts=opts.InitOpts())
bar.add_xaxis(["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"])#如果不是字符串类型貌似有bug
bar.add_yaxis("商家A", [5, 20, 36, 10, 75, 90])
bar.set_global_opts(title_opts=opts.TitleOpts(title="主标题", subtitle="副标题"))
bar.render('path.html')
```
## 链式调用
```python
bar = (
    Bar()
    .add_xaxis()
    .add_yaxis()
    .render()
)
```

初始化配置
```python
init_opts=opts.InitOpts(
    # 图表画布宽度，css 长度单位。
    width= "900px",
    # 图表画布高度，css 长度单位。
    height= "500px",
    # 网页标题
    page_title = "Awesome-pyecharts",
    # 图表主题
    theme= "white",
    # 图表背景颜色
    bg_color= None,
    )

```

# 折线图

```python
c = (
    Line(init_opts=opts.InitOpts(
        width='1700px',
        height="1000px")#设置画布大小
    )
        .add_xaxis([str(i) for i in sub['DATE'].index.values])
        .add_yaxis(
        "商家A",
        list(sub['TEMPERATURE']),
        is_smooth=True,
    )
        .set_global_opts(title_opts=opts.TitleOpts(title="Line-MarkLine"),
                axispointer_opts=opts.AxisPointerOpts(
                            is_show=True, link=[{"xAxisIndex": "all"}]
                        ),
    )
        .render(os.path.join(target_dir, "line_markline.html"))
)
```