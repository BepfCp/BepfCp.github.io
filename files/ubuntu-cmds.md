Linux Shell Bash Frequently Used Commands

| 命令  | 含义                     |
| :---: | ------------------------ |
| cd -  | 快速回到上一次打开的目录 |
| ctr+a | 光标移动到行首           |
| ctr+e | 光标移动到行尾           |
| alt+d | 删除光标后一个单词       |
| ctr+w | 删除光标前一个单词       |

-----

`Nvidia-smi` Output Details

[nvidia-smi output](https://gitee.com/yichen_li/image/blob/master/pic/nvidia-smi.png)

| 名称              | 含义                                                      | 名称         | 含义                                                         |
| ----------------- | --------------------------------------------------------- | ------------ | ------------------------------------------------------------ |
| GPU               | GPU编号                                                   | Name         | GPU型号                                                      |
| Persistence-M     | 持续模式，耗能大，但是在新的GPU应用启动时，花费的时间更少 | Fan          | 风扇转速，从0到100%之间变动                                  |
| Temp              | 温度，单位是摄氏度                                        | Perf         | 性能状态，从P0到P12，P0表示最大性能，P12表示状态最小性能（ GPU 未工作时为P0，达到最大工作限度时为P12） |
| Pwr:Usage/Cap     | 能耗                                                      | Memory Usage | 显存使用率                                                   |
| Bus-Id            | GPU总线，domain:bus.device.function                       | Disp.A       | Display Active，表示GPU的显示是否初始化                      |
| Volatile GPU-Util | 浮动的GPU利用率                                           | Uncorr       | ECC：Error Correcting Code，错误检查与纠正                   |
| Compute M         | compute mode，计算模式                                    | /...         | 下方的 Processes 表示每个进程对 GPU 的显存使用率             |

----

