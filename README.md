# Cabin Ambient

为 2019 BMW X5 xDrive40i（G05、iDrive 7）开发的氛围灯 App，需要车上已安装 IterioDev Comfort。

## 车机操作

1. 在原厂 iDrive 菜单打开氛围灯。如果 Ambient Light 开启了 Drive Mode Colours，请先关闭。
2. 在 **Color** 左栏选择 Comfort 实际报告的分区或灯条，例如 **Dashboard light strip**、**Dashboard trim lights** 或 **Seatback / pillar lights**。
3. 在中栏选 **Static**、**Breathe**、**Rainbow** 或 **Colour loop**，在右栏用色盘或 HEX/RGB 设定颜色，再点 **Apply to this zone**。各区独立运行，例如 Dash Line 可以保持静态紫色，同时 Dash Decor 循环多种颜色。
4. 要让整车使用统一设置，选 **Whole car · all lights**，再点 **Apply same effect to all**。这会替换当前场景里的逐区设置。之后仍可对任何分区单独应用效果。
5. 点 **Save entire car as preset** 读取 Comfort 当前生效的分区颜色，并保存 Cabin Ambient 正在运行的灯效。已有的逐区静态颜色也可以直接保存。可保存八套，在 **Presets** 中用 **Apply entire preset** 恢复整套配置，也可编辑或删除。

要让部分区域同步，点左栏 **Multi-select**，勾选要一起调整的区域。设好颜色、灯效和周期后点 **Apply to N selected**。这批区域共用同一个灯效起点，其他区域继续原有灯效。整车预设会保留同步关系。

**Rainbow** 和 **Colour loop** 都支持 **Smooth fade** 和 **Direct switch**。周期最长 300 秒，Colour loop 最多支持 16 种颜色。颜色较多时，最短周期会相应加长。脚窝分区仍会忽略已知的误报标记。

**Rainbow** 从当前 HEX/RGB 颜色开始，循环只改变色相，保留该区所选颜色的饱和度和数值。**Colour value** 随各区的颜色单独保存，同一批多选后应用的区域共用本次设置。灰色、白色和黑色的饱和度为零，在 Rainbow 中会保持原色。

**Door handles & pockets** 是原来的 **Doors Other**，包括 Comfort 在这一分区检测到的门把手和储物槽灯。被识别为车顶氛围灯的模块可从 **Roof ambient lights** 调整。

每区的 **Brightness** 可调到 150%，100% 以上会提高 RGB 的中间通道值。**Max output · all** 会让当前由 Comfort 控制的灯具使用 100% 的固定输出。关闭此选项或点 **Use BMW colours** 会恢复之前的灯具输出设定。

已应用场景保存在车机，退出界面后后台继续运行，车机唤醒且 Comfort 可用后恢复。**Use BMW colours** 把灯光控制交回原厂，同时保留 App 中的场景供之后重新应用。

## 从 GitHub 更新

已添加 `ZEKAI-Design/cabin-ambient` Releases 来源的车机可从 **MGU Store → Settings → Check now → Installed → Cabin Ambient → Update** 更新。首次添加来源时，在 **Settings → Add source** 输入仓库名并选择 **Releases**。

界面运行时来自 [idrive7-apps](https://github.com/cauliflowermossgrape/idrive7-apps)。
