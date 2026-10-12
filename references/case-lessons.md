# 可迁移案例模式 / Transferable case patterns

以下是从恢复实践提炼的匿名方法模式，不是附带原始回执的项目审计报告。未分发任何游戏代码、资产、聊天记录或运行捕获。案例说明不证明当前目标的行为或恢复质量；实际结论必须回到当前项目证据。

These anonymized patterns explain recovery decisions. They are not project audit reports or acceptance receipts. No game source, assets, conversations, or runtime captures are included. Validate every claim against the current target.

## A：渲染纠偏 / Rendering corrections

| 缺口 / Gap | 恢复与验证 / Recovery and validation |
|---|---|
| 原包使用 Linear，导出工程继承 Gamma / Color-space mismatch | 核对原包设置，只改变相关变量并做同条件差分；不调曝光补偿 / Verify original settings and isolate the change |
| Shader 属性 HDR/Gamma 标记丢失 / Missing property metadata | 恢复声明与上传语义；公式和材质数值相同仍可能失真 / Restore metadata and upload semantics |
| Sprite mesh、UV、packed padding 丢失 / Lost sprite geometry | 核对原序列化与实际 UI 采样；PNG 一致只证明图像文件 / Verify geometry and sampling, not only PNG bytes |
| 矩阵声明错误或重复 Y 翻转 / Matrix or platform conversion errors | GPU 读回并核对最终产物程序；编译通过不证明输出 / Check GPU output and the shipped program |
| 导入自动生成默认渲染配置 / Generated default pipeline settings | 追踪实际绑定，核对原配置；不照搬另一个项目管线 / Trace bindings and preserve target-specific settings |

## B：资源保留但消费者缺失 / Assets retained, consumers missing

| 缺口 / Gap | 恢复与验证 / Recovery and validation |
|---|---|
| 参数已保留但 Shader 未消费 / Unused material parameters | 沿活跃 Renderer 到最终程序恢复公式、空间与条件；引用数不等于同帧绘制数 / Trace active rendering paths |
| 动态阴影资源存在但写入链为空 / Missing dynamic texture writer | 恢复创建、渲染、blit、绑定和释放；静态存在不证明执行 / Restore the full texture lifecycle |
| 缩放到相似名字的错误根节点 / Wrong transform receiver | 核对字段偏移、父子关系和坐标空间 / Verify receiver identity and transform space |
| 调试入口登记齐全，正式 Init 漏接 / Debug-only initialization | 将有证据的接线接回原启动链，不把调试 bootstrap 当正式入口 / Validate the original startup path |
| 后一次 OnComplete 覆盖前一次，却被还原为追加 / Callback replacement changed to append | 恢复最后有效副作用与生命周期 / Preserve effective callback semantics |
| 胜负已检测但结算 UI 为空 / Win detection without result UI | 恢复弹窗、奖励、重试和存档消费者；排除 SDK 不等于排除业务回调 / Restore downstream business behavior |
| Conditional 使日志未编入包 / Logs removed at compilation | 核验诊断输出链后解释日志缺失 / Verify instrumentation before interpreting silence |

## C：局部方法通过不等于全链闭合 / Local success is not full integration

| 观察 / Observation | 判断 / Decision |
|---|---|
| 顶点颜色已恢复但实际绑定恒白 Shader / Correct color data, placeholder shader | 检查最终消费者；数据存在不能证明视觉 / Verify the final consumer |
| 历史覆盖报告与当前源码不同 / Stale coverage report | 按版本、范围和替代关系复核；方法计数不是语义完成率 / Reconcile versions and claim boundaries |
| 独立 policy 与原类内转写并存 / Candidate policy and inlined implementation | 核对契约、适配与调用方；不要求文件或类名相同 / Trace contracts and adapters |
| 对象清理通过但动画事件桥为空 / Cleanup without animation events | 单独恢复状态、Animator、事件与特效消费者 / Validate each lifecycle consumer |
| 暂无同条件原包画面 / No matched original capture | 保留视觉未知，继续独立静态恢复 / Keep visual claims unknown and continue independent work |

文件、类型、可编译实现、可执行语义、限定运行证据和最终等价性是不同层。迁移的是验证方法，不是其他项目的参数、覆盖率或结论。

Files, types, compilation, executable semantics, scoped runtime evidence, and final equivalence are separate layers. Transfer the method, not another project's settings or conclusions.
