### margin collapse

块的顶部和底部边距有时会组合（折叠）为单个边距，其大小是各个边距中最大的（或者只是其中一个，如果它们相等），这种行为称为边距折叠。请注意，浮动和绝对定位元素的边距永远不会折叠。
详见 `demo2.html`。

`margin collapse` 出现的场景：

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing

1.Adjacent siblings

相邻同级的边距会重叠（除非后一个需要清除浮动）

2.No content separating parent and descendants

没有内容区分父母和后代

如果没有创建 border, padding, inline part, bfc 或将块的 margin-top 与其一个或多个后代块的 margin-top 顶部分开的间隙；

或者没有 border, padding, inline content, height, or min-height 来将块的 margin-bottom 与其一个或多个后代块的 margin-bottom 分开，然后这些边距会折叠。 collapse margin 最终位于父级之外。

3.Empty blocks

如果没有 border, padding, inline content, height, or min-height 来将块的 margin-bottom 和 margin-bottom 分类，则它的 top and bottom margins collapse.

注意事项：
当涉及到负边距时，折叠边距的大小是最大正边距和最小（最负）负边距之和。
当所有边距均为负值时，折叠边距的大小是最小（负值最大）的边距。这适用于相邻元素和嵌套元素。
折叠边距仅与垂直方向相关。
display 设置为 flex 或 的容器中的边距不会折叠 grid。
