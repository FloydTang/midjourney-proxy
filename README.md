# midjourney-proxy

> 更多功能：[midjourney-proxy-plus](https://github.com/litter-coder/midjourney-proxy-plus)

代理 MidJourney 的discord频道，实现api形式调用AI绘图

[![GitHub release](https://img.shields.io/static/v1?label=release&message=v2.4&color=blue)](https://www.github.com/novicezk/midjourney-proxy)
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

## 主要功能
- [x] 支持 Imagine 指令和相关动作
- [x] Imagine 时支持添加图片base64，作为垫图
- [x] 支持 Blend(图片混合)、Describe(图生文) 指令
- [x] 支持任务实时进度
- [x] 支持中英文翻译，需配置百度翻译或gpt
- [x] prompt 敏感词判断，支持覆盖调整
- [x] 任务队列，默认队列10，并发3。可参考 [MidJourney订阅级别](https://docs.midjourney.com/docs/plans) 调整mj.queue
- [x] user-token 连接 wss，可以获取错误信息和完整功能
- [x] 支持 discord域名(server、cdn、wss)反代，配置 mj.ng-discord

## 使用前提
1. 注册并订阅 MidJourney，创建自己的频道，参考 https://docs.midjourney.com/docs/quick-start
2. 获取用户Token、服务器ID、频道ID等：[获取方式](./docs/discord-params.md)

## 快速启动
1. `Railway`: 基于Railway平台，不需要自己的服务器: [部署方式](./docs/railway-start.md)；若Railway不能使用，可使用Zeabur启动
2. `Zeabur`: 基于Zeabur平台，不需要自己的服务器: [部署方式](./docs/zeabur-start.md)
3. `Docker`: 在服务器或本地使用Docker启动: [部署方式](./docs/docker-start.md)

## 本地开发
- 依赖java17和maven
- 更改配置项: 修改src/main/application.yml
- 项目运行: 启动ProxyApplication的main函数
- 更改代码后，构建镜像: Dockerfile取消VOLUME的注释，执行 `docker build . -t midjourney-proxy`

## 配置项
- mj.discord.guild-id：discord服务器ID
- mj.discord.channel-id：discord频道ID
- mj.discord.user-token：discord用户Token
- mj.discord.session-id：discord用户的sessionId，不设置时使用默认的，建议从interactions请求中复制替换
- mj.discord.user-agent：调用discord接口、连接wss时的user-agent，默认使用作者的，建议从浏览器network复制替换
- 更多配置查看 [配置项](./docs/config.md)

## 相关文档
1. [API接口说明](./docs/api.md)
2. [版本更新记录](https://github.com/novicezk/midjourney-proxy/wiki/%E6%9B%B4%E6%96%B0%E8%AE%B0%E5%BD%95)

## 注意事项
1. 作图频繁等行为，可能会触发midjourney账号警告，请谨慎使用
2. 常见问题及解决办法见 [Wiki / FAQ](https://github.com/novicezk/midjourney-proxy/wiki/FAQ)
3. 在 [Issues](https://github.com/novicezk/midjourney-proxy/issues) 中提出其他问题或建议
4. 感兴趣的朋友也欢迎加入交流群讨论一下，扫码进群名额已满，加管理员微信邀请进群

 <img src="https://raw.githubusercontent.com/novicezk/midjourney-proxy/main/docs/manager-qrcode.png" width="220" alt="微信二维码"/>

## 应用项目
依赖此项目且开源的，欢迎联系作者，加到此处展示
- [wechat-midjourney](https://github.com/novicezk/wechat-midjourney) : 代理微信客户端，接入MidJourney，仅示例应用场景，不再更新
- [stable-diffusion-mobileui](https://github.com/yuanyuekeji/stable-diffusion-mobileui) : SDUI，基于本接口和SD，可一键打包生成H5和小程序
- [ChatGPT-Midjourney](https://github.com/Licoy/ChatGPT-Midjourney) : 一键拥有你自己的 ChatGPT+Midjourney 网页服务
- [MidJourney-Web](https://github.com/ConnectAI-E/MidJourney-Web) : 🍎 Supercharged Experience For MidJourney On Web UI
- [koishi-plugin-midjourney-discord](https://github.com/araea/koishi-plugin-midjourney-discord) : Koishi插件，在Koishi支持的聊天平台中调用Midjourney

## 其它
如果觉得这个项目对你有所帮助，请帮忙点个star；也可以请作者喝杯茶～

 <img src="https://raw.githubusercontent.com/novicezk/midjourney-proxy/main/docs/receipt-code.png" width="220" alt="二维码"/>

[![Star History Chart](https://api.star-history.com/svg?repos=novicezk/midjourney-proxy&type=Date)](https://star-history.com/#novicezk/midjourney-proxy&Date)

---

<!-- jiuliang-about-start -->

## 关于半斤九两 / About EVEN BETTER

半斤九两科技（EVEN BETTER）专注“外贸 + AI”的真实落地。我们希望帮助外贸企业把产品、客户、渠道和团队流程，沉淀成客户看得懂、渠道跑得动、团队留得下的系统。

我们主要提供：

- 外贸 AI 落地方法：围绕 Build / Traffic / Team，判断企业该先建资产、放流量，还是建系统。
- 企业表达与内容增长：把产品、案例、FAQ、老板经验和信任证据，整理成海外客户看得懂的内容资产。
- 主动开发流程：从客户画像、线索搜索、客户背调到开发信和跟进复盘，跑出可复用闭环。
- 团队 AI 工作流：把经验写进 AGENTS.md、SOP、模板库、检查清单和可复用 Skill。

更多内容可以查看我们整理的 [《外贸人 Codex 蓝皮书》](https://github.com/FloydTang/waimaoren-codex-bluebook)。

### 找到我们

- 官网：[tang92.com](https://tang92.com)
- 公众号：半斤九两
- GitHub：[@FloydTang](https://github.com/FloydTang)

扫码关注公众号，领取后续模板、案例和更新；也可以通过公众号后台留言联系九两。

<p>
  <img src="https://raw.githubusercontent.com/FloydTang/waimaoren-codex-bluebook/main/assets/wechat-qr.png" alt="半斤九两公众号二维码" width="180">
</p>

<!-- jiuliang-about-end -->
