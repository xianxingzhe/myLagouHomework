# myLagouHomework
my homework about lagou course

### 选择题
1、ABCD  2、D
### 简答题
patchVnode 函数主要作用是对比新旧节点，更新差异。
patchaVnode的工作流程首先是在真正对比节点前先触发 prepatch和update钩子函数，
1、如果新旧节点的引用一直，则表示没有变化
2、如果新旧两个都有text文本且不相等，先移除纠节点的children(如果有的话)，设置dom元素的textContent为新节点的文本  
3、如果新老节点都有children且不相等那就调用updateChildren更新节点的差异
4、如果只有新节点有children,那么先清除老节点的textContent(如果老节点有text属性)，然后添加新节点的所有children
5、如果只有老节点有children属性，移除所有老节点  
6、如果只有老节点有text，清空对应dom元素的textContent  
最后触发用户设置的postpatch钩子函数
