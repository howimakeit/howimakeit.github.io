---
layout: post-page
title:  "RFM分析"
date:   2026-03-16
categories: 
excerpt: "“RFM分析用于用户识别和用户相关价值体系的构建”"
image: "/assets/images/road/RFM分析/04.jpg"
---

<h1 style='text-align:center;'>RFM分析（用户价值识别）</h1>

---

<h2 style='text-align:center;'>一、模型介绍</h2>

<p>RFM模型（高价值用户分层，R—时间内，F—频率，M—金额总数），用来确定用户价值，具体还可以多次细分，例如高R低FM，高RF低M，一共可以有10种类别划分。具体就是打分机制，简化的模型可能没有打分机制，但是一般都是用打分机制判断，标准如下表所示，一般还会计算用户三个指标的均值用于判断是高还是低，标准可以自己拟定。这次数据集中没有金额大小，就按照是否购买计算，也就是只有0和1两个选项。</p>

<img src = '/assets/images/road/RFM分析/01.png'>

<h2 style='text-align:center;'>二、数据来源</h2>

<p style = 'text-align:center;'>https://www.kaggle.com/datasets/yijiajia/taobao-userbehavior</p>

<h2 style='text-align:center;'>三、代码（SQL、python、pycharm上的SQL）</h2>

<img src = '/assets/images/road/RFM分析/02.png'>

<p>（先是WITH AS的CTE查询提取出有共同特征的所有用户，之后是RFM的判定以及代码。这里还有用INDEX引索加快搜索，R - SUM F - SUM CASE WHEN THEN M - COUNT）</p>

<img src = '/assets/images/road/RFM分析/03.png'>

<p>（python的代码，引入了pandas库，代码便于维护，但是非专业人员不好修改，有一定门槛）</p>

<img src = '/assets/images/road/RFM分析/04.png'>

<p>（以上个人认为是最优解，运行不会调用到SQL的C++底层，运行速度很快，唯一的缺点就是不容易调试）</p>

<h2 style='text-align:center;'>末</h2>

<p>需要注意的是，RFM分析并不局限于R、F、M三个指标，若是对目标的描述要更加精确，各个因素权重不一样的时候，可以引入其它指标构建体系，RFM只是提供一个大概方向和思路：频率，金额，最近消费。</p>