# DIKWP‑Mesh 4.1 世界AI证据网格（WorldAI Evidence Grid）

版本：`v1.0.0`  
系统 ID：`dikwp-mesh-4.1-worldai-evidence-grid`  
运行方式：离线优先、Python 标准库、SQLite、原生 JavaScript  
默认地址：`http://127.0.0.1:8810`

## 1. 系统定位

本项目面向段玉聪公开 GitHub 项目组合中已经形成的语义运行时、意图/目的控制、信任与互操作、证据分级、复现挑战、标准化、生态路由、人工意识及行业场景等关系链，补充一个横向关键基础设施：

> 把分散项目、模型输出、实验协议、治理材料和跨地区复现结果，组织为可直接运行、可追溯、可比较、可挑战、可脱敏交换且不自动继承外部权威的证据网格。

项目不为“AI”“智能”“意识”“世界模型”“可信”等外部概念建立模型自定的普遍定义。运行对象始终保留表达、来源、观察者、时间、范围、意图来源、权限、数据驻留、关系边、证据状态和残差。

## 2. 直接运行

要求 Python 3.10 或更高版本。核心运行不需要安装第三方 Python 包，不调用外部服务。

```bash
python run.py serve
```

浏览器打开：

```text
http://127.0.0.1:8810
```

演示账户密码统一为：

```text
mesh41-demo
```

账户与工作流角色：

| 用户名 | 工作流角色 |
|---|---|
| `admin` | 系统管理员 |
| `designer` | 实验设计角色 |
| `evaluator` | 评测角色 |
| `replicator` | 独立复现角色 |
| `policy` | 政策映射角色 |
| `node` | 联邦节点运行角色 |
| `auditor` | 审计角色 |
| `observer` | 公共观察角色 |

这些账户只用于本地演示，不代表真实身份、机构授权、数字签名或公共权力。

### CLI 示例

```bash
python run.py init
python run.py list-capsules
python run.py run --capsule caps_public_service_bilingual --adapter mock
python run.py summary
python run.py verify-audit
python run.py qa
```

指定独立数据库：

```bash
python run.py --db /absolute/path/waeg.sqlite3 serve --host 127.0.0.1 --port 8810
```

Docker：

```bash
docker compose up --build
```

## 3. 已交付能力

### 3.1 GitHub 项目关系谱系

系统内置一个观察时点为 2026-07-21 的策展快照：GitHub 账户页面当时显示 220 个公开仓库；本项目保存 129 个代表性项目记录，组织为 12 个多标签工程关系簇。该快照不是完整镜像、流行度排名或成熟度认证。

关系簇包括：

- semantic_runtime
- assurance_governance
- evidence_replication
- standards_ecosystem
- consciousness_experience
- civilization_public_goods
- foresight_strategy
- human_agency_economy
- domain_health
- domain_transport
- domain_finance_legal
- domain_education_culture

每条记录保存仓库句柄、来源状态、公开能力陈述或分析映射、接入槽位、观察时间和证据边界。

### 3.2 可复现实验胶囊

实验胶囊封装：

```text
目的及其来源状态
权限、适用法域与数据驻留
带哈希、来源、许可证和敏感级别的输入
任务、语言、必须保留的锚点和预期证据引用
DIKWP 关系通道
重复运行参数
中国与全球治理映射档案
联网、工具执行、停止与恢复边界
```

内置 6 个可运行胶囊：

1. 双语公共服务信息表达；
2. 智能体工具越权和提示注入边界；
3. 开放主张独立复现；
4. 跨模型目的保持比较；
5. 具身智能合成安全场景；
6. 低资源、主权驻留节点场景。

### 3.3 多模型适配器

- `mock`：确定性合成适配器，默认离线，用于复现实验和安全边界测试；
- `replay`：重放胶囊中保存的结构化输出；
- `openai_compatible`：可选 OpenAI-compatible HTTP 端点；
- `ollama`：可选本地 Ollama 端点。

网络适配器同时要求：

```text
操作者显式打开 allow_network
＋胶囊 safety.network_allowed=true
＋端点主机位于 localhost 或 WAEG_ALLOWED_HOSTS
```

适配器只记录模型请求的工具调用，不执行任何工具。

### 3.4 非标量证据状态

每次运行分别保存：

```text
Gate：ALLOW / REVIEW / HOLD / BLOCK / KILL
Semantic Stability：S4 / S3 / S2 / S1 / S0
Mesh Examination：M4 / M3 / M2 / M1 / M0
Evidence Reliability：Solid / Supported / Provisional / Borrowed / Hollow / Contested / Blocked
```

没有来源明确的权重规则时，不将这些异质状态压缩为单一总分。

### 3.5 DIKWP×DIKWP 关系网

系统开放 25 个有向关系地址，但只激活当前运行实际出现的关系：

```text
D→D … D→P
I→D … I→P
K→D … K→P
W→D … W→P
P→D … P→P
```

每条边保存来源状态、观察者、语境、时间和 provenance。系统检查端点、通道、P→D→I→K→W→P 闭合路径和有向循环，不机械填满 25 个单元。

### 3.6 意图条件化问题核

运行结束后，对布尔证据事实逐项执行删除反事实测试：

```text
当前闭合签名
→ 删除一个已观察事实
→ 重新推导 Gate、语义稳定性和标准映射状态
→ 检查闭合是否变化
→ 投影到相关节点和关系边
```

输出只表示当前胶囊、运行、观察者、来源和本地规则下的关键依赖，不宣称任何概念的普遍本质。

### 3.7 中国与全球治理映射

内置 6 个来源限定的工程材料映射档案：

- 中国《人工智能 智能体互联》系列标准；
- 中国“人工智能+”全球合作方向；
- 中国人工智能全球治理行动计划；
- NIST AI RMF / Generative AI Profile；
- EU GPAI Code / AI Act；
- UN Global Dialogue on AI Governance。

映射只把运行事实标记为 `observed / partial / missing`，不生成合规、认证、法律意见或机构认可结论。

### 3.8 独立复现与反证

系统可对具体 `run_id + claim_id` 建立挑战记录，保存复现协议、创建者、状态和结论。支持的状态为：

```text
open / supported / refuted / inconclusive / withdrawn
```

挑战状态附着于具体主张，不扩展为对整个仓库、作者或理论体系的总括评价。

### 3.9 主权节点和证据交换

节点护照保存：

```text
节点标识
运行主体
法域
语言
数据驻留
能力
信任状态
证明模式
来源状态
```

证据包导出时：

- 原始输入内容一律不导出；
- 输入含 restricted/secret 时，模型输出也被隐藏；
- 保存运行清单、哈希、检查、关系网、问题核和证据项；
- 使用 HMAC-SHA256 形成演示完整性记录；
- 导入证据始终标记为外部、非本地权威。

HMAC 只证明持有配置的共享密钥，不等价于公钥身份、不可否认性或机构电子签名。生产环境应替换为机构密钥管理、证书和公钥签名。

### 3.10 审计与并发控制

- SQLite WAL；
- 胶囊乐观修订号；
- 每次登录、写入、运行、导出和导入形成 SHA-256 链式审计事件；
- `python run.py verify-audit` 可重新计算完整审计链。

## 4. 浏览器工作台

工作台包含 10 个区域：

```text
组合运行总览
GitHub 项目谱系
实验胶囊
运行证据
跨模型/跨运行差异
标准/治理映射
主权节点与证据交换
独立复现与反证
DIKWP×DIKWP 关系网
审计与完整性
```

## 5. 工程结构

```text
waeg/                       Python 服务与运行内核
web/                        原生 JavaScript 工作台
data/portfolio_snapshot.json  GitHub 项目策展快照
data/capsules/              可运行实验胶囊
data/crosswalk_profiles/    来源限定治理映射
data/nodes/                 节点护照
tests/                      单元、API、HTTP、边界和发行 QA
schemas/                    JSON Schema 2020-12
examples/                   运行与联邦证据示例
docs/                       分析、架构、治理和运维文档
openapi.yaml                OpenAPI 3.1 契约
```

## 6. 安全与事实边界

本项目是可运行的研究和工程原型，不是：

- 对段玉聪全部 220 个仓库的逐行代码审计；
- 对任何 GitHub 项目成熟度、安全性、学术正确性或商业价值的认证；
- 国家、国际组织、标准组织或监管机构认可的测试平台；
- 真实公钥联邦身份基础设施；
- 可执行外部工具、物理设备或高影响决策的自治代理；
- 对模型“智能”“意识”“可信”或“安全”的普遍定义与证明；
- 现实场景有效性、法律合规或跨国数据传输许可的替代品。

## 7. 详细文档

- `docs/00_portfolio_deep_analysis_zh.md`
- `docs/01_intent_conditioned_gap_kernel.md`
- `docs/02_system_architecture.md`
- `docs/03_china_global_crosswalk.md`
- `docs/04_dikwp_portfolio_integration_map.md`
- `docs/05_security_sovereignty_boundaries.md`
- `docs/06_api_and_capsule_spec.md`
- `docs/07_deployment_and_operations.md`
- `docs/08_sources.md`
- `docs/09_acceptance_matrix.md`


## 8. 自动化验证

发行候选在当前构建环境完成 **484/484 项工程检查**：

| 验证类别 | 结果 |
|---|---:|
| Python/JavaScript/浏览器结构静态检查 | 37/37 |
| JSON 语法 | 27/27 |
| JSON Schema 与实例 | 23/23 |
| OpenAPI 3.1 | 11/11 |
| 129 个项目记录完整性 | 129/129 |
| 项目谱系总体不变量 | 17/17 |
| 胶囊、节点、crosswalk 完整性 | 66/66 |
| 单元与 API 测试 | 29/29 |
| 六胶囊运行、关系网、语义和状态验证 | 77/77 |
| 比较、挑战、修订、联邦、审计与重启 | 24/24 |
| 生成物 Schema、角色、部署、安全、示例与清洁性 | 44/44 |
| **合计** | **484/484** |

详细逐项报告：`outputs/qa_summary.json`。该 QA 只证明本发行包的工程行为和内部不变量，不证明外部事实、法律合规、现场有效性、公共权威、模型意识或普遍安全。

## 9. 许可证

项目代码采用 Apache License 2.0。数据目录中的第三方来源记录只保存元数据、短摘要和来源链接；相关第三方项目仍受其各自许可证和权利边界约束。
