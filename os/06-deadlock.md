# 死锁

## 概念

### 资源

资源就是在任何时候都**只能被一个进程使用**的任何对象

可剥夺资源: 可以从拥有它的进程中剥夺而不会产生任何副作用 (存储器)

不可剥夺资源: (刻录机)

### 死锁

如果在一个进程集合中的每个进程都在等待只能由该集合中的另一个进程引发的事件，该组进程就被死锁

### 产生条件

* 互斥
* 占有和等待: 已占有某些资源的进程可以请求新的资源
* 非剥夺条件
* 循环等待条件: ~~至少有2个或以上进程构成循环链, 每个进程都在等待由循环链中下一个成员占有的资源~~

#### 死锁建模

\tikz{
    \node[circle, draw] (p) at (0,0) {P};
    \node[rectangle, draw] (r) at (2,0) {R};
    \draw[->] (r) -- (p);
}:\  
aa

## 鸵鸟算法

即视而不见

*理由:*

* 死锁极少发生
* 预防死锁的代价太高

UNIX和Windows采用这方法,
这是方便性与正确性的平衡

## 死锁检测和恢复

* 允许死锁发生
* 尝试检测并恢复

### 单资源类型的死锁检测

每种资源只可分配一次, ~~每种类型只存在一个资源~~

构造资源图, 检测环路

### 多资源类型的死锁检测

每种资源只可分配多次, ~~每种类型存在多个资源~~

### 从死锁中恢复

* 剥夺法恢复, 很可能需要人工干预, 取决于资源类型
* 回退法恢复, 需要保存资源映像和资源状态
* 杀死进程法, 环路内环路外, 最好从头再运行没有副作用

## 死锁避免

<!--
    vi: ft=pandoc.markdown
-->