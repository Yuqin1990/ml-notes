2.4 Understanding exponentially weighted averages
Advantage: Takes very little memory, keep overwriting v by taking the formula 
![](/assets/Screen Shot 2018-03-07 at 11.43.08 PM.png)
![](/assets/Screen Shot 2018-03-08 at 12.04.35 AM.png)

2.5 Bias correction in exponentially weighted average
Bias correction 
紫色曲线开始的时候相对较低一些。这是因为开始时我们设置，所以初始值会相对小一些，直到后面受前面的影响渐渐变小，趋于正常。

修正这种问题的方法是进行偏移校正（bias correction
在刚开始的时候，t比较小，，这样就将修正得更大一些，效果是把紫色曲线开始部分向上提升一些，与绿色曲线接近重合。随着t增大，，基本不变，紫色曲线与绿色曲线依然重合。这样就实现了简单的偏移校正，得到我们希望的绿色曲线。

但是偏移校正并不总是必须的。因为，在一次次迭代后，受初始值影响越来越小，紫色曲线与绿色曲线基本重合。所以，在经过一段初始迭代过程后，再取值就不需要进行偏移校正了。
![](/assets/Screen Shot 2018-03-08 at 12.16.45 AM.png)