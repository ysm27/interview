vue 组件可能存在多个实例，如果使用对象形式定义 data，则会导致它们共用一个 data 对象，那么状态变更将会影响所有组件实例，这是不合理的。

采用函数形式定义，在 initData 时，会将其作为工厂函数返回全新 data 对象，让各个组件维护各自的数据，有效规避多实例之间状态污染问题。

而 vue 根实例创建过程中不存在该限制，是因为根实例只能有一个，所以不需要担心这种情况。

