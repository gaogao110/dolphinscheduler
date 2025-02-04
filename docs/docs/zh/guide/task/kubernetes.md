# Kubernetes

## 综述

kubernetes任务类型，用于在kubernetes上执行一个短时和批处理的任务。worker最终会通过使用kubernetes client提交任务。

## 创建任务

- 点击项目管理-项目名称-工作流定义，点击"创建工作流"按钮，进入DAG编辑页面。
- 工具栏中拖动 <img src="/img/tasks/icons/kubernetes.png" width="25"/> 到画板中，选择需要连接的数据源，即可完成创建。

## 任务参数

- 节点名称：设置任务的名称。一个工作流定义中的节点名称是唯一的。
- 运行标志：标识这个节点是否能正常调度,如果不需要执行，可以打开禁止执行开关。
- 描述：描述该节点的功能。
- 任务优先级：worker 线程数不足时，根据优先级从高到低依次执行，优先级一样时根据先进先出原则执行。
- Worker 分组：任务分配给 worker 组的机器执行，选择 Default 会随机选择一台 worker 机执行。
- 环境名称：配置运行任务的环境。
- 失败重试次数：任务失败重新提交的次数。
- 失败重试间隔：任务失败重新提交任务的时间间隔，以分为单位。
- 延迟执行时间：任务延迟执行的时间，以分为单位。
- 超时警告：勾选超时警告、超时失败，当任务超过“超时时长”后，会发送告警邮件并且任务执行失败。
- 命名空间：选择kubernetes集群上存在的命名空间
- 最小CPU：任务在kubernetes上运行所需的最小CPU
- 最小内存：任务在kubernetes上运行所需的最小内存
- 镜像：镜像地址
- 自定义参数：kubernetes任务局部的用户自定义参数,自定义参数最终会通过环境变量形式存在于容器中,提供给kubernetes任务使用
- 前置任务:在当前kubernetes任务之前需要执行的任务

## 任务样例

### 在 DolphinScheduler 中配置 kubernetes 集群环境

若生产环境中要是使用到 kubernetes 任务类型，则需要预先配置好所需的kubernetes集群环境

### 配置 kubernetes 任务节点

根据上述参数说明，配置所需的内容即可。

![kubernetes](/img/tasks/demo/kubernetes-task-en.png)

## 注意事项

任务名字限制在小写字母、数字和-这三种字符之中