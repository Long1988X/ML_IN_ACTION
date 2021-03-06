[toc]

### 决策树

#### 1. 简介

**决策树是什么？**

> 决策树(decision tree)是一种基本的==<u>分类</u>与<u>回归</u>==法。
>
> 分类决策树模型是一种描述对实例进行分类的树形结构。

**举个例子**

![decision_tree](/home/sdlg/ML_IN_ACTION/Notes/decision_tree.png)

>如上图所示的流程图就是一个决策树，长方形代表判断模块(decision block)，椭圆形成代表终止模块(terminating  block)，表示已经得出结论，可以终止运行。从判断模块引出的左右箭头称作为分支(branch)，它可以达到另一个判断模块或者终止模块。

> 决策树由结点(node)和有向边(directed edge)组成。结点有两种类型：内部结点(internal node)和叶结点(leaf node)。内部结点表示一个==特征或属性==，叶结点表示一个==类==。

**理解**

> 将决策树转换成==if-then规则==的过程是这样的：由决策树的根结点(root node)到叶结点(leaf node)的每一条路径==构建一条规则==；路径上内部结点的特征对应着==规则的条件==，而叶结点的类对应着==规则的结论==。

#### 2. 过程

* 收集数据：使用任何方法，获取需要的数据；
* 准备数据：按照一定规则整理数据，并排版，方便后续处理；
* 分析数据：是否符合预期；
* 训练算法：构造决策树，或者决策树学习，就是==构造一个决策树的数据结构==；
* 测试算法：计算错误率，错误率达到可接收范围，决策树就可以投入使用了；
* 使用算法：适用任何监督学习算法；而使用决策树可以==更好的理解数据的内在含义==；

#### 3. 构造决策树

**准备工作**

> * 收集数据不充分：导致没有足够的特征让我们构建错误率低的决策树；
> * 特征充足，但不知道用哪些特征：导致无法构建出分类效果好的决策树模型；

**构建步骤**

> 特征选择、决策树的生成和决策树的修剪；

##### 3.1 特征选择

* 特征选择在于：选取对==训练数据====具有分类能力==的特征；
* 特征选择就是：决定用哪些特征来划分==特征空间==；
* 选择特征的标准：信息增益（information gain)