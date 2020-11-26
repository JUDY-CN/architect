# 组件图 (Component Diagram)

组件图又称构建图，用于显示系统各组件及各组件关系的物理视图。

## 状态图组成元素

| 组成元素         | 说明                                                         | 符号                                 |
| ---------------- | ------------------------------------------------------------ | ------------------------------------ |
| 组件 (Component) | 系统的模块化部分                                             | 用左侧带有突出两个小矩形的矩形来表示 |
| 接口 (Interface) | 由一组操作组成，它指定了一个契约，这个契约必须由实现和使用这个接口的构件所遵循 | 用实心圆来表示                       |
| 端口（Port）     | 属于外部接口，是被封装组件与外界的交互点。实现接口的组件使用端口来收发消息，与外界交互 | 用小矩形框来表示                     |
