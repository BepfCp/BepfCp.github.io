---
title: 【MEMO】Linux
tags:
- Linux
date: 2022-10-13 05:10:00
---

# Hands-on Linux

本篇博客主要用来记录我在学习使用Linux的过程中的笔记、问题解决方案以及学习资源，仅供个人查阅参考。

## bash 操作

```bash
# 关闭或打开图形界面
sudo service gdm stop  # 临时关闭图形界面，节省显存
sudo service gdm start  # 打开图形界面

# 创建新用户
sudo adduser [username]  # 添加用户
sudo usermod -aG sudo [username]  # 给用户添加sudo权限
su - [username]  # 切换用户名

# 更改组权限
chgrp -R conda mujoco_py

# 后台运行命令
nohup python -u test.py > log.txt 2>&1 &

# 清空无效内存占用
sync
sudo sh -c "echo 3 > /proc/sys/vm/drop_caches"
```

## Tmux

```bash
tmux new -s [name]  # 创建session
tmux ls  # 显示session列表
tmux kill-session -t [num]  # 停止session
tmux attach -t [num]  # 重新登入session
ctr+b+d  # 退出session
```

