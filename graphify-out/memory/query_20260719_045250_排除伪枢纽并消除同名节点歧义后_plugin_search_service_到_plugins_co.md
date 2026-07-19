---
type: "path_query"
date: "2026-07-19T04:52:50.833571+00:00"
question: "排除伪枢纽并消除同名节点歧义后，Plugin Search Service 到 Plugins Controller 的真实依赖是什么？"
contributor: "graphify"
source_nodes: ["Plugin Search Service", "package:kazumi/plugins/plugins_controller.dart", "PluginsController", "pluginsController", "Plugins Controller"]
---

# Q: 排除伪枢纽并消除同名节点歧义后，Plugin Search Service 到 Plugins Controller 的真实依赖是什么？

## Answer

真实关系是 Plugin Search Service 单向依赖 Plugins Controller。plugin_search_service.dart 以 EXTRACTED 1.0 导入 package:kazumi/plugins/plugins_controller.dart，同时以 EXTRACTED 1.0 引用无源码的规范化 PluginsController 类型，并定义 pluginsController 字段。plugins_controller.dart 以 EXTRACTED 1.0 定义实际 PluginsController 类。图谱未把规范化类型节点 pluginscontroller 与实际定义节点 plugins_plugins_controller_pluginscontroller 合并，因此自动最短路径无法形成完整的有向文件到类链；但 import、type reference 和 field definition 三项证据共同确认依赖方向为 Plugin Search Service 到 Plugins Controller。图中没有 calls 边，不能据此断言调用了具体方法。

## Source Nodes

- Plugin Search Service
- package:kazumi/plugins/plugins_controller.dart
- PluginsController
- pluginsController
- Plugins Controller