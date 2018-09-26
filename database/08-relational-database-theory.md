---
# vi: ft=pandoc.markdown
---

# 关系型数据库设计理论

## 函数依赖

平凡函数依赖
: $(x, y) \rightarrow x$

完全函数依赖
: $X \xrightarrow{f} Y$

部分函数依赖
: $X \xrightarrow{r} Y$

传递函数依赖
: $X \xrightarrow{p} Y$

### 闭包推导

*补充? P184*

### 候选码推导

*补充? P185*

## 关系模式规范化

目的
: 在关系数据库中, 对关系模式的最低要求是满足第一范式。但满足最低要求的关系模式往往不能很好地描述现实世界, 可能会存在插入异常、删除异常、修改复杂以及数据冗余等问题, 需要寻求解决这些问题的方法

基本思想
: 逐步消除数据依赖中不合适的部分, 使各关系模式达到某种程度的\`分离'.

实现
: 通过模式分解把一个低级别范式的关系模式逐步转换为若干个高级别范式的关系模式集合来完成的

实质
: 概念的单一化。

1. 1NF
1. 2NF
1. 3NF
1. BCNF

## 关系模式分解

二者独立

1. 无损连接性: 保证信息不丢失

    $U_1 \cap U_2 \rightarrow U_1 - U_2 \in F^+ or U_1 \cap U_2 \rightarrow U_2 - U_1 \in F^+$

1. 保持函数依赖: 在减轻或解决数据冗余和各种操作异常情况的同时, 保证分解后的关系模式保留了原关系模式的所有语义

    $F^{+} = G^{+}$