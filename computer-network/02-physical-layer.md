<!--
  vi: ft=pandoc.markdown
-->

# 物理层

功能
: 屏蔽传输介质差异, 提供bit流的传输服务

设备
: 中继器(放大), HUB(集中, 广播, 半双工)

## 信道极限容量

奈氏准则
: $C = 2 w\log_2 M$

香农公式
: $C = w \log_21+S/N$

信噪比
: $\text{信噪比(dB)} = 10\log_10(S/N)$

<div class="example">
在无噪声情况下, 若某通信链路的带宽为3khz, 采用4个相位, 每个相位具有4种振幅的QAM调制技术, 则该通信链路的最大数据传输速率是

$C = 2 \times 3k \times \log_2 (4 \times 4) = 24kbit/s$
</div>

## 信道复用

1. 频分复用
1. 时分复用
1. 波分复用(光纤)
1. 码分复用: $\text{序列} \times \text{码片}$, $1$为$1$, $0$为无效, $-1$为$0$