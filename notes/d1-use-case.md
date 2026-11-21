生态案例Uniswap V2 Stop Order Demo
1.监听哪条链、哪个合约的什么事件？
监听源链上 Uniswap V2 Pair合约发出的 Sync 事件
2.满足什么条件时触发？
当 Sync 事件触发后，UniswapDemoStopOrderReactive 根据最新的储备量计算汇率，当汇率跌破预设的止损阈值时触发回调。
3.在哪条链做什么动作？
在目标链上由 UniswapDemoStopOrderCallback 接收回调，链上复核汇率后，把用户授权的代币转入并经由 Uniswap V2 Router 完成兑换，把换出的代币退回给用户，最后发出 Stop 事件通知 Reactive 合约标记订单完成。
4.如果不用 Reactive，你要怎么做？代价是什么？
不用 Reactive自己写一个链下机器人不断监听 Sync 事件算价格、跌破阈值后自己签名发交易去执行卖出，或者全靠人工盯盘手动操作。
简单在哪里： 省去了自己维护 24 小时不间断运行的价格监控与自动发单机器人，事件驱动的判断和回调由网络机制自动串联。
代价是什么： 需要提前配置参数和代币授权，涉及多步跨链/回调流转与相应资金/Gas 成本，且该止损单是一次性触发即结束的。
<img width="1376" height="768" alt="Gemini_Generated_Image_rvsz6jrvsz6jrvsz" src="https://github.com/user-attachments/assets/a15da1a9-82c4-4df8-a7d6-6f71c695e26a" />
