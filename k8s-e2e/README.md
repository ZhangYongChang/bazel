# Bazel

Bazel组织开发了面向k8s和docker相关的rule，这些rule能实现端到端的交付，直接将源码对应的服务发布到k8s集群。

主要有下面的优势：
1. 编译效率和正确性特别高，分布式构建
2. 构建过程抽象化，发明新语言和语法来实现，面向编程门槛比较高
3. Bazel组织开发相当多的语言插件，覆盖10多种常见的语言
4. Google内部开发都是采用Bazel来进行端到端的交付，直接从源码交付，能将时间每人的平均时间控制在秒级交付


xdot <(bazel query --notool_deps --noimplicit_deps "deps(//hellohttp/go:server)" --output graph)