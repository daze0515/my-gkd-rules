# 我的 GKD 自定义规则

个人维护的 GKD 本地订阅规则库，用来补充公共订阅（如 id667）没覆盖的场景。

## 目录结构

- `apps/` 每个应用一个文件，文件名 = 应用包名
  - `com.qq.reader.json5` QQ阅读 - 开屏/热启动广告

## 如何导入 GKD

### 方式一：单个文件订阅（推荐新手）
1. 在 GitHub 上打开某个规则文件（比如 `apps/com.qq.reader.json5`）
2. 点 `Raw` 按钮，复制地址栏链接
3. GKD → 订阅 → 右上角 `+` → 粘贴链接

### 方式二：整仓订阅（推荐进阶）
如果你装了 GKD 官方的订阅转换工具，可以用一个聚合链接订阅整个仓库。

## 如何添加新规则

1. 在 `apps/` 下新建文件，文件名用应用包名（如 `com.tencent.mobileqq.json5`）
2. 按 GKD 订阅规范写规则
3. `git add . && git commit -m "feat: add xxx rule" && git push`

## 规则编写规范

- 优先用稳定 id 做锚点（如 `splash_root`），不要只靠文本匹配
- `matchTime` 不要给太大（10-20秒），防止误触
- `actionMaximum: 1` 防止重复点击
- 关键规则尽量填 `snapshotUrls`，方便以后维护
