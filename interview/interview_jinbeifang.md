## 1.vue生命周期

**beforecreate :**

实例初始化之后，数据观测 (data observer) 和 event/watcher 事件配置之前被调用。

**created:**

在实例创建完成后被立即调用。在这一步，实例已完成以下的配置：数据观测 (data observer)，property 和方法的运算，watch/event 事件回调。然而，挂载阶段还没开始，`$el` property 目前尚不可用。

**beforeMount:** 

在挂载开始之前被调用：相关的 `render` 函数首次被调用。**该钩子在服务器端渲染期间不被调用。****

**mounted:**

实例被挂载后调用，这时 `el` 被新创建的 `vm.$el` 替换了。如果根实例挂载到了一个文档内的元素上，当 `mounted` 被调用时 `vm.$el` 也在文档内。

**beforeupdate:**

数据更新时调用，发生在虚拟 DOM 打补丁之前。这里适合在更新之前访问现有的 DOM，比如手动移除已添加的事件监听器。

**该钩子在服务器端渲染期间不被调用，因为只有初次渲染会在服务端进行。**

**updated**:

由于数据更改导致的虚拟 DOM 重新渲染和打补丁，在这之后会调用该钩子。**该钩子在服务器端渲染期间不被调用。**

**activated**:

被 keep-alive 缓存的组件激活时调用。

**该钩子在服务器端渲染期间不被调用。**

**deactivated**

被 keep-alive 缓存的组件停用时调用。`

**该钩子在服务器端渲染期间不被调用。**:

**beforedetroy**:

实例销毁之前调用。在这一步，实例仍然完全可用。

**该钩子在服务器端渲染期间不被调用。**

**detroyed:**

实例销毁后调用。该钩子被调用后，对应 Vue 实例的所有指令都被解绑，所有的事件监听器被移除，所有的子实例也都被销毁。

**该钩子在服务器端渲染期间不被调用。**

**errorCaputred**:

当捕获一个来自子孙组件的错误时被调用。此钩子会收到三个参数：错误对象、发生错误的组件实例以及一个包含错误来源信息的字符串。此钩子可以返回 `false` 以阻止该错误继续向上传播。

