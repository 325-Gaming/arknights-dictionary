# 舟语字典

这里存放一些指不定在别的什么地方用得上的妙妙字典。

## 四字舟语词库

这是可以用在[nonebot-plugin-handle](https://github.com/SonodaHanami/nonebot-plugin-handle)的妙妙词库。

`answers_arknights.json` 内存放了四字舟语的词库，词库会~~不~~定期更新。

`answers_arknights.json` 是由程序自动生成的文件，其中的内容不应被手动改动，文件遵守以下格式

```json
[
    {
        "word": "四字舟语",
        "explanation": [
            "四字舟语释义，第一行应该是原始词语",
            "该数组中每个字符串占用一行，不保证以句号结尾"
        ],
        "category": [
            "舟语的分组",
            "总分组和子分组不区分"
        ]
    }
]
```

`pinyin_arknights.json` 内对应存放了四字舟语的拼音，文件遵守以下格式

```json
{
    "明日方舟": ["ming2", "ri4", "fang1", "zhou1"],
    "维什戴尔": ["wei2", "shi2", "dai4", "er3"],
    "目光呆滞": ["mu4", "guang1", "dai1", "zhi4"]
}
```

`pypinyin_diff_validation.py` 用于比对 `pinyin_arknights.json` 与 [pypinyin](https://pypi.org/project/pypinyin/) 库给出的拼音的差异

`pypinyin_diff_whitelist.json` 用于在比对差异时自动跳过某些词语，文件遵守以下格式

```json
{
    "矮脚长桌": "（此处可为空）",
    "八面骰子": "骰子，轻声",
    "半洗孤钻": ""
}
```

特别地，拼音中若存在轻声则无音调。

如果有缺失的舟语，请发issue。若有拼音纠错，请发pr。

## 干员id

干员的唯一id被存放于 `character_id.json` 内，其是由程序自动生成的文件，不应被手动改动。

~~其实我也不知道这个文件有什么用~~

~~其实这个文件确实暂时未被使用~~

## 干员信息

干员的相关信息存放于 `operator.json` 内，由程序自动生成并由人工校对完善 ~~，不应被手动改动~~ 。

其中干员按照 职业（`job`） - 稀有度（`rarity`） - 实装顺序 排序

职业的顺序为 `先锋 近卫 重装 狙击 术师 医疗 辅助 特种`

每个干员的信息遵守以下格式

```json
"予愿安洁莉娜": {
    "id": "char_1015_aglna2",
    "code_name": "予愿安洁莉娜",
    "code_name_en": "Angelina the Mellow Wish",
    "code_name_jp": "予愿安洁莉娜",
    "job": "特种",
    "sub_job": "巡空者",
    "position": "近",
    "rarity": 6,
    "tag": [
        "高空",
        "输出",
        "控场"
    ],
    "is_recruit": false,
    "birthday": {
        "is_undefined": "",
        "month": 5,
        "day": 14
    },
    "pinyin": [
        "yu3",
        "yuan4",
        "an1",
        "jie2",
        "li4",
        "na4"
    ]
}
```

## 活动信息

活动的相关信息存放于 `event` 目录下，包含国服（`cn.json`）、日服（`jp.json`）、国际服（`global.json`），由人工编辑。

其中活动按照 开始时间（`start`） 倒序排序

活动类型为 `rogue_main`、`rogue_monthly`、`sidestory`、`time_limited_event` 其中的一种

每个干员的信息遵守以下格式

```json
"「卫戍协议：盟约」下半": {
    "type": "time_limited_event",
    "start": "2026-03-14 16:00",
    "end": "2026-04-25 04:00"
}
```
