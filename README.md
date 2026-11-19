# Reactive Builder Camp 学习记录

## 环境准备
- 操作系统：Windows (WSL2 Ubuntu)
- Foundry 版本：forge 1.1.0.0-nightly
- 测试钱包地址：0x1866B14869E3DFfd28eF11dFaf85dF5e6d031b49
- Lasna 地址页链接：
- 本地测试结果（选做）：

## 遇到的问题
- 正在做哪一步：安装 Foundry 时，执行 curl -L https://foundry.paradigm.xyz | bash
- 报错：curl: (35) Recv failure: Connection reset by peer 以及 Unable to establish SSL connection
- 解决方式：因为 WSL 内部网络连接 GitHub 被干扰，无法使用命令行直接下载。改为在 Windows 浏览器中手动下载 Foundry 的 Linux 压缩包（foundry_nightly_linux_amd64.tar.gz），移动到 WSL 中解压，最后通过修改 .bashrc 永久配置环境变量解决。
