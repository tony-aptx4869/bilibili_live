![hero](img/hero.png)

# Bilibili Live

**[This App on AWTRIX Hub](https://awtrix.de/script/LzgkgCuRbhs5)**

AWTRIX NG / TC001（ESP32）Berry 小应用：显示 Bilibili 直播状态、直播间在线人数与粉丝数。

## 亮点

- 直播中显示直播图标 + 在线人数；未直播显示普通图标 + 粉丝数。
- 粉丝模式：开启 `Follower Mode` 并填写 `UID`，只显示粉丝数。
- 直播中支持 App 内双页：`Show Follower Count` 开启时按 70% / 30% 分配「直播页 / 粉丝页」；关闭时只显示直播页。
- 数字无分隔符，自动使用 `K / M / G / T` 整数单位，如 `999M`。
- 校验 API 返回的 `code` 字段（`0` 成功）；失败后每 5 秒重试，累计 3 次失败以橙色显示 `Check ID`。
- 字体颜色继承系统 `Text Color`，滚动与翻页过渡使用系统设置。
- 单次完整 HTTP 请求 + 正则提取，不在 `draw()` 分配内存，适合小内存设备。

## 安装

您只需点击**发送到AWTRIX**按钮。

## 配置

在 **Apps** 页找到 `Bilibili Live`，点齿轮修改：

| 配置项 | 默认值 | 说明 |
|---|---|---|
| `Follower Mode` | `false` | 只显示粉丝数，使用下方 UID 查询 |
| `UID` | `9617619` | `space.bilibili.com/<uid>` 中的数字；开启 `Follower Mode` 时生效 |
| `Room ID` | `6` | `live.bilibili.com/<roomid>` 中的数字，必改 |
| `Normal Icon` | `bilibiliblink` | 未直播时的图标 ID |
| `Streaming Icon` | `bilibililive` | 直播时的图标 ID |
| `Show Follower Count` | `true` | 直播时是否在直播页后显示粉丝页 |
| `Refresh` | `1` min | 数据刷新间隔 |
| `Duration` | `10` s | App 显示时长；`0` = 使用系统每 App 时长 |

保存配置会重启应用。两个图标通过 `@icons` 声明；若未安装，用 Web UI 的图标管理补装同名字体图标。
