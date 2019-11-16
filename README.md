# template

这是 readthedocs 的模板，所有翻译的文档，都克隆这个文档进行创建；

本配置支持`Markdown`和`.ret`格式书写；

支持 `Markdown` 的表格；

## 克隆后的配置修改

### 更改`conf.py`

更改 `/docs/conf.py` 文件中的 `project`

```
project = u'文档名字-Title'
```

`project`的属性是在文档的左侧顶部，在整个文档的总标题；

### 更改  `/docs/index.rst`

更改 `/docs/index.rst` 文件顶部的介绍信息，这是类似文档的介绍信息；

## 文档左侧目录说明

### 不指定目录顺序

如果文档的左侧目录，**没有顺序要求**，`/docs/index.rst` 中可以使用如下配置

```
文档目录:

.. toctree::
   :maxdepth: 2
   :glob:

   source/*

```

### 指定目录顺序

如果文档的左侧目录，**需要按照顺序显示**，`/docs/index.rst` 中可以使用如下配置

```
文档目录:

.. toctree::
   :maxdepth: 2
   :glob:

   source/first_filename
   source/second_filename
   source/third_filename
   source/fourth_filename

```

### 目录需要归类

如果文档的左侧目录，**不仅需要顺序显示，还需要归类**，`/docs/index.rst` 中可以使用如下配置

```
.. toctree::
   :maxdepth: 2
   :caption: 用户使用文档

   source/first_filename
   source/second_filename


.. toctree::
    :maxdepth: 2
    :caption: API 参考

   source/third_filename
   source/fourth_filename

```

## 左侧目录来自哪里？

左侧目录来自您文档中的最高级标题（`h1`/`h2`/`h3` 这种）；

以 Markdown 格式为例；

- 如果文档内使用最高级的标题是`#`，那么所有`#`标题都会作为目录出现在左侧
- 如果文档内使用最高级的标题是`##`，那么所有`##`标题都会作为目录出现在左侧
