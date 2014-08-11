# Mesa: 全球备份, 近乎实时, 可拓展数据仓库

> 翻译自 [Mesa: Geo-Replicated, Near Real-Time, Scalable Data Warehousing](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/42851.pdf)

<div align="center">
Ashish Gupta, Fan Yang, Jason Govig, Adam Kirsch, Kelvin Chan, Kevin Lai, Shuo Wu, Sandeep Govind Dhoot, Abhilash Rajesh Kumar, Ankur Agiwal, Sanjay Bhansali, Mingsheng Hong, Jamie Cameron, Masood Siddiqi, David Jones, Jeff Shute, Andrey Gubarev, Shivakumar Venkataraman, Divyakant Agrawal
</div>

<div align="center">
Google, Inc.
</div>


## 介绍

Google在多个地域运行着一个可拓展的广告平台，它每天为全球的用户提供数十亿广告服务。与每个广告相关的详细信息，例如目标的标准、给人留下印象和点击的数量等等，都会实时记录并处理。这些数据广泛地用在Google不同的用例上，包括报告、内部审计，分析，计费和预测。广告要在推广效果上获得良好的效果，必须通过与复杂的前端服务交互来解决对底层数据的在线和按需查询。Google的内部广告服务平台使用实时数据来确定预算和之前已经上线的广告性能，用以提高现在和未来广告服务的相关性。作为Google广告平台就需要继续拓展，而作为内部和外部用户则要求对他们广告行为更大的可视化，对更多细节和细粒度信息的需求导致了原始数据大小的急速增长。可拓展性和数据的重要性导致了针对处理、存储和查询的技术和可操作性的独特挑战。对这种数据存储的需求如下：

原子性更新。一个单独的用户行为可能导致对相关数据的多次更新，影响着数千个一致性的视图，这些视图由一些指标集组成（如点击和花费）而且跨越一系列维度（例如广告商和国家）。它绝不可能在部分更新完成时就查询到系统的某个状态。

一致性和正确性。由于商业和法律的原因，这个系统必须返回一直而且正确的数据。我们要求强一致性并且是可重复的，即使这个请求跨越了多个数据中心。
 
可用性。这个系统必须没有单点故障。在预计和没有预计到的维护和失败下也没有停机时间，这包括整个数据中心或者整个地域停运的影响。

近乎实时的更新吞吐量。这个系统必须支持持续的更新，不管是新的行数据还是对现有行的增量更新，在一秒内数百万行数据的顺序上实现更新。这个更新操作在几分钟内对跨越不同视图和数据中心的一致性请求都必须是有效的。


可拓展性。这个系统必须能够随着数据量和请求数的增长而拓展。例如，它必须能够支持万亿行和PT级的数据。更新和查询的效率必须在这些数据增长得很大时维持住。

在线数据和元数据转换。为了支持新的特性和对现有数据粒度的改变，客户端通常要求改变数据Schema或者修改现有数据的值。这些改变必须不会影响到普通的查询和更新操作。

Mesa是Google对于这些技术性和可操作性难题的解决方案。即使这些需求的子集已经被现有的数据仓库解决了，Mesa是唯一同时为商业关键数据解决所有这些难题的。

Mesa是一个分布式、可备份并且高可用的结构化数据处理、存储和查询系统。Mesa处理由上层服务生成的数据，聚合然后持久化这些数据到内部，并且通过用户的查询提供数据的服务。即使这篇论文大部分都在讨论将Mesa应用在广告系统中，Mesa其实是一个通用的数据仓库解决方案，用以满足上述的所有需求。

Mesa综合了Google的基础架构和服务，例如Colossus（Google的下一代分布式文件系统）[22, 23]、BigTable[12]和MapReduce[19]。为了实现存储的可拓展性和可用性，数据水平分割



## 



[29] H. V. Jagadish, L. V. S. Lakshmanan, and D. Srivastava. Snakes and Sandwiches: Optimal Clustering Strategies for a Data Warehouse. In SIGMOD, pages 37–48, 1999.  
[47] A. Thusoo, Z. Shao, et al. Data Warehousing and Analytics Infrastructure at Facebook. In SIGMOD, pages 1013–1020, 2010.  