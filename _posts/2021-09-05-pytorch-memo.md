---
title: PyTorch Memo
tags:
- PyTorch
- dl
- note
date: 2021-09-05 09:51:00
---

# PyTorch Memo

本篇博客主要用来记录我在学习使用[PyTorch](https://pytorch.org/)的过程中的笔记、问题解决方案以及学习资源，仅供个人查阅参考。

<!-- more -->

官方网站：[PyTorch](https://pytorch.org/)

## 常用命令

创建、复制以及删除虚拟环境

```bash
conda create -n torch python=3.8  # 从头开始创建
conda create -n rl --clone torch  # 复制已经创建的虚拟环境
conda remove -n rl --all  # 删除创建的虚拟环境
```



安装cuda和cudnn，以支持GPU加速

```sh
conda install cuda=10.1
conda install -c cudnn=8.0
# cuda和cudnn的版本需做对应修改
```



检查PyTorch是否支持GPU加速

```python
print(torch.cuda.is_available())
```



## 学习资源

[1] [PyTorch学习资源](https://pytorch.zhangxiann.com/)，收集自知乎@[张贤同学](https://www.zhihu.com/people/zhangxiann/posts)，内容主要是作者个人学习Pytorch的笔记，适合基础入门。

