测试了下在纵向recyclerView中嵌套一个横向RecyclerView的场景。
1.原始情况：屏幕显示6个Grid布局的RecyclerView,每个GridView里有12*2个TextView。(使用实际业务的页面，布局实际上比Litho使用的略复杂)
2.litho:屏幕显示12个Linear横向布局RecyclerView,每个RV里有23个TextView。
感官上的结果：
### litho
1. 丝滑般流畅
2. 打开时生成顶部第一个列表，等待大概0.2秒左右显示完屏幕剩下所有列表
3. 打开页面速度略微快于原始情况(可能也是受到一定界面复杂度影响)
### 原始
1. 异常卡顿
2. 界面整体生成，没有出现单独先生成一个列表的情况。
