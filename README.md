# Alpha Lab · Investment Graph Viz Lab

7 种可视化风格实现同一个投资研究知识图谱, 探索"哪种图形最适合展示公司间关系".

数据源: [Alpha Lab](https://alpha-lab.work) 的 `/api/v1/facts` + `/api/v1/kg/graph`

## 目录

| 文件夹 | 库 | 特点 |
|---|---|---|
| `investment-graph-index.html` | — | 门户 landing page, 索引 7 种实现 |
| `investment-graph-visnetwork/` | [vis-network 9.1](https://visjs.github.io/vis-network/) | ⭐ 主力方案. Physics 力导向 + Live 市值 + KG 关系 (55 家 · 60 边) |
| `investment-graph-cytoscape/` | [cytoscape.js](https://js.cytoscape.org/) | 生物信息学系, 更学术风 |
| `investment-graph-d3-pack/` | [d3.js](https://d3js.org/) | 圆嵌套 (pack layout), 展示层级 |
| `investment-graph-antv-g6/` | [AntV G6](https://g6.antv.antgroup.com/) | 蚂蚁金服系, 商业风格 |
| `investment-graph-reactflow/` | [React Flow](https://reactflow.dev/) | React 组件, 可编辑 |
| `investment-graph-sigma/` | [Sigma.js](https://www.sigmajs.org/) | WebGL, 大规模节点渲染快 |
| `investment-graph-poc/` | 手写 canvas | PoC 阶段 |

## 特点

**vis-network 版**:
- 55 家公司节点 (registry from alpha-lab)
- 60 条 KG 关系边 (18 SEC 10-K 验证 + 42 KOL 提及)
- 节点大小 = log(市值 USD), 每天从 yfinance 更新
- 边样式区分数据源: 粗实线 = SEC 验证, 细虚线 = KOL 说
- 边颜色区分关系: 🟢 供货 / 🔵 客户 / 🟠 依赖 / 🟡 投资 / 🟣 竞争
- Hover 显示 evidence 原文引用

## 使用

直接双击任何一个 `index.html` 即可, 无需 build. 依赖库从 CDN 加载.

后端 API `https://api.alpha-lab.work/api/v1/` 是公开的.
