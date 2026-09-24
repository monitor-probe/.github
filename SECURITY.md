# 安全策略

## 报告漏洞

请不要在公开的 issue、讨论区或 PR 里描述漏洞。到出问题的仓库点 **Security → Report a vulnerability**
私下提交，报告只有维护者能看到。

| 仓库 | 范围 |
|---|---|
| [monitor](https://github.com/monitor-probe/monitor/security/advisories/new) | hub、面板、`install.sh` 与 `install-hub.sh` |
| [agent](https://github.com/monitor-probe/agent/security/advisories/new) | agent |
| [monitor-theme-default](https://github.com/monitor-probe/monitor-theme-default/security/advisories/new) | 默认主题 |
| [monitor-theme-serverstatus](https://github.com/monitor-probe/monitor-theme-serverstatus/security/advisories/new) | serverstatus 主题 |
| [monitor-document](https://github.com/monitor-probe/monitor-document/security/advisories/new) | 文档站 |

不确定属于哪个仓库时，提交到 monitor。

报告中请尽量写明：受影响的版本、部署方式（一键脚本或 Docker，前面有哪些反向代理）、复现步骤，以及
攻击者需要具备的条件——匿名访问者、持有某个节点 token 的人，还是已登录的管理员。

## 支持的版本

只为最新发布的版本修复安全问题，旧版本请升级。

## 范围

以下情况均按安全问题处理：

- 未登录即可读到节点的 IP、主机名、备注或 token，或调用面板接口
- 一个节点的 token 能读写其它节点，或改动 hub 的设置
- 匿名请求能让 hub 占用远超正常水平的内存、CPU 或出网流量
- 安装脚本或 agent 以 root 执行了非预期的内容
- 主题上传、备份恢复等路径能写到 hub 数据目录之外
