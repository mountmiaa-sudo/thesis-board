# thesis-board

毕业论文进度看板：一个无构建步骤的静态页面，手机可直接访问、也可直接编辑。

站点：<https://mountmiaa-sudo.github.io/thesis-board/>

- `index.html` — 单文件页面，内联 CSS/JS，无外部依赖
- `progress.json` — 唯一数据源（待办、里程碑、五阶段状态、更新日志）

## 两条更新路径

**手机端**：点页面右上角「编辑」，勾选待办、拖阶段进度、加日志，保存后经 GitHub Contents API 直接提交回本仓库。首次使用需粘贴一个细粒度 token（仅授权本仓库 Contents 读写），token 只存在该设备浏览器的 localStorage 里，不会进入仓库。

**桌面端**：编辑 `progress.json` 并 push，或由 Claude Code 的 `update-board` skill 在论文会话结束时自动更新。

两边改同一个文件，保存前会用 sha 比对，检测到仓库已有更新版本时拒绝覆盖。

仓库公开，仅存放进度性描述，不含数据、代码与论文正文。
