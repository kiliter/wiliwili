# Windows 退格返回键定制版

基于 wiliwili v1.6.0（上游提交 `88e5876`），面向 Windows x64，使用 D3D11 渲染。

## 使用方式

解压完整压缩包，运行 `wiliwili.exe`。资源和 mpv 已按上游构建方式内嵌。

- 普通页面：按 Backspace（退格键）返回，Esc 不再触发页面返回。
- 搜索等文本输入框：Backspace 删除文字，Esc 取消输入，Enter 确认。
- 手柄返回键、鼠标右键，以及 A/B 互换设置继续使用原有逻辑。
- 使用键盘图标主题时，内置字体的返回提示图标仍可能显示 Esc；页面实际返回键为 Backspace。

## 构建说明

专用流程为 `.github/workflows/windows-backspace.yaml`，支持手动触发和相关文件更新后自动构建。
流程检出固定版本的 Borealis 子模块，校验并应用 `patches/windows-backspace.patch`，随后执行 Windows 编译和产物上传。
原有多平台流程的 Windows 构建同样应用该补丁；其他平台保留原有返回键行为。

## 验证边界

GitHub Actions 编译成功只代表构建通过。页面返回、搜索删字、中文输入法、A/B 互换、鼠标右键和视频全屏返回，需要在 Windows 实机检查。

参考：[上游自定义 PC 端快捷键说明](https://github.com/xfangfang/wiliwili/wiki#自定义pc端快捷键)。
