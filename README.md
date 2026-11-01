# CHILocalization-4-RecoLove
『レコラヴ ブルーオーシャン\ゴールドビーチ』中文化方案

> 非官方简体中文汉化补丁，仅用于技术交流，请支持正版。

## 项目简介

本项目为 PS Vita 游戏 **《レコラヴ Gold Beach》** 与
**《レコラヴ Blue Ocean》** 的简体中文汉化整合包。

| 项目 | Gold Beach | Blue Ocean |
| --- | --- | --- |
| 日文名 | レコラヴ Gold Beach | レコラヴ Blue Ocean |
| 游戏编号 | PCSG00782 | PCSG00781 |
| 日版版本 | 1.07 | 1.07 |
| 发布格式 | xdelta | xdelta |
| 主文件补丁 | 6 | 6 |
| DLC 补丁 | 289 | 184 |
| 补丁总数 | 295 | 190 |

本发布物不包含完整游戏本体、官方升级补丁或 DLC 安装包。

## 汉化范围

两作均已覆盖：

- 主线剧情、角色剧情、消息与选择支
- 系统菜单、提示、教程、保存与读取界面
- 场景、地点、活动、服装、道具和任务说明
- 简体中文字库、缺字扩展与角色名字栏显示
- UI 贴图、菜单图片及必要的图像润色
- 已收录 DLC 的剧情脚本、表项、标题、说明和 UI
- 必要的 DLC 文件大小元数据

### Gold Beach

- 主线与角色剧情完整汉化
- 系统、菜单、提示和固定 UI 文本汉化
- 字库、角色名字栏和 UI 图片处理
- 当前工程收录的 110 个 DLC 内容目录已处理
- DLC 剧情、服装与道具名称、活动标题、说明和必要元数据已处理

### Blue Ocean

- 主线与角色剧情完整汉化
- 系统、菜单、提示和固定 UI 文本汉化
- 字库、角色名字栏和 UI 图片处理
- 4 个剧情 DLC 的完整脚本已处理
- 当前工程收录的 101 个 DLC 内容目录已处理
- 服装、道具、活动、动作与相关说明已处理
## 预览效果

<img width="960" height="544" alt="2026-08-24-201656" src="https://github.com/user-attachments/assets/2bc569cd-d7fa-4272-9302-b60e1d76e8d6" />
<img width="960" height="544" alt="2026-08-23-005713" src="https://github.com/user-attachments/assets/c2cde04d-57d1-46ae-bc1b-375aedc91e0b" />
<img width="960" height="544" alt="2026-10-28-102137" src="https://github.com/user-attachments/assets/c1bf7677-0628-4093-9e60-b1870d7e065d" />
<img width="960" height="544" alt="2026-10-25-193139" src="https://github.com/user-attachments/assets/49b1e545-8474-4b4f-bc92-8954f73e1cc0" />
<img width="960" height="544" alt="2026-10-25-194331" src="https://github.com/user-attachments/assets/f5070a32-99cf-46a0-b945-3f3202b5b720" />

## 兼容性

- 仅支持日版 **PCSG00782 1.07** 与 **PCSG00781 1.07**
- PS Vita 需安装可用的 **rePatch** 插件
- 不支持港版、美版或其他游戏编号
- Vita3K 模拟器未测试
- 使用错误的游戏版本、错误的基础文件或不完整的 DLC
  可能导致补丁校验失败、黑屏、加载卡死或崩溃

## 目录结构

```text
CHILocalization-4-RecoLove/
├─ README.md
├─ PCSG00781/
│  ├─ patches/
│  │  ├─ MAIN/
│  │  └─ DLC/
│  ├─ patch_manifest.tsv
│  ├─ stock_manifest.tsv
│  └─ release_report.json
└─ PCSG00782/
   ├─ patches/
   │  ├─ MAIN/
   │  └─ DLC/
   ├─ patch_manifest.tsv
   ├─ stock_manifest.tsv
   └─ release_report.json
```

## 使用 xdelta 补丁

本发布物不附带 `xdelta3.exe`。请自行准备

### 一、准备原版文件

1. 安装对应日版游戏，并升级至官方 **1.07**。
2. 安装准备使用的 DLC。
3. PS Vita 安装可用的 rePatch 插件。
4. 自行获取对应的合法解密文件。

需要准备：

```text
ux0:app/PCSG00781/       或   ux0:app/PCSG00782/
ux0:patch/PCSG00781/     或   ux0:patch/PCSG00782/
ux0:addcont/PCSG00781/   或   ux0:addcont/PCSG00782/
```

`Common.cpk` 来自 1.00 本体，`eboot.bin`、`Script.cpk`、
`Table.cpk` 和 `UI.cpk` 来自 1.07 升级补丁。

### 二、应用主文件补丁

进入对应的 `PCSG00781` 或 `PCSG00782` 目录。使用
`patch_manifest.tsv` 中的 `stock_relative` 选择原版文件，
应用 `patches/MAIN/` 中的补丁，并按 `target_relative` 放置输出：

```text
xdelta3 -d -f -s <原版文件> <补丁文件> <输出文件>
```

主文件包括：

| 补丁 | 用途 |
| --- | --- |
| `eboot.bin.xdelta` | 主程序与界面文字 |
| `media_cpk_Common.cpk.xdelta` | 字库与公共资源 |
| `media_cpk_Script.cpk.xdelta` | 主线、角色剧情与选择支 |
| `media_cpk_Table.cpk.xdelta` | 系统、服装、道具与说明 |
| `media_cpk_UI.cpk.xdelta` | UI 文本与图片 |
| `media_data_04_sprite_01_logo_01log_texture.pac.xdelta` | 启动提示图 |

输出文件最终放入：

```text
ux0:rePatch/PCSG00781/
ux0:rePatch/PCSG00782/
```

### 三、应用 DLC 补丁

每个 DLC 对应一个内容 ID，补丁位于 `patches/DLC/<内容ID>/`。

1. 找到该 DLC 合法安装后导出的完整解密目录。
2. 保留其原有完整文件结构。
3. 按 `patch_manifest.tsv` 对 `media/cpk/` 和
   `sce_pfs/` 中列出的文件应用补丁。
4. 将输出文件放入对应的
   `ux0:reAddcont/<游戏编号>/<内容ID>/`。
5. 未列出的语音、模型、动画、UI 和其他资源必须保持原版。

注意：

- 只替换 `patch_manifest.tsv` 明确列出的文件。
- 未安装的 DLC 无需处理。
- 已安装的 DLC 必须保留完整原版资源。
- 不要把补丁应用到旧的汉化文件或其他版本的文件上。

## 校验

- `patch_manifest.tsv` 记录每个补丁、基准文件和目标文件的
  大小及完整 SHA256。
- `stock_manifest.tsv` 记录生成补丁时使用的原版文件 SHA256。
- 所有 xdelta 均在发布前执行过“原版 + 补丁 → 目标文件”回放验证。
- 若出现 `source checksum mismatch`，说明原版文件不匹配，
  请重新确认游戏版本和解密导出结果。

## 已知限制

- 受 PS Vita 字库容量与寻址上限影响，个别生僻字会采用
  当前字库中可用的简体字形或对应原字显示。
- 角色名表保留原版读音和索引结构，名字栏在显示层使用中文译名。
- Vita3K 未测试，不保证 3D 演出、模型和贴图的模拟器兼容性。
- 本补丁仅适用于日版 1.07。

## 故障排查

### 补丁提示源文件不一致

确认：

- 游戏编号正确；
- 本体与官方升级补丁版本正确；
- 使用的是 `OpenDecrypted` 导出的解密文件；
- `Common.cpk` 来自 1.00 本体；
- 其他主文件来自 1.07 升级补丁；
- 没有把补丁应用到旧汉化文件。

### 启动后仍显示日文

检查：

- rePatch 插件是否启用；
- 文件是否位于正确的 `ux0:rePatch/<游戏编号>/`；
- 是否按 `target_relative` 放置了文件；
- 是否误把文件覆盖到 `ux0:patch/`。

### DLC 加载或进入剧情时卡死

检查：

- 对应 DLC 是否已安装；
- 原版 DLC 解密目录是否完整；
- 是否只替换了清单列出的文件；
- `media/sound/voice/`、模型、动画等资源是否被误删或漏放；
- DLC 内容 ID 是否与目录一致。

并记录：

- 所在场景；
- 触发角色；
- 选择支路径；
- 是否安装 DLC；
- 截图或短录像。

## 致谢

- 感谢 [gothgirllover67/recolovetr](https://github.com/gothgirllover67/recolovetr)
  的英化工程提供参考与完善思路；
- 感谢 [marco-calautti/DeltaPatcher](https://github.com/marco-calautti/DeltaPatcher)；
- 感谢 [jmacd/xdelta](https://github.com/jmacd/xdelta)；
- 感谢所有参与测试、校对与润色的朋友。

## 免责声明

- 本项目为非官方汉化，仅供技术交流；
- 请于下载后 24 小时内删除；
- 本项目与游戏权利方无任何关联，也无任何获利关系；
- 仅包含汉化所必需的改动文件，仅包含游戏汉化所需的最小文件；
- 补丁只能用于使用者本人合法持有的游戏及解密副本；
- 请勿用于商业用途、二次售卖或非法传播；
- 请支持正版游戏。
