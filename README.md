# 菜谱可视化

再明确一下各位小伙伴的分工：
* 我：数据获取，MDS后的显示页面
* 卢旺：如何度量两个菜谱的相似度，MDS对数据进行降维
* 蔡晨沁：country's view
* 白梅：global view

前两个页面的原型我已经建立好：大家访问 https://tonypod.github.io/recipeviz/ 这个链接就可以看到效果，另外，大家可以clone这个仓库，有什么改动pull request统一提交到这里吧

PPT是英文的，为便于理解，用中文描述一下前两个view是这样的：

1. Global view：由于我们的数据只支持15个国家，这15个国家在整张地图上稍微突出显示（区分世界其他国家）。右侧是查询窗口，查询条件有：包含某个ingredients（自动提示输入），限定cooking technique，限制flavor indices的范围（如spiciness在2和5之间），限制course（如soup, breakfast），限制各种营养素的含量（如热量、蛋白质含量）等等。<b>课上老师说用圆圈大小表示符合要求的菜谱数量看起来不太明显，因此还是用不同的颜色来表示比较好</b>

2. Country's view：在Global view中点击15个国家的其中一个跳转至Country's view，通过传入的GET请求的参数得知是哪一个国家，以一定的时间间隔（比如200毫秒）出现反映这个国家统计信息的bubble，每个bubble代表一个统计信息，bubble的大小为这个国家符合该属性的菜谱个数，bubble的颜色代表不同的属性（如基本信息，营养信息，ingredient信息）

3. Recipe similarity view：先设计一个距离度量来计算菜谱间的相似度（对于ingredients的相似度可以采用Jaccard Similarity），然后通过MDS进行降维，降维后的数据以散点图的形式显示在页面上

我们还有1个多月的时间，大家加油 ↖(^ω^)↗
