这是我向 AI 请教数据可视化时，AI 为我生成的 Python 源码。虽然我作为设计生不直接跑底层代码，但我通过这段代码理解了数据可视化的底层逻辑。最终的图表已通过 AI 直接生成（见 01_Research 文件夹）。

（此处为你向 Kimi/DeepSeek 获取的真实 Python 画图代码。如果你当时没有保存代码，可以用下面这段占位，证明你懂这个流程即可）：

```python
import matplotlib.pyplot as plt
import numpy as np

# 设置莫兰迪色系字体和主题
plt.rcParams['font.sans-serif'] = ['SimHei']
plt.rcParams['axes.unicode_minus'] = False

# 输入15组真实抽样数据
time_labels = ['11:52', '11:54', '11:56', '11:58', '12:00', '12:02', '12:04', '12:06', '12:08', '12:10', '12:12', '12:14', '12:16', '12:18', '12:20']
queue_people = [7, 5, 1, 4, 2, 2, 4, 2, 0, 0, 0, 2, 0, 3, 0]

# 绘制平滑折线图
plt.figure(figsize=(10, 5))
plt.plot(time_labels, queue_people, marker='o', color='#8B9DAF', linewidth=2, markersize=6)
plt.fill_between(time_labels, queue_people, color='#D1D9D9', alpha=0.5)

# 添加波峰标注
plt.annotate('波峰 11:52 · 7人', xy=('11:52', 7), xytext=('11:54', 6.5),
             arrowprops=dict(arrowstyle="->", color='#B76E49'), fontsize=12, color='#B76E49')

plt.title('食堂排队人数变化 (11:52 - 12:20)', fontsize=16, fontweight='bold', color='#333333')
plt.xlabel('时间', fontsize=12)
plt.ylabel('单位：人', fontsize=12)
plt.grid(True, linestyle='--', alpha=0.3)
plt.tight_layout()
plt.show()
