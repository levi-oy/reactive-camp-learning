# Reactive Builder Camp 学习记录

## 环境准备
- 操作系统：Windows (WSL2 Ubuntu)
- Foundry 版本：forge 1.1.0.0-nightly
- 测试钱包地址：0x1866B14869E3DFfd28eF11dFaf85dF5e6d031b49
- Lasna 地址页链接：https://lasna.reactscan.net/address/0x1866b14869e3dffd28ef11dfaf85df5e6d031b49
- 本地测试结果（选做）：

## 遇到的问题
- 正在做哪一步：安装 Foundry 时，执行 curl -L https://foundry.paradigm.xyz | bash
- 报错：curl: (35) Recv failure: Connection reset by peer 以及 Unable to establish SSL connection
- 解决方式：因为 WSL 内部网络连接 GitHub 被干扰，无法使用命令行直接下载。改为在 Windows 浏览器中手动下载 Foundry 的 Linux 压缩包（foundry_nightly_linux_amd64.tar.gz），移动到 WSL 中解压，最后通过修改 .bashrc 永久配置环境变量解决。
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0358fb8e-67b7-4ac0-acc3-cb360ad352bc" />

D1 
Where to Begin
Step 1 — Reactive Basics 
Origins & Destinations
1. **源链是事件发生、被监听的地方；目标链是 Reactive 帮你执行动作的地方，两者可以不同。**  
2. **回调通过官方 Callback Proxy 转交，目标链合约认这个中间人地址才执行，防止冒充。**  
3. **主网和测试网不能混用：源链是测试网，目标链也必须是测试网。**  
拿 **Ethereum Sepolia** 这一行举例：`Ethereum Sepolia | ✅ | 11155111 | 0xAa14... | Chainlist` 意思是——这条链叫 Ethereum Sepolia，既能当源链也能当目标链，Chain ID 是 11155111，Callback Proxy 地址是 `0xAa14...`，RPC 入口去 Chainlist 查。

官方 Demo 仓库
https://github.com/Reactive-Network/reactive-smart-contract-demos
