---
type: "query"
date: "2026-07-19T05:39:32.149820+00:00"
question: "PluginSearchService 实际读取或调用了 PluginsController 的哪些字段和方法？"
contributor: "graphify"
source_nodes: ["PluginSearchService", "pluginsController", "querySource", "queryAllSource", "_queryPlugin", "PluginsController"]
---

# Q: PluginSearchService 实际读取或调用了 PluginsController 的哪些字段和方法？

## Answer

当前图谱无法确定具体成员使用。plugin_search_service.dart 对外共有 7 条 imports、4 条 references、11 条 defines，但 calls 边为 0。与 PluginsController 相关的跨节点边只有两条文件级关系：导入 package:kazumi/plugins/plugins_controller.dart，以及引用无源码的规范化 PluginsController 类型，均为 EXTRACTED 1.0 且没有 source_location。PluginSearchService、pluginsController、querySource、queryAllSource、_queryPlugin、_handleSearchError、cancel 等 11 个成员节点的出边全部为 0，只有文件 defines 它们的入边。因此图谱能确认服务持有控制器依赖，却不能确认读取了 pluginList、pluginHTTPList 或调用了任何具体方法；需要源码级只读核对。

## Source Nodes

- PluginSearchService
- pluginsController
- querySource
- queryAllSource
- _queryPlugin
- PluginsController