# Awesome LLM API Keys · 大模型 API Key 申请大全 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 各家 AI 大模型 API Key 去哪申请、有没有免费额度、要不要海外卡、怎么调用——一张表看完。每家都链接到 **[og.cc.cd](https://og.cc.cd/) 的详细中文分步教程**。
>
> Where to get an API key for every major LLM provider — console links, free quotas, payment/region rules and base URLs, with step-by-step guides on [og.cc.cd](https://og.cc.cd/).

核对日期 / Last checked：2026-10-20（xAI、Mistral、MiniMax 为 2026-10-21）

## 目录

- [申请总表](#申请总表)
- [调用信息：Base URL 与环境变量](#调用信息base-url-与环境变量)
- [地区与付款的坑](#地区与付款的坑)
- [Key 安全清单](#key-安全清单)
- [相关工具](#相关工具)
- [English](#english)
- [来源](#来源)

## 申请总表

“支付 / 地区”一列只转述官方原文，不构成法律意见；不提供任何绕过地区限制的方法。

| 厂商 | 控制台 / Key 页面 | 免费额度（已核实） | 支付 / 地区（官方说法） | 详细教程 |
|---|---|---|---|---|
| OpenAI | [platform.openai.com/api-keys](https://platform.openai.com/api-keys) | 允许地区有 Free 用量档（月上限 $100）；赠金金额未写明 | 中国大陆、港澳不在支持国家和地区列表；Build 档需累计购买 $5；支付方式所核页面未写明 | [中文教程](https://og.cc.cd/guides/openai-api-key/) |
| Anthropic Claude | [platform.claude.com/settings/keys](https://platform.claude.com/settings/keys) | 所核文档未写明 | 中国大陆、港澳不在支持地区列表；Key 只显示一次 | [中文教程](https://og.cc.cd/guides/claude-api-key/) |
| Google Gemini | [aistudio.google.com/apikey](https://aistudio.google.com/apikey) | 部分模型有 Free Tier；GCP $300 赠金不能用于 Gemini API | 中国大陆、港澳不在可用地区列表，须满 18 岁；付费需绑定 Cloud Billing、预付最低 $5 | [中文教程](https://og.cc.cd/guides/gemini-api-key/) |
| DeepSeek | [platform.deepseek.com/api_keys](https://platform.deepseek.com/api_keys) | 优先扣赠送余额；金额未写明 | 文档未提及地区限制；支付方式所核页面未写明 | [中文教程](https://og.cc.cd/guides/deepseek-api-key/) |
| 阿里云百炼（北京） | [bailian.console.aliyun.com](https://bailian.console.aliyun.com/) | 新人每模型通常 100 万 Token、90 天 | 免费额度无需实名；按量付费需实名 + 充值；支付宝、银联在线支付、网银等 | [中文教程](https://og.cc.cd/guides/aliyun-bailian-api-key/) |
| 阿里云百炼（新加坡） | [modelstudio.console.alibabacloud.com](https://modelstudio.console.alibabacloud.com/) | 新人每模型通常 100 万 Token、90 天；用完默认转按量付费 | 2026-09-15 起须先完善账号信息；Key 与北京站不互通 | [中文教程](https://og.cc.cd/guides/aliyun-bailian-api-key/) |
| 小米 MiMo | [platform.xiaomimimo.com](https://platform.xiaomimimo.com/) | 有 Welcome Bonus 页面；金额未核实 | 小米账号登录，充值前须实名；国内微信/支付宝/小米支付，海外 Waffo（美元）；国内外 Key 不互通 | [中文教程](https://og.cc.cd/guides/mimo-api-key/) |
| 月之暗面 Kimi | [platform.kimi.com/console/api-keys](https://platform.kimi.com/console/api-keys) | 个人认证后送 15 元代金券（不可用于 Kimi K3） | 充值前须个人认证；微信/支付宝扫码充值 | [中文教程](https://og.cc.cd/guides/kimi-api-key/) |
| 智谱 GLM（bigmodel.cn） | [bigmodel.cn/usercenter/proj-mgmt/apikeys](https://bigmodel.cn/usercenter/proj-mgmt/apikeys) | 所核文档未写明 | 目前调用 API 不强制实名；支付方式所核页面未写明 | [中文教程](https://og.cc.cd/guides/glm-api-key/) |
| Z.ai（智谱国际站） | [z.ai/manage-apikey/apikey-list](https://z.ai/manage-apikey/apikey-list) | 所核文档未写明 | 所核文档未写明 | [中文教程](https://og.cc.cd/guides/glm-api-key/) |
| 火山方舟（豆包） | [console.volcengine.com/ark/region:ark+cn-beijing/apiKey](https://console.volcengine.com/ark/region:ark+cn-beijing/apiKey) | 新用户每模型有免费推理额度（仅在线推理，不含批量） | 免费额度用完后须实名 + 开通模型；支付方式所核页面未写明 | [中文教程](https://og.cc.cd/guides/volcengine-ark-api-key/) |
| OpenRouter | [openrouter.ai/settings/credits](https://openrouter.ai/settings/credits) | 少量免费额度 + `:free` 模型 | 文档未提及地区限制；支持信用卡、支付宝（AliPay）、USDC | [中文教程](https://og.cc.cd/guides/openrouter-api-key/) |
| xAI Grok | [console.x.ai](https://console.x.ai/) | 所核文档未写明（快速开始写明：注册后需充值 credits 才能调用） | 支付方式所核页面未写明 | [官方快速开始](https://docs.x.ai/developers/quickstart) |
| Mistral | [console.mistral.ai](https://console.mistral.ai/) | Free 模式默认开通 API，**无需信用卡**（有用量与速率限制） | Key 可设过期时间，完整 Key 只显示一次 | [官方快速开始](https://docs.mistral.ai/getting-started/quickstarts/studio/activate-and-generate-api-key) |
| MiniMax | [platform.minimax.io/user-center/basic-information/interface-key](https://platform.minimax.io/user-center/basic-information/interface-key) | 所核文档未写明；按量付费在 Billing → Balance 充值 | 支付方式所核页面未写明；另有 M Plan 订阅 Key | [官方快速开始](https://platform.minimax.io/docs/guides/quickstart-preparation) |

> 完整对比与每家分步教程：**[大模型 API Key 申请指南（og.cc.cd）](https://og.cc.cd/guides/how-to-get-llm-api-keys/)**

## 调用信息：Base URL 与环境变量

| 厂商 | Base URL | 环境变量 |
|---|---|---|
| OpenAI | `https://api.openai.com/v1` | `OPENAI_API_KEY` |
| Anthropic Claude | `https://api.anthropic.com（原生 / native）` | `ANTHROPIC_API_KEY` |
| Google Gemini | `generativelanguage.googleapis.com（原生 / native）` | `GEMINI_API_KEY / GOOGLE_API_KEY` |
| DeepSeek | `https://api.deepseek.com` | `DEEPSEEK_API_KEY` |
| 阿里云百炼（北京） | `https://dashscope.aliyuncs.com/compatible-mode/v1` | `DASHSCOPE_API_KEY` |
| 阿里云百炼（新加坡） | `https://dashscope-intl.aliyuncs.com/compatible-mode/v1` | `DASHSCOPE_API_KEY` |
| 小米 MiMo | `https://api.xiaomimimo.com/v1` | `MIMO_API_KEY` |
| 月之暗面 Kimi | `https://api.moonshot.cn/v1` | `MOONSHOT_API_KEY` |
| 智谱 GLM（bigmodel.cn） | `https://open.bigmodel.cn/api/paas/v4` | `未规定 / not prescribed` |
| Z.ai（智谱国际站） | `https://api.z.ai/api/paas/v4/` | `未规定 / not prescribed` |
| 火山方舟（豆包） | `https://ark.cn-beijing.volces.com/api/v3` | `ARK_API_KEY` |
| OpenRouter | `https://openrouter.ai/api/v1` | `OPENROUTER_API_KEY` |
| xAI Grok | `https://api.x.ai/v1` | `XAI_API_KEY` |
| Mistral | `https://api.mistral.ai/v1` | `MISTRAL_API_KEY` |
| MiniMax | `https://api.minimax.io/v1（OpenAI）· https://api.minimax.io/anthropic` | `MINIMAX_API_KEY` |

大多数国内平台和 OpenRouter、xAI、Mistral、MiniMax 都提供 **OpenAI 兼容接口**：把 OpenAI SDK 的 `base_url` 换成上表地址、`api_key` 换成对应 Key 即可。

## 地区与付款的坑

- **OpenAI、Anthropic、Google Gemini** 的支持列表都不包括中国大陆、香港和澳门；OpenAI 明确警告在列表以外访问可能导致账号被封禁。
- **Key 常与地域/站点绑定**：百炼北京与新加坡、MiMo 国内与海外、智谱 bigmodel.cn 与 z.ai 的 Key 都不互通。
- **国内平台普遍要实名，时机不同**：百炼、火山方舟在免费额度用完后；MiMo、Kimi 在充值前；智谱目前调用 API 不强制。
- **“免费”有附加条件**：GCP $300 赠金不能用于 Gemini API；Kimi 15 元代金券不能用于 K3；火山方舟免费额度不含批量推理；百炼新加坡站额度用完默认转按量付费。
- **不想绑海外卡？** 已核实可用支付宝/微信的：百炼、MiMo（国内）、Kimi、OpenRouter（AliPay）；Mistral 的 Free 模式无需信用卡。

## Key 安全清单

1. 用环境变量或 `.env`（先加进 `.gitignore`），不要把 Key 写进代码或提交到 Git。
2. 不要把 Key 放进浏览器或手机 App 的前端代码。
3. 能限权就限权：Gemini Key 只开 Gemini API；百炼可限 IP 和模型；火山方舟可限 Model ID、接入点和 IP。
4. 泄露立刻换：先建新 Key、切换应用，再吊销旧 Key。
5. 多建 Key 不等于多给额度：DeepSeek、Kimi、OpenRouter 按账号计限额。

```bash
# 提交前检查有没有把 Key 暂存进去
git diff --cached | grep -nE 'sk-|API_KEY=' && echo "STOP: a key is staged"
```

## 相关工具

- [Token 计数器](https://og.cc.cd/token-counter/)：粘贴提示，看各模型的 token 数和单次费用
- [大模型成本计算器](https://og.cc.cd/llm-cost-calculator/)：按每日请求量估算月费（含缓存、DeepSeek 闲时）
- [主流模型 API 价格对比](https://og.cc.cd/guides/llm-api-pricing-comparison/) · 价格表仓库 [llm-api-pricing](https://github.com/yijzhu/llm-api-pricing)
- [个人 AI 助理 / Agent 对比](https://github.com/yijzhu/awesome-personal-ai-agents)

---

## English

| Provider | Console | Free quota (verified) | Payment / region (official wording) | Guide |
|---|---|---|---|---|
| OpenAI | [Console](https://platform.openai.com/api-keys) | Free usage tier ($100/month cap) in allowed geographies; credit amount not stated | Mainland China, HK, Macau not on the supported list; Build tier needs $5 in purchases; payment methods not stated | [Guide (EN/中文)](https://og.cc.cd/guides/openai-api-key/) |
| Anthropic Claude | [Console](https://platform.claude.com/settings/keys) | Not stated | Mainland China, HK, Macau not on the supported-regions list; key shown once | [Guide (EN/中文)](https://og.cc.cd/guides/claude-api-key/) |
| Google Gemini | [Console](https://aistudio.google.com/apikey) | Free Tier on some models; the $300 GCP credit cannot be used | Mainland China, HK, Macau not on the available-regions list; 18+; paid use needs Cloud Billing, $5 minimum prepay | [Guide (EN/中文)](https://og.cc.cd/guides/gemini-api-key/) |
| DeepSeek | [Console](https://platform.deepseek.com/api_keys) | Granted balance is used first; amount not stated | No regional restriction in the docs; payment methods not stated | [Guide (EN/中文)](https://og.cc.cd/guides/deepseek-api-key/) |
| Alibaba Bailian (Beijing) | [Console](https://bailian.console.aliyun.com/) | New users: usually 1M tokens per model, 90 days | Free quota needs no real-name; pay-as-you-go needs real-name + top-up; AliPay, UnionPay, online banking | [Guide (EN/中文)](https://og.cc.cd/guides/aliyun-bailian-api-key/) |
| Alibaba Model Studio (Singapore) | [Console](https://modelstudio.console.alibabacloud.com/) | Usually 1M tokens per model, 90 days; rolls into pay-as-you-go by default | Complete account info first (since 2026-09-15); keys not shared with Beijing | [Guide (EN/中文)](https://og.cc.cd/guides/aliyun-bailian-api-key/) |
| Xiaomi MiMo | [Console](https://platform.xiaomimimo.com/) | “Welcome Bonus” page exists; amount not verified | Xiaomi account; real-name before top-up; China: WeChat/AliPay/Mi Pay, overseas: Waffo (USD); keys not shared | [Guide (EN/中文)](https://og.cc.cd/guides/mimo-api-key/) |
| Moonshot Kimi | [Console](https://platform.kimi.com/console/api-keys) | ¥15 voucher after verification (not for Kimi K3) | Personal verification before top-up; WeChat / AliPay QR payment | [Guide (EN/中文)](https://og.cc.cd/guides/kimi-api-key/) |
| Zhipu GLM (bigmodel.cn) | [Console](https://bigmodel.cn/usercenter/proj-mgmt/apikeys) | Not stated | API calls don’t currently require real-name; payment not stated | [Guide (EN/中文)](https://og.cc.cd/guides/glm-api-key/) |
| Z.ai (Zhipu international) | [Console](https://z.ai/manage-apikey/apikey-list) | Not stated | Not stated | [Guide (EN/中文)](https://og.cc.cd/guides/glm-api-key/) |
| Volcengine Ark (Doubao) | [Console](https://console.volcengine.com/ark/region:ark+cn-beijing/apiKey) | New-user free inference quota per model (online inference only) | Real-name + enable the model after the free quota; payment not stated | [Guide (EN/中文)](https://og.cc.cd/guides/volcengine-ark-api-key/) |
| OpenRouter | [Console](https://openrouter.ai/settings/credits) | Small free allowance + `:free` models | No regional restriction in the docs; cards, AliPay, USDC | [Guide (EN/中文)](https://og.cc.cd/guides/openrouter-api-key/) |
| xAI Grok | [Console](https://console.x.ai/) | Not stated (quickstart: load credits before using the API) | Payment methods not stated | [Official quickstart](https://docs.x.ai/developers/quickstart) |
| Mistral | [Console](https://console.mistral.ai/) | Free mode: API enabled by default, **no credit card** (usage and rate limits apply) | Keys can expire; the full key is shown only once | [Official quickstart](https://docs.mistral.ai/getting-started/quickstarts/studio/activate-and-generate-api-key) |
| MiniMax | [Console](https://platform.minimax.io/user-center/basic-information/interface-key) | Not stated; pay-as-you-go tops up under Billing → Balance | Payment not stated; separate M Plan subscription key | [Official quickstart](https://platform.minimax.io/docs/guides/quickstart-preparation) |

Most Chinese platforms plus OpenRouter, xAI, Mistral and MiniMax expose an **OpenAI-compatible API** — swap `base_url` and `api_key` in the OpenAI SDK (see the table above).

Full comparison: **[How to get an LLM API key (og.cc.cd)](https://og.cc.cd/guides/how-to-get-llm-api-keys/)** · Tools: [token counter](https://og.cc.cd/token-counter/) · [LLM cost calculator](https://og.cc.cd/llm-cost-calculator/)

## 来源

每篇 og.cc.cd 教程末尾都列出了所用官方页面。表外三家的来源：

- [og.cc.cd 各家申请教程（含官方来源列表）](https://og.cc.cd/guides/how-to-get-llm-api-keys/)
- [xAI — Quickstart](https://docs.x.ai/developers/quickstart)
- [Mistral — Activate Studio and generate an API key](https://docs.mistral.ai/getting-started/quickstarts/studio/activate-and-generate-api-key)
- [MiniMax — Prerequisites](https://platform.minimax.io/docs/guides/quickstart-preparation)

---

## 许可与署名

内容以 [CC BY 4.0](LICENSE) 发布，转载请注明来源：[og.cc.cd — AI 开发者工具箱](https://og.cc.cd/)。
本仓库只收录官方页面写明的事实；“未写明”表示我们核对的官方页面没有说明，不代表答案是否定的。价格、额度和地区政策随时会变，**付费前请以官方页面为准**。

发现过期或错误？欢迎提 [Issue](../../issues) 或 PR，并附上官方来源链接。

## License

Content is licensed under [CC BY 4.0](LICENSE). Please credit [og.cc.cd — AI Developer Toolbox](https://og.cc.cd/).
Only facts stated on official pages are listed; “not stated” means the official pages we checked do not say. Prices, quotas and region rules change — **always confirm on the official page before you pay**.

Spotted something outdated? Open an [issue](../../issues) or PR with the official source link.
