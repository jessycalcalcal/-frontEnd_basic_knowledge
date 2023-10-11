normal flow
containing block

### postion 属性值

5 种：
absolute
relative
static
fixed
sticky

### containing block 包含块

元素的大小和位置通常受其 `containg block` 的影响。大多数情况，containg block 是元素最近的 block 元素的 `content area`，但情况并非总是如此：详见 `demo1.html`。

根据例子可知，

#### 识别 containg block --- 取决于元素的 position 属性

1. 如果 position 属性为 static（默认值）、relative 或 sticky，则 `containg block` 由最近 `block`（inline-block, block, or list-item element） 或 `能建立格式化上下文`（table container, flex container, grid container, or the block container itself）的祖先元素的 content box edge 形成。

2. 如果 position 属性为 absolute，则 `containg block` 由最近的`非static` (fixed, absolute, relative, or sticky) 祖先元素的 padding edge 形成。

3. 如果 position 属性为 fixed，则 `containg block` 由`视口`（在连续媒体的情况下）或`页面区域`（在分页媒体的情况下）建立。

4. 如果 position 属性是 absolute 或 fixed，则 `containg block` 也可以由具有以下属性的最近祖先元素的 padding edge 形成：

- transform 或 perspective: 非 none 值
- will-change 值为: transform 或 perspective
- filter 值非 none 或 will-change 的值 filter（仅适用于 Firefox）
- contain 值为: layout、paint、strict、content
- container-type: 值非 normal
- backdrop-filter: 值非 none，如 backdrop-filter: blur(10px);

#### 识别 根据 containg block 计算元素的百分比

元素的属性值为百分比时，计算值依赖于 `containg block`
height top bottom 依赖于` containg block` 的 height
width left right padding margin 依赖于` containg block` 的 width
