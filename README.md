# 古诗词数据库

这个古诗词数据库是2017年从古诗文网爬取下来的，目前的数据总量虽不及古诗文网，但其诗词数据进行了一定的清洗整理和格式化。这个古诗词数据目前主要有73281首古诗词和3156个诗人的详细数据，并且已经应用在两个应用上：[诗鲸Android客户端和诗鲸微信小程序](https://sspai.com/post/43820)。

![image](miniapp.jpg)

# 数据说明

### 1.gushiwen 文件夹

这个文件夹下面是爬虫爬取的原始内容，其中 `view` 文件夹里面是一首首古诗，`author` 文件夹里面是一个个诗人，`ju` 文件夹里面是一些诗词名句。

### 2.image 文件夹

这个文件夹下面是是人的头像图片，`image_xxx.jpg`表示这是编号为xxx的诗人的头像URL地址。

### 3.data 文件夹

这个文件夹是目前最新的整理数据，其中子目录 `poetry` 里面是一首首古诗，`poet` 里面是一个个诗人，`aio` (all in one) 存放的文件是将诗人和诗词数据整理到一个文件的结果。

### 4.其他文件夹

其他文件夹中的内容是为了应用向下兼容而保留的旧版本的整理数据，可以不用关注。

# 数据结构

### 1.诗词数据

`id`是诗词在古诗文网上的索引(最近古诗文网改版了，已经不是用id了)，`name`是诗词的名称，`content`是诗词的内容，`dynasty`是诗词的朝代，`star`是数据爬取时这首诗词的点赞人数，`poet`是诗人的信息，`fanyi`是诗词的注释和释义等数据，`shangxi`是诗词的赏析，`about`是关于这首诗词的其他内容，例如诗人的创作背景等，在古诗文网凡不是诗词释义和诗词赏析的内容都会归总到关于诗词的内容中。


```
{
  "about": "创作背景\n\n　　唐玄宗天宝初年，李白xxx",
  "content": "君不见，黄河之水天上来，奔流到海不复回。xxx",
  "dynasty": "唐代",
  "fanyi": "译文\n你难道看不见那黄河之水从天上奔腾而来，波涛翻滚直奔东海，从不再往回流。xxx",
  "id": 7722,
  "name": "将进酒",
  "poet": {
    "desc": "李白（701年－762年），字太白，号青莲居士，唐朝浪漫主义诗人，被后人誉为“诗仙”。xxx",
    "id": 247,
    "image": "https://raw.githubusercontent.com/hujiaweibujidao/poetry/master/image/image_247.jpg",
    "name": "李白",
    "star": 0
  },
  "shangxi": "鉴赏\n\n　　将进酒，唐代以前乐府歌曲的一个题目，内容大多咏唱饮酒放歌之事。xxx",
  "star": 32615,
  "tags": [
    "乐府",
    "唐诗三百首",
    "咏物",
    "抒情",
    "哲理",
    "宴饮"
  ]
}
```


### 2.诗人数据

`id`是诗人在古诗文网上的索引(最近古诗文网改版了，已经不是用id了)，`name`是诗人的姓名，`desc`是诗人的简介，`content`是诗人的详细介绍，`dynasty`是诗人的朝代，`star`是数据爬取时这个诗人的点赞人数。

```
{
  "content": "轶事典故\n\n姓名由来\nxxx",
  "desc": "李白（701年－762年），字太白，号青莲居士，唐朝浪漫主义诗人，被后人誉为“诗仙”。xxx",
  "dynasty": "唐代",
  "id": 247,
  "image": "https://raw.githubusercontent.com/hujiaweibujidao/poetry/master/image/image_247.jpg",
  "name": "李白",
  "star": 4895
}
```

# LICENSE

[GNU General Public License version 3](http://www.gnu.org/licenses/gpl.txt)

Copyright (c) 2018 Javayhu. All rights reserved.
