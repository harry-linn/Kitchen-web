# 厨房 Kitchen — 隐私政策 / Privacy Policy

> 本文件是「厨房 / Kitchen」(以下简称「本 app」)的隐私政策。
> 此版本同时面向中文用户与英文用户;如有歧义以中文版本为准。
> 最后更新:2026-05-08

---

## 中文版本

### 1. 总览

「厨房」是一款本地优先的菜谱 / 冰箱管理 app。我们的设计原则是:**用户的所有数据默认只保存在用户自己的设备和用户自己的 iCloud 上。** 我们(开发者本人)不持有用户数据,不向第三方出售数据,不投放广告,不做跨 app 追踪。

我们只在用户**主动**触发"AI 智能"相关功能时,才会把用户当时提交的内容(菜谱文本 / 图片 / 语音转写后的文本)经过 HTTPS 发送给 AI 服务商,以获得返回结果。除此之外,本 app 不会把任何数据离开你的设备。

### 2. 我们收集哪些数据 / 不收集哪些数据

#### 2.1 我们**会**离机发送的内容(仅在你主动用 AI 时)

| 数据 | 出口 | 触发条件 |
| - | - | - |
| 菜谱标题 / 步骤 / 食材文本 | DeepSeek API (HTTPS) | 你点击"AI 生成菜谱""菜谱步骤一键改写""冰箱 AI 推荐做菜"等按钮时 |
| 你拍照 / 选相册导入的菜谱 / 食材图片(转为 base64) | DeepSeek API (HTTPS) | 你使用"拍照导入""相册导入""冰箱拍照识别食材"等功能时 |
| 你说话后由本地语音引擎转写得到的**文本**(不是音频) | DeepSeek API (HTTPS) | 你在"语音快速入库"中点击"AI 智能分析"时 |

这些请求**不携带**任何账号、邮箱、Apple ID、设备 ID 或其它身份标识。从 DeepSeek 的视角看,所有请求都是匿名的。

#### 2.2 我们**不会**收集的内容

- ❌ 任何形式的账号、邮箱、电话号码、真实姓名
- ❌ 通讯录、健康数据、定位信息
- ❌ 录音音频本身(语音入库的录音由 Apple `SFSpeechRecognizer` 本地转写,音频永不离开设备)
- ❌ 设备 ID / IDFA / 广告 ID / 跨 app 追踪标识
- ❌ 浏览记录、使用统计、崩溃日志(本 app 当前未接入任何分析或崩溃上报 SDK)
- ❌ 你的购买记录(由 Apple StoreKit 处理,我们只在本地缓存"是 / 否会员"这一个布尔值)

#### 2.3 你的菜谱、冰箱、设置等业务数据

存储在以下两个地方:

1. **你的设备本地**(由 Apple Core Data 管理)
2. **你自己的 iCloud**(仅当你打开"云同步"开关时,数据存入你 Apple ID 名下的 CloudKit 私有库 / 你创建的家庭共享 zone)

我们(开发者)**无法访问** iCloud 上的数据,Apple 用 end-to-end 加密接管,iCloud 数据的隐私权完全归属于你。

### 3. 第三方服务

#### 3.1 DeepSeek

我们使用 DeepSeek 提供的大模型 API 实现 AI 相关功能。每次调用都是无状态的、匿名的 HTTPS 请求。请求中包含的内容仅限于上述 §2.1 列出的项目。DeepSeek 自身的隐私政策与数据使用条款见:https://www.deepseek.com/

如果你不希望任何数据离开你的设备,请**不要使用任何 AI 相关功能**(可在「设置 → 账户与服务 → AI」里关闭对应开关,或者直接不点击 AI 按钮)。app 的全部本地功能(手动添加菜谱 / 冰箱、本地搜索、回收站、备份导入)都不依赖 DeepSeek。

#### 3.2 Apple iCloud / CloudKit

仅当你主动开启"云同步"或"家庭分享冰箱"时使用。数据存放在你 Apple ID 名下的 CloudKit 容器,由 Apple 端到端加密。开发者无法访问。

#### 3.3 Apple StoreKit

订阅 / 购买流程完全由 Apple StoreKit 处理。本 app 不接触你的支付凭证,只能通过 Apple 提供的接口查询你当前是否拥有有效的会员权益。

### 4. Siri / 快捷指令

本 app 接入了 iOS 的 App Intents 框架,用户可以通过 Siri 语音触发。Siri 转写得到的语音指令由 Apple 在系统层面处理后,以纯文本形式传给本 app。本 app 不会把这部分文本再转发给任何第三方,除非用户随后主动触发了 AI 功能(同 §2.1)。

### 5. 权限请求

| 权限 | 用途 | 不授权会怎样 |
| - | - | - |
| 相机 | 拍照添加菜谱、冰箱拍照识别食材 | 上述两个功能不可用,其余功能正常 |
| 相册 | 从相册添加菜谱、保存生成图片 | 上述功能不可用,其余功能正常 |
| 麦克风 + 语音识别 | 语音快速入库(本地转写) | 该功能不可用,其余功能正常 |
| iCloud | 跨设备同步 / 家庭分享冰箱 | 同步功能关闭,纯本地使用 |
| Siri | 调用本 app 的快捷指令 | 用户不能用 Siri,只能在 app 内操作 |
| 通知 | 食材临期提醒、消息中心 | 收不到提醒,其余功能正常 |
| FaceID / TouchID | 进入"危险操作 / 扔掉冰箱" | 该入口不可用,其余功能正常 |

### 6. 儿童隐私

本 app 不针对 13 岁以下儿童,不刻意收集任何与年龄相关的信息。如果监护人发现儿童在使用本 app 并产生了 AI 调用,可联系开发者删除相关请求记录(详见 §8)。

### 7. 数据如何删除

| 想删除 | 操作 |
| - | - |
| 本机数据 | 卸载 app(iOS 会自动删除沙盒) |
| iCloud 上的数据 | iOS 系统设置 → Apple ID → iCloud → 管理账户存储 → Kitchen → 删除数据 |
| 已经发出的 DeepSeek 请求 | 联系开发者邮箱(见 §8),开发者会代你向 DeepSeek 发起删除请求(以 DeepSeek 政策为准) |
| 订阅 | iOS 系统设置 → Apple ID → 订阅 → 取消(由 Apple 处理) |

### 8. 联系方式

- 开发者:Harry Linn / 林杭
- 联系邮箱:`Harry.linn@hotmail.com`

收到邮件后我们会在 7 个工作日内回复。

### 9. 政策更新

本政策可能因功能变化而更新。重要变更会通过 app 内提示或新版本 release notes 告知。本文件的最新版本始终发布在:

`https://kitchen-legal.harry-linn.workers.dev`


---

## English Version

### 1. Overview

Kitchen is a local-first recipe and fridge manager. By design, **all your data lives on your device and in your own iCloud only.** The developer does not hold your data, does not sell data to third parties, does not run ads, and does not track across apps.

The only time data leaves your device is when you **actively** use an "AI"-related feature; in that case the content you submit (recipe text, image, transcribed voice text) is sent over HTTPS to our AI vendor for processing. Outside of those moments, no data leaves your device.

### 2. What We Collect / What We Don't

#### 2.1 What we send off-device (only when you actively use AI)

| Data | Destination | Trigger |
| - | - | - |
| Recipe title / steps / ingredient text | DeepSeek API (HTTPS) | Buttons such as "AI generate recipe", "Rewrite steps", "Recommend a meal from fridge" |
| Photos you import (encoded as base64) | DeepSeek API (HTTPS) | Camera / Photo Library import, fridge photo recognition |
| The **transcribed text** of your voice (not the audio) | DeepSeek API (HTTPS) | "Smart parse" button inside the voice quick-entry sheet |

These requests do **not** include any account, email, Apple ID, device ID, or any other identifier. From DeepSeek's perspective every request is anonymous.

#### 2.2 What we never collect

- ❌ Account / email / phone / real name (we have no account system)
- ❌ Contacts, health data, location
- ❌ Raw audio (voice entry uses Apple `SFSpeechRecognizer` on-device; audio never leaves your phone)
- ❌ Device ID / IDFA / cross-app tracking identifiers
- ❌ Browsing history, usage analytics, crash logs (no analytics / crash SDK is currently integrated)
- ❌ Your purchase history (StoreKit is handled by Apple; we only cache a single boolean entitlement locally)

#### 2.3 Your recipes / fridge / settings data lives in

1. Your device (managed by Apple Core Data)
2. Your own iCloud (CloudKit private database / shared zones), only when you opt-in via Settings → Account & Services → Cloud Sync.

The developer cannot read iCloud data; Apple end-to-end encrypts it for you.

### 3. Third-Party Services

#### 3.1 DeepSeek

We use DeepSeek's LLM API to power the AI features. Each call is a stateless, anonymous HTTPS request, carrying only the items listed in §2.1. Their privacy and data terms apply: https://www.deepseek.com/

If you do **not** want any data to leave your device, simply **do not use any AI feature**. All purely local features (manual add, search, trash, backup, import) work without DeepSeek.

#### 3.2 Apple iCloud / CloudKit

Used only when you opt-in to Cloud Sync or shared fridge. Stored under your Apple ID, end-to-end encrypted by Apple. The developer has no access.

#### 3.3 Apple StoreKit

Handles all subscriptions. The app never sees your payment information; it only queries Apple whether you currently hold a valid entitlement.

### 4. Siri / Shortcuts

Kitchen exposes 20 App Intents to Siri / Shortcuts. Apple transcribes your speech on the system level and hands the text to the app. The app does not forward this text to any third party unless you subsequently trigger an AI feature (see §2.1).

### 5. Permissions

| Permission | Use |
| - | - |
| Camera | Photo recipe import / fridge photo recognition |
| Photo Library | Add recipes from albums |
| Microphone + Speech Recognition | Voice quick-entry (on-device transcription) |
| iCloud | Cross-device sync / family-shared fridge |
| Siri | Voice triggers for app shortcuts |
| Notifications | Expiring-soon alerts, in-app notification center |
| FaceID / TouchID | Gate the "Danger Zone / wipe fridge" actions |

Declining any permission disables the corresponding feature only; the rest of the app keeps working.

### 6. Children's Privacy

Kitchen is not directed at children under 13 and does not knowingly collect age-related data. Guardians who discover that a child has triggered AI calls may contact the developer (§8) to request DeepSeek-side deletion.

### 7. How to Delete Your Data

| To delete | Action |
| - | - |
| On-device data | Uninstall the app |
| iCloud data | iOS Settings → Apple ID → iCloud → Manage Account Storage → Kitchen → Delete |
| Past DeepSeek requests | Email the developer (§8) — we will forward your deletion request to DeepSeek (subject to DeepSeek's policy) |
| Subscription | iOS Settings → Apple ID → Subscriptions → Cancel |

### 8. Contact

- Developer: Harry Linn
- Email: `Harry.linn@hotmail.com`

We respond within 7 business days.

### 9. Policy Updates

This policy may evolve as features evolve. Material changes will be announced via in-app notice or release notes. The latest version is always at:

`https://kitchen-legal.harry-linn.workers.dev`
