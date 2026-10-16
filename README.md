# README 写作与项目说明

让 Agent 把项目说明写给第一次来的读者：先说明用途和具体用法，再分层提供启动、开发与交接入口。

这是给支持 Agent Skills 的 Agent 阅读的文字规范，不是应用、MCP 服务或自动扫描程序。

## 一个具体例子

以下输入和输出是虚构示意，不代表真实产品效果。

**使用前：** 一个虚构工具的 README 开头只有“基于 Python 的高效数据处理平台”，随后是一大段开发命令。

**使用后：** “把一份支出 CSV 按月份汇总为另一份 CSV。运行 `python summarize.py demo.csv`，在终端看到输出位置。当前只支持 date、amount 两列，不会修改原文件；已有同名输出文件会被覆盖。”随后给使用入口，再链接开发说明。

## 安装与触发

Codex 用户可将仓库直接安装到用户级 Skills 目录。需要 Git；目标目录必须不存在，已有同名 Skill 时先比较，不覆盖：

```sh
mkdir -p ~/.agents/skills
git clone https://github.com/Yorushikamimimi/readme-and-project-positioning.git ~/.agents/skills/readme-and-project-positioning
```

仓库根目录就是 Skill 目录，只有一份 [SKILL.md](SKILL.md)。若客户端没有发现，按客户端说明刷新或重启，再显式触发：

```text
请使用 $readme-and-project-positioning，核对当前项目，把 README 改成首次读者能看懂的说明。只改文档，不启动项目。
```

也可以把仓库克隆到自己的源码目录，然后按客户端支持的方式将该目录链接或复制到 Skills 目录。其他客户端的发现路径和触发方式需按各自文档核对；本项目不承诺所有平台兼容。

## 会交付什么

README 实际修改或审阅建议，以及修改位置、事实依据、已核对与未验证事项。

它是文字工作流，不会自动证明项目可运行；没有截图、安装包或测试证据时应如实说明。

使用者已有明确授权时直接执行；缺少且影响结果的权限才询问。调用 Skill 不自动授权读取凭证或私人资料、安装依赖、启动项目、派出多个 Agent、提交、推送或公开仓库。实际动作遵从使用者自己的项目规则和已有授权。

## 验证与限制

初始版本的隔离验证结果见 [当前进度](CURRENT_PROGRESS.md)。格式检查和虚构案例验证分别记录；本地验证不等于所有 Agent 平台、真实项目或生产环境通过。未提供 App、DMG 或 Release 安装包。

## 维护与来源

公开版本以本仓库根目录 SKILL.md 为维护源；复制安装的副本需要使用者主动比较、更新，符号链接则直接引用源码目录。已有的本机定制版不会因本仓库发布自动替换，也不要求使用维护者的账号、目录或工作流。

- [Agent Skills 格式](https://agentskills.io/specification)
- [Codex Skills 文档](https://developers.openai.com/codex/skills/)
- 具体写法或审查依据见 SKILL.md 末尾参考链接。链接材料的版权归各自作者，本项目未复制其代码或成段文案。
- [MIT 许可证](LICENSE)
