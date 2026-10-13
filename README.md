# api-discovery-path-tree-local-clustering

本仓库为论文 **基于路径树局部聚类的API发现方法** 的配套材料。

> 受商业保密协议约束，**本文提出算法的核心实现代码暂不公开**。

## 方法简介
流量驱动API发现存在3个难点：动态参数与固定业务字段难以区分、结构相近接口容易混淆、全局聚类计算开销大。

基于路径树局部聚类的API发现方法：构建路径树完成HTTP请求层级划分；在叶节点局部区域构建属性相似图，执行相似度约束密度聚类得到语义请求簇；采用两级泛化机制：规则预泛化 + 依据簇内路径片段变化率二次泛化，生成API路径模板。

## 方法实现说明
本文路径树模块基于开源项目 **Drain3** 改造实现：
https://github.com/logpai/Drain3

局部密度聚类模块采用 **scikit-learn** 库内置的 DBSCAN 算法。
将预先计算得到的HTTP请求属性相似度矩阵输入DBSCAN；聚类仅在路径树每个叶节点的局部样本上执行，不对全部流量样本全局聚类，以此降低计算开销。

## 数据集
实验采用公开数据集 **ATRDF（API Traffic Research Dataset Framework）**
- 数据集官方地址：https://github.com/ArielCyber/Cisco_Ariel_Uni_API_security_challenge
- 论文实验处理方式：剔除CSS、JS、图片等静态资源请求，过滤格式异常残缺HTTP报文，丢弃全部恶意攻击流量；仅保留正常业务HTTP流量共108252条样本，保留原始完整URL路径，用于簇内路径片段变化率统计。

## 基线对比方法
论文对比3种流量驱动API发现基线，所有基线算法输入完全相同流量样本。

1. Speculator
开源仓库：https://github.com/openclarity/speculator

2. MRG
论文地址：https://arxiv.org/abs/2604.19471

3. HRAL
论文地址：https://arxiv.org/abs/2607.02442

## 引用
如果参考本仓库资料，请引用论文：
> todo
