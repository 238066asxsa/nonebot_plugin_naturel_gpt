<div align="center">
  <a href="https://v2.nonebot.dev/store"><img src="./image/README/nbp_logo.png" width="180" height="180" alt="NoneBotPluginLogo"></a>
  <br>
  <p><img src="./image/README/NoneBotPlugin.svg" width="240" alt="NoneBotPluginText"></p>
</div>

<div align="center">
    ✨ 更人性化(拟人)的GPT聊天Ai插件! ✨<br/>
    🧬 支持多个人格自定义 / 切换 | 尽情发挥你的想象力吧！ ⚙️<br/>
    🎆 如果喜欢请点个⭐吧！您的支持就是我持续更新的动力 🎉<br/>
    <a href="./LICENSE">
        <img src="https://img.shields.io/badge/license-Apache 2.0-6cg.svg" alt="license">
    </a>
    <a href="https://pypi.python.org/pypi/nonebot-plugin-naturel-gpt">
        <img src="https://img.shields.io/pypi/v/nonebot-plugin-naturel-gpt.svg" alt="pypi">
    </a>
    <img src="https://img.shields.io/badge/python-3.8+-6a9.svg" alt="python">
    <a href="https://jq.qq.com/?_wv=1027&k=71t9iCT7">
        <img src="https://img.shields.io/badge/加入交流群-636925153-c42.svg" alt="python">
    </a>
    <h2>🧩 [2023/2/18] v1.3 重要更新: 自定义拓展支持 🧩</h2>
    <p>本次更新后插件开始支持自定义拓展，您可以直接通过自然语言直接调用多种拓展功能，包括 文本/图片/语音</p>
    <p>默认提供了三个样例拓展（发送随机数、发送图片、发送表情包），支持仅使用少量的代码就能实现各种自定义功能</p>
    <p>! 详见下方 <strong>自定义拓展部分</strong> !</p>
</div>

## 💡 功能列表

> 以下未勾选功能仅表示未来可能开发的方向，不代表实际规划进度，具体开发事项可能随时变动
> 勾选: 已实现功能；未勾选: 正在开发 / 计划开发 / 待定设计

* [X] 自动切换api_key: 支持同时使用多个openai_api_key，失效时自动切换
* [X] 自定义人格预设: 可自定义的人格预设，打造属于你的个性化的TA
* [X] 聊天基本上下文关联: 群聊场景短期记忆上下文关联，尽力避免聊天出戏
* [X] 聊天记录总结记忆: 自动总结聊天记忆，具有一定程度的长期记忆能力
* [X] 用户印象记忆: 每个人格对每个用户单独记忆印象，让TA能够记住你
* [X] 数据持久化存储: 重启后TA也不会忘记你（使用pickle保存文件）
* [X] 人格切换: 可随时切换不同人格，更多不一样的TA
* [X] 新增/编辑人格: 使用指令随时编辑TA的性格
* [X] 自定义触发词: 希望TA更主动一点？或者更有目标一点？
* [X] 自定义屏蔽词: 不想让TA学坏？需要更安全一点？
* [X] 随机参与聊天: 希望TA主动一些？TA会偶然在你的群组中冒泡……
* [X] 异步支持：赋予TA更强大的消息处理能力！
* [X] 可拓展功能: 厌倦了单调的问答AI？为TA解锁超能力吧！TA能够根据你的语言主动调用拓展模块 (如:发送图片、语音等) TA的上限取决于你的想象
* [X] 多段回复能力: 厌倦了传统一问一答的问答式聊天？TA能够做得更好！
* [ ] 潜在人格唤醒机制: 一定条件下，潜在人格会被主动唤醒
* [ ] 主动聊天参与逻辑: 尽力模仿人类的聊天参与逻辑，目标是让TA能够真正融入你的群组
* [ ] 回忆录生成: 记录你们之间的点点滴滴，获取你与TA的专属回忆
* [ ] 记忆编辑功能: 不小心让TA记住了奇怪的事情？要不还是忘了吧
* [ ] TTS文字转语音: 让TA开口说话！(暂定使用Vits，但是仍存在一些技术问题，欢迎大佬参与合作指点)

## 📕 使用方式

1. 安装本插件并启用，详见NoneBot关于插件安装的说明
2. 加载插件并启动一次NoneBot服务
3. 查看自动生成的 `config/naturel_gpt.config.yml` ，并填入你的OpenAi_Api_key
4. 在机器人所在的群组或者私聊窗口@TA或者 `提到`TA当前的 `人格名` 即开始聊天
5. 使用命令 `rg / 人格设定 / 人格 / identity` 即可查看bot信息和相关指令
6. 启用后bot会开始监听所有消息并适时作出记录和回应，如果你不希望bot处理某条消息，请在消息前加上忽视符（默认为 `#` ，可在配置文件中修改）

## 🛠️ 参数说明 — `config/naturel_gpt.config.yml`

<details> <summary>🔍点击查看可配置的参数说明</summary> <pre><code>

| 参数名                        | 类型  | 释义                                       | 默认值                         | 编辑建议                                                                                           |
| ----------------------------- | ----- | ------------------------------------------ | ------------------------------ | -------------------------------------------------------------------------------------------------- |
| OPENAI_API_KEYS               | array | OpenAi的 `Api_Key，以字符串列表方式填入    | ['']                           |                                                                                                    |
| CHAT_HISTORY_MAX_TOKENS       | int   | 聊天记录最大token数                        | 2048                           |                                                                                                    |
| CHAT_MAX_SUMMARY_TOKENS       | int   | 聊天记录总结最大token数                    | 512                            |                                                                                                    |
| CHAT_MEMORY_MAX_LENGTH        | int   | 聊天记忆最大条数                           | 12                             | 超出此长度后会进行记忆总结并删除更早的记录                                                         |
| CHAT_MEMORY_SHORT_LENGTH      | int   | 短期聊天记忆参考条数                       | 8                              |                                                                                                    |
| CHAT_MODEL                    | str   | 聊天生成的语言模型                         | text-davinci-003               |                                                                                                    |
| CHAT_FREQUENCY_PENALTY        | float | 聊天频率重复惩罚                           | 0.4                            |                                                                                                    |
| CHAT_PRESENCE_PENALTY         | float | 聊天主题重复惩罚                           | 0.6                            |                                                                                                    |
| CHAT_TEMPERATURE              | float | 聊天生成温度: 越高越随机                   | 0.6                            |                                                                                                    |
| CHAT_TOP_P                    | float | 聊天信息采样率                             | 1                              |                                                                                                    |
| IGNORE_PREFIX                 | str   | 忽略前置修饰：添加此修饰的聊天信息将被忽略 | #                              |                                                                                                    |
| REPLY_MAX_TOKENS              | int   | 生成回复的最大token数                      | 1024                           |                                                                                                    |
| REQ_MAX_TOKENS                | int   | 发起请求的最大token数（即请求+回复）       | 2048                           |                                                                                                    |
| USER_MEMORY_SUMMARY_THRESHOLD | int   | 用户聊天印象总结触发阈值                   | 12                             | 越小触发越频繁，推荐10-20                                                                          |
| REPLY_ON_AT                   | bool  | 在被 `@TA` 时回复                          | True                           |                                                                                                    |
| REPLY_ON_NAME_MENTION         | bool  | 在被 `提及` 时回复                         | True                           | `提及` 即用户发言中含有当前bot人格名                                                               |
| PRESETS                       | dict  | 人格预设集合                               | 略                             | 默认有四个预设，详见生成的配置文件                                                                 |
| NG_DATA_PATH                  | str   | 数据文件目录                               | ./data/naturel_gpt/            | 保存实现数据持久化                                                                                 |
| NG_EXT_PATH                   | str   | 拓展脚本文件目录                           | ./data/naturel_gpt/extensions/ | 保存用于保存拓展脚本                                                                               |
| NG_EXT_LOAD_LIST              | str   | 加载拓展列表                               |                                | 只有在此列表中的拓展会被bot使用                                                                    |
| ADMIN_USERID                  | array | 管理员id，以字符串列表方式填入             | ['']                           | 只有管理员可删除预设                                                                               |
| FORBIDDEN_USERS               | array | 黑名单用户id，以字符串列表方式填入         | ['']                           | 黑名单中的用户消息不会被记录和响应设                                                               |
| WORD_FOR_WAKE_UP              | array | 自定义触发词，以字符串列表方式填入         | []                             | 消息中含有列表中的词将唤醒bot                                                                      |
| WORD_FOR_FORBIDDEN            | array | 自定义禁止触发词，以字符串列表方式填入     | []                             | 消息中含有列表中的词将呗拒绝唤醒bot（优先级高于触发词）                                            |
| RANDOM_CHAT_PROBABILITY       | float | 随机触发聊天概率，设为0禁用                | 0                              | 调整范围[0~1]，设置过高会大量消耗token                                                             |
| NG_MSG_PRIORITY               | int   | 消息响应优先级                             | 10                             | 大于1，数值越大优先级越低                                                                          |
| NG_BLOCK_OTHERS               | bool  | 是否拦截其它插件的响应                     | False                          | 开启后可能导致优先级低于本插件的其他插件不响应                                                     |
| NG_ENABLE_EXT                 | bool  | 是否启用聊天自定义拓展                     | True                           | 开启后bot可使用拓展功能，但会额外消耗token（取决于拓展描述复杂度，如果没有安装任何拓展请务必关闭） |
| NG_MAX_RESPONSE_PER_MSG       | int   | 每条消息最大回复次数                       | 5                              | 限制bot针对每条信息最大回复次数，避免封禁                                                          |
| NG_ENABLE_MSG_SPLIT           | bool  | 是否允许消息分割发送                       | True                           | 如果允许，bot有可能会在一次回复中发送多条消息                                                      |
| \_\_DEBUG\_\_                 | bool  | 是否开启DEBUG输出                          | False                          | 开启可查看prompt模板输出                                                                           |

</code> </pre> </details>

## 🪄 指令说明

### 基本命令——"rg"(需要加上在NoneBot中设定的指令前缀)

- 别称: "人格"、"人格设定"、"identity"
- 功能: 查看当前可用人格预设列表和基本的插件帮助
- (*) 管理员帮助命令——"rg admin"

### 完整命令列表/示例

<details> <summary>🔍点击展开查看完整命令和示例</summary> <pre> <code>

- 切换人格——"rg 设定 <-all>"
  + 别称: set
  + 功能: 用于切换当前bot人格
  + 使用示例: `rg set 白羽` (切换当前人格至白羽) | `rg set 白羽 -all` (切换并应用到所有会话)
- 查询人格——"rg 查询"
  + 别称: query
  + 功能: 用于查询bot人格预设信息
  + 使用示例: `rg query 白羽` (查询白羽的人格预设)
- 更新人格——"rg 更新"
  + 别称: update
  + 功能: 用于 更新/修改 指定bot人格预设
  + 使用示例: `rg update 白羽 白羽是一只可爱的喵星人...` (修改白羽的人格预设信息)
- 添加人格——"rg 添加"
  + 别称: new
  + 功能: 用于添加指定bot人格预设
  + 使用示例: `rg new 白羽 白羽是一只可爱的喵星人...` (新增名为"白羽"的人格预设信息)
- 删除人格——"rg 删除" (仅限bot管理员使用)
  + 别称: del
  + 功能: 用于删除指定人格预设，同时会删除该人格的相关记忆！
  + 使用示例: `rg del 白羽` (删除白羽人格预设)
- 锁定人格——"rg 锁定" (仅限bot管理员使用)
  + 别称: lock
  + 功能: 用于锁定指定人格预设，锁定后非管理员无法修改该预设
  + 使用示例: `rg lock 白羽` (锁定白羽人格预设)
- 解锁人格——"rg 解锁" (仅限bot管理员使用)
  + 别称: unlock
  + 功能: 用于解锁指定人格预设，解锁后允许所有用户修改此预设
  + 使用示例: `rg unlock 白羽` (解锁白羽人格预设)
- 查询拓展——"rg 拓展" (仅限bot管理员使用)
  + 别称: ext
  + 功能: 用于查询当前正常加载的所有拓展信息
  + 使用示例: `rg ext`
- 查询所有会话——"rg 会话" (仅限bot管理员使用)
  + 别称: chats
  + 功能: 用于查询当前所有会话状态
  + 使用示例: `rg chats`
- 开启会话——"rg 开启 <-all>" (仅限bot管理员使用)
  + 别称: on
  + 功能: 用于开启会话，开启后bot会开始按预定程序进行消息回应
  + 使用示例: `rg on` (开启当前会话) | `rg on -all` (开启所有会话)
- 停止会话——"rg 停止 <-all>" (仅限bot管理员使用)
  + 别称: off
  + 功能: 用于停止会话，停止后bot不再响应任何回复(包括记录消息)
  + 使用示例: `rg off` (关闭当前会话) | `rg off -all` (关闭所有会话)
- 重置会话——"rg 重置 [预设名]" (仅限bot管理员使用)
  + 别称: reset
  + 功能: 用于重置当前会话bot人格，包括当前人格的记忆和聊天记录等 (注: 不可撤回！)
  + 使用示例: `rg reset -all` (重置当前会话中的所有人格记忆) | `rg reset 白羽` (重置当前会话中的所有人格记忆)

</code> </pre> </details>


## 🤖 行为逻辑QA

<details> <summary>🔍点击展开查看行为逻辑QA</summary> <pre> <code>

Q: 如何区分会话？

A: 根据群组(群聊场景)、私聊(个人)区分会话，即同一群组内共享一个会话，私聊窗口独占一个会话；不同人格的会话和记忆完全独立

---

Q: TA是如何产生回复的？

A: TA会根据 对话上下文(即最近几条聊天记录 不论是否与TA相关)、过往记忆(过去聊天记录的总结)、发起 `@`或 `提及`的用户印象(根据与该用户的聊天记录总结) 生成prompt模板，然后通过 OpenAi 的接口产生对应的回复发送，并且把产生的回复再填加入相应的聊天记录中

---

Q: TA如何记忆用户印象？

A: TA根据用户的id(通常是qq号)的 对TA发起 `@`或 `提及`的聊天记录、响应和历史印象 自动总结产生bot对每个用户的印象，该印象记录与会话无关(即多个会话共享)，但各个人格之间信息相互独立

---

Q: 插件如何实现记录持久化保存？

A: 由于本项目的记忆保存与人格预设存在一定耦合，故使用了pickle直接对程序中使用的数据信息进行序列化后保存为本地文件，然后在程序启动的时候使用pickle加载，这样做的好处是代码实现简便，但由于运行过程数据信息几乎都保存在内存中，如果您的bot活跃用户过多(>1k)、或者人格预设过多(>100)，可能会造成一定的性能负担，敬请见谅！

---

Q: 为什么我在编辑了配置文件中的人格预设信息后重载插件，编辑没有生效？

A: 由于用户数据信息与人格预设信息高度绑定，如果已经生成过pickle文件后程序不会再响应配置文件中人格预设的修改，而是会直接读取已有的pickle文件中的信息，您可以尝试使用 `!rg` 指令根据响应提示直接进行编辑，或者直接删除数据目录中的 `.pkl` 文件(注意：会造成bot记忆丢失)后重载程序重新生成

</code> </pre> </details>

## 🧩 自定义拓展

> 自定义拓展指的是本插件所提供的一个拓展接口，支持加载其它自定义脚本提供的功能，并且提供一套引导流程来 `教会` Bot使用这个功能，从而在bot在与用户通过自然语言聊天时能够根据场景情况主动调用对应的拓展功能

- 拓展模块存放目录(默认): `./data/naturel_gpt/extensions/` (启动加载一次本插件会自动创建)
- 注意：启用拓展后会自动在 nonebot 根目录下创建一个名为 `ext_cache` 的文件夹，该文件夹用于暂存加载的拓展包，请不要 存入/删除 其中的文件！否则可能导致 文件被误删/插件运行出错！

### 使用自定义拓展

> 你可以使用任意来源于本仓库 `/extensions/` 目录下的拓展，也可使用其它用户自行编写的拓展，但是请注意仅从你信任的来源获取，否则可能包含危险程序！

1. 生成拓展模块存放目录(启动一次插件)
2. 将你需要安装的拓展 (通常是 `ext_xxx.py`) 放入拓展模块存放目录(默认 `./data/naturel_gpt/extensions/`)
3. 在本插件的配置文件中正确填写以下内容( `#` 号 后内容为注释)

```yaml
    NG_EXT_LOAD_LIST:
    - EXT_NAME: ext_random  # 拓展文件名 (不含'.py')
      IS_ACTIVE: true   # 是否启用
      EXT_CONFIG: {}  # 拓展配置 如该拓展插件无要求可为空
    - ... # 可填写多项
```

4. 重新加载本插件自动加载拓展

### 官方拓展列表

#### > 随机数生成器

- 拓展文件: ext_random.py
- 说明: 一个示例拓展，用于引导bot调用并生成随机数

#### > 发送随机二次元图片

- 拓展文件: ext_random_pic.py
- 说明: 调用 `api.ixiaowai.cn` 的接口获取一张二次元图片并发送

#### > 发送表情包

- 拓展文件: ext_emoticon.py
- 说明: 调用 `alapi` 接口，搜索指定关键字(由bot自主决定)的表情包并发送
- 配置项: - token*: 平台 token (需自行申请)

#### > 发送语音消息（测试中）

- 拓展文件: ext_voice.py
- 说明: 调用语音生成接口(需自行搭建)

### 编写自定义拓展

> 自行编写拓展需要具有一定的 Python 编程基础，如果您有相关能力可直接参考本仓库 `/extensions/` 目录下的拓展进行编写(非常简单！) 自行编写的拓展安装流程与上述相同
> 注意：该功能尚处于早期阶段，拓展编写在未来版本有可能随时变化！

✨ 如果您想分析您自行开发的拓展，可向本仓库提交pr，将您的拓展命名为 `share_ext_xxx.py`('xxx'部分可自行命名，请勿与已存在的拓展名冲突) 并上传至本仓库的 `/share_exts/` 目录下，欢迎您成为本项目的贡献者！

#### 基本的拓展模块模板
<details> <summary>🔍点击查看拓展模块编写模板</summary> <pre><code>

```python
from .Extension import Extension

# 拓展的配置信息，用于ai理解拓展的功能 *必填*
ext_config:dict = {
    "name": "ExtensionName",   # 拓展名称，用于标识拓展，尽量简短
    "arguments": {  
        "arg1": "int",   # 填写期望的参数类型，尽量使用简单类型，便于ai理解含义使用
        "arg2": "int",   # 注意：实际接收到的参数类型为str(由ai生成)，需要自行转换
    },
    # 拓展的描述信息，用于提示ai理解拓展的功能 *必填* 尽量简短 使用英文更节省token
    "description": "send ... (use eg: /#Send&xxx#/)",
    # 参考词，用于上下文参考使用，为空则每次都会被参考(消耗token)
    "refer_word": ['use extension'],
    # 每次消息回复中最大调用次数，不填则默认为99
    "max_call_times_per_msg": 99,
    # 作者信息
    "author": "",
    # 版本
    "version": "v0.0.1"
}

class CustomExtension(Extension):
    async def call(self, arg_dict: dict) -> dict:
        """ 当拓展被调用时执行的函数 *由拓展自行实现*

        参数:
            arg_dict: dict, 由ai解析的参数字典 {参数名: 参数值}
        """
        custom_config:dict = self.get_custom_config()  # 获取yaml中的配置信息

        ### 在这里处理主要的自定义逻辑

        return {  # 返回的信息将会被发送到会话中
            'text': f"[来自拓展的消息]...", # 文字信息
            'image': f"http://...",  # 图片url
            'voice': f"http://...",  # 语音url
        }

    def __init__(self, custom_config: dict):
        super().__init__(ext_config.copy(), custom_config)
```

</code></pre> </details>

## 🎢 更新日志

## [2023/2/24] v1.3.5

- 修复了因唤醒词设置类型不规范问题导致偶发错误的问题
- 修复第一次启动自动创建数据文件夹目录失败的问题
- 为更换人格预设增加了批量操作 `-all` 指令（限管理员可用）
- 增加了 `chats` 指令，用于查看所有会话状态
- 优化 README.md 文档
- 增加了是否开启消息切分多条发送的配置项（默认开启）
- 增加了黑名单功能，在黑名单中的用户消息不会被记录和响应

## [2023/2/20] v1.3.3

- 优化了不启用拓展模块时bot的回复质量，减少虚空调用拓展的情况
- 优化对话生成prompt，增强了bot发送多段聊天的能力
- 增加了bot感知当前时间的能力
- 从bot的发言记录中将错误的调用指令去除，避免bot重复学习错误的拓展指令使用
- 将大多数文本生成的prompt改为英文描述，尽量降低部分tokens消耗
- 新增了一个表情包拓展模块

## [2023/2/19] v1.3.2

- 修复了yaml配置中设置禁用拓展不生效的问题
- 持续优化对话生成prompt，提高bot理解使用拓展的能力
- 为 开启/关闭 会话的指令增加了 `-all` 选项，可一次性 开启/关闭 所有会话

## [2023/2/19] v1.3.1

- 优化拓展模块的参数传递
- 修改了一些拓展插件提示，更便于bot理解拓展使用方式

## [2023/2/18] v1.3.0

- *拓展支持：增加了插件拓展支持(插件的插件？)，支持使用自然语言自定义拓展更多功能，提供了两个示例拓展
- 多处细节优化

## [2023/2/16] v1.2.0

> 本次更新增加了异步能力，功能可能尚不稳定，如要继续使用旧版的记忆文件请做好备份

- 异步更新：bot的回复生成开始支持异步请求，提高了消息处理速度
- 移除双回车符的停用词限制，优化了ai对长文本的输出能力
- 优化错误输出，在api请求出错时会在控制台显示错误信息以供排查
- 优化记忆逻辑，bot在请求文本错误时不会把错误提示信息一并存入记忆

### [2023/2/12] v1.1.6

- 增加切换会话是否启用的开关功能
- 增加了记忆重置功能，可指定重置当前会话的所有人格或特定人格
- 消息拦截响应、消息处理优先级支持自定义配置
- 简化帮助命令输出，分离管理员命令的帮助信息到 `rg admin` 中

### [2023/2/9] v1.1.5

- 修复未创建对话前调用bot指令报错的问题
- 增加自定义触发词唤醒的功能
- 增加自定义屏蔽词拒绝回复的功能
- 增加bot随机参与聊天功能，可选择启用
- 优化了手动 `@bot` 时的信息的聊天prompt生成逻辑，使bot回复更具有指向性
- 优化配置文件管理逻辑，更新后可继续沿用原配置文件，程序加载后会自动补充更新配置文件字段

### [2023/2/6] v1.1.4

> 注意：本次更新需要删除原bot记忆文件重新生成(即./data/naturel_gpt文件夹)，否则可能产生无法预计的错误

- 修复了bot记忆串线的问题(多个群组同时使用场景下记忆混乱)
- 优化bot生成记忆和印象摘要的逻辑，提高了bot回复的速度
- 优化了控制台输出

### [2023/2/5] v1.1.2

- 新增了人格预设的 锁定/解锁 功能，锁定后非管理员无法编辑该预设
- 更新README文档
- 优化rg命令显示格式
- 微调了 `config.py` 中的一些默认参数
- 修复本插件拦截其它插件响应的问题，降低了本插件的响应优先级
- 更新了交流群信息(见本文档开头)，欢迎各路大佬加入互相学习、一同探讨更新方向、分享更多玩法等

### [2023/2/2] v1.1.1

- 修复查询人格错误的问题

### [2023/2/2] v1.1.0

> 注意：本次更新需要删除原bot记忆文件重新生成(即./data/naturel_gpt文件夹)，否则可能产生无法预计的错误

- 新增了预设编辑功能
- 新增自定义管理员id功能，管理员可以删除预设 / 修改锁定的预设
- 增加debug开关控制生成文本时的控制台输出（默认关闭）
