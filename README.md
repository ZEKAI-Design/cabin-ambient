# Cabin Ambient

为 2019 BMW X5 xDrive40i（G05、iDrive 7）做的中控 App。通过车上已有的 IterioDev Comfort 服务应用静态、呼吸、彩虹及自定义循环。车主已在实车确认颜色和灯效控制正常。

## 调色和预设

在 **Color** 左侧选灯效，再选 **Choose zones**。右侧先点区域，再点某一条灯带，或点整组。中间色圈或 **Edit code** 只修改选中的目标，右侧每行显示该目标已有的颜色。**Whole car** 编辑全车统一色，回到 **Choose zones** 时仍可继续编辑各区。**Presets** 保存整套场景，包括各区配色。G05 参考灯位和 Comfort 报回的分区分别保存。

## 实车控制

在原厂 iDrive 菜单打开氛围灯。如 Ambient Light 开启了按驾驶模式改色，先在该 App 关闭此选项。进入 **Color → Static → Choose zones → Read car zones**。选择 Comfort 报告的分区，设置 RGB 后点 **Apply to car**。**Settings accepted** 表示 Comfort 收到了配置，请观察实体灯带确认实际变化。点 **Use BMW colours** 会让 Comfort 把配色交回原厂系统。脚窝灯正常可选，不显示误报的故障数。

动态灯效使用 **Start on car** 启动。当前效果、颜色和分区会保存在车机；应用随车机后台启动，在 Comfort 报告车内氛围灯重新可用时自动续播，不需要再次打开 App。车辆休眠或车内灯光暂不可用时暂停发送更新。更改灯效、颜色或分区会停止当前续播。手动点 **Stop car effect** 会停止并清除自动续播状态，同时尝试恢复启动前的配色。恢复失败时可在 **Static** 中点 **Use BMW colours**。静态颜色由 Comfort 保存并按其车辆状态恢复。

## G05 灯位

| 分组 | 参考位置 |
| --- | --- |
| Dashboard | 按车主描述显示上灯带、下灯带 |
| Centre console | 中央通道左右饰条 |
| Doors | 四门各自的轮廓、储物格和内拉手灯 |
| Footwells | 驾驶与副驾驶脚窝 |
| Seatbacks | 两张前座靠背侧面及下部的灯 |
| Sky Lounge | 全景天窗星空顶（407），预览按整片天窗调色 |

预览布局参考 BMW《G05 General Vehicle Electronics》第 2.3.1 和第 11 章。BMW 培训图的灯光部件位置用于参考。仪表台按车内可见灯带显示，星空顶左右各三颗 LED 模组在预览中合为一组。实际分区可查看 Comfort 的报告，灯带能否独立控制还需实车验证。Bowers & Wilkins（6F1）扬声器罩灯由音响模块另行控制。车窗按钮、阅读灯和车外迎宾灯属于另外的照明功能。 [BMW 技术培训资料](https://www.scribd.com/document/520740351/03-G05-General-Vehicle-Electronics) · [BMW 2019 X5 配置表](https://www.press.bmwgroup.com/canada/article/attachment/T0289548EN/432931)

## 从 GitHub 安装

车机联网后，在 **MGU Store → Settings → Add source** 输入 `ZEKAI-Design/cabin-ambient`，选择 **Releases**。回到 **Store** 安装 **Cabin Ambient**。已安装的版本可以从 **Installed** 更新。

## 构建与发布格式

在仓库根目录运行 `python3 kit/tools/build.py --omit-sdk zekai_cabin_chroma`。车机在安装时使用自身的 OAP SDK。保留 App 的内部 ID，使已安装的版本可以升级。

界面构建工具和运行时来自 [idrive7-apps](https://github.com/cauliflowermossgrape/idrive7-apps)，许可见 `LICENSE-IDRIVE7-APP-KIT`。分区检测读取已安装 Comfort 服务连接时发出的状态消息。
