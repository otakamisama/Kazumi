---
type: "path_query"
date: "2026-07-19T04:44:13.692541+00:00"
question: "排除 map、_、t、_state 等伪枢纽后，Plugin Search Service 到 Player Item 的真实最短路径是什么？"
contributor: "graphify"
source_nodes: ["Plugin Search Service", "package:kazumi/services/logging/logger.dart", "Player Item"]
---

# Q: 排除 map、_、t、_state 等伪枢纽后，Plugin Search Service 到 Player Item 的真实最短路径是什么？

## Answer

精确节点 plugin_plugin_search_service 与 player_player_item 在无向图中的最短路径是 2 跳：plugin_search_service.dart --imports--> package:kazumi/services/logging/logger.dart <--imports-- player_item.dart。两条边均为 EXTRACTED、confidence_score 1.0，但 source_location 为空。按原始边方向重建有向图后，从 Plugin Search Service 到 Player Item 不可达，反向也不可达；两者唯一的共同出边是 logger。因此这不是业务调用链，而是两个模块共同依赖日志基础设施。

## Source Nodes

- Plugin Search Service
- package:kazumi/services/logging/logger.dart
- Player Item