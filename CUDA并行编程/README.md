# CUDA并行编程

本目录是 infiniTensor summer camp 2026 中 CUDA 并行编程课程的发布包。

## 使用原则

- 每节课目录保留两个核心文件：`outline.html` 和 `slides.pptx`。
- `outline.html` 负责按 PPT 逐页讲清这一节课在完整课程中的位置、衔接、讲课内容、设计意图、可视化作用、讲课提示和容易误解的边界。
- `slides.pptx` 是课堂展示文件。
- `slide-previews/` 是 HTML 大纲引用的逐页 PPT 预览图，不是生成过程截图。
- 如某节课有必须随课使用的课堂互动资产，可以放在该 lesson 目录内，并在 README 与对应 `outline.html` 中说明使用页码和操作方式。当前例外是 Lesson 04 的 `show-float.html`。
- 原始材料、临时规划、审计记录、提示词和生成过程不放在 GitHub 发布目录中；这些内容保留在本地工作区的 `workflow/`、`cuda/` 和 `outputs/` 目录中。

## 课程结构

| 课程 | 目录 | PPT 页数 | 定位 |
| --- | --- | ---: | --- |
| Lesson 01 | `第一节课/` | 28 | 并行直觉、CPU/GPU 分工、CUDA 入口、AI 与并行动机 |
| Lesson 02 | `第二节课/` | 30 | Host/Device、最小 CUDA 程序、执行模型、编译与验证 |
| Lesson 03 | `第三节课/` | 40 | 从能跑到能判断瓶颈：byte、FLOP、bandwidth、AI、Roofline、NCU |
| Lesson 04 | `第四节课/` | 52 | 从 memory-bound 诊断到优化假设：float2/float4、alignment、float3、half/half2 |

## 互动演示

| 文件 | 使用位置 | 说明 |
| --- | --- | --- |
| `第四节课/show-float.html` | Lesson 04, slides 13, 16, 17, 28, 38 附近 | 选择 `float1/float2/float3/float4` 和地址偏移，点击“执行硬件读取”，观察 size、alignment、访问形态、`LDG.32/64/128` 示意，以及 Global Memory 到 Registers 的分量移动。该文件是教学演示，不是真实硬件时序模拟。 |

## 当前校验结论

原先课程已经完成了“四节基础课”的拆分和简化：

- Lesson 01 和 Lesson 02 来自 `cuda/lesson1` 的重组结果，目标是把原高密度 CUDA 入门内容拆成两节更适合本科/专升本学生接受的基础课。
- Lesson 03 和 Lesson 04 来自 `cuda/lesson2` 的重构结果，目标是把原“性能模型与逐元素优化”拆成“诊断课”和“行动课”。
- `cuda/lesson2/new_3/CUDA 性能模型导论.pptx` 是旧版 29 页材料；本发布目录采用 `outputs/lesson2-new3-new4-codex-ppt-rebuild/cuda-performance-model-new3/cuda-performance-model-new3.pptx` 的 40 页版本。
- `cuda/lesson2/new_3/Presentation3.pptx` 只有 3 页，应视为过程文件，不作为发布成品。

## 入口文件

- 课程总览：`index.html`
- Lesson 01：`第一节课/outline.html`
- Lesson 02：`第二节课/outline.html`
- Lesson 03：`第三节课/outline.html`
- Lesson 04：`第四节课/outline.html`
