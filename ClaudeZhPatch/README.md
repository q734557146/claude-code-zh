# Claude Desktop zh-CN Patch

Windows 版 Claude Desktop / Claude Code 界面汉化补丁源码。

## 适用范围

- 仅针对官方直连 1P 模式。
- 暂不支持 3P 模式。
- 暂不支持第三方中转、第三方服务端、魔改客户端、代理封装版或其它非官方接入方式。
- 本仓库不包含 Anthropic 官方应用文件。

## 仓库内容

```text
.codex-tools/zh-patcher/
  build_dom_preload.py            生成 renderer / DOM 层汉化 preload
  patch_native_menu_locale.py     本地菜单 locale 汉化辅助脚本
  test_settings_translations.py   翻译覆盖检查
  collect_untranslated.py         未翻译文本采集辅助工具
  build_translations.py           翻译映射生成辅助工具
  english_to_chinese.json         DOM 文本翻译映射
  settings_overrides.json         设置页/动态文本覆盖翻译

translations/
  claude-desktop-zh-CN.overrides.json
  zh-CN/root-zh-CN.json
  zh-CN/ion-zh-CN.json
  zh-CN/ion-zh-CN.overrides.json
  zh-CN/statsig/zh-CN.json
```

## 不包含的内容

本源码包刻意不包含：

- 安装器源码
- 安装脚本
- 成品 EXE
- 用户说明 DOCX / TXT
- 官方 app.asar 或其它 Claude 官方文件
- 本地备份文件
- 证书、私钥、抓包工具、日志、截图、缓存

## 开发命令

从仓库根目录运行：

```powershell
python .codex-tools\zh-patcher\test_settings_translations.py
python .codex-tools\zh-patcher\build_dom_preload.py
python .codex-tools\zh-patcher\patch_native_menu_locale.py
```

注意：脚本默认面向本机 Windows 版 Claude Desktop 路径，发布前请根据目标版本自行检查路径和权限逻辑。

## 免责声明

本项目不是 Anthropic 官方项目，仅用于本地界面汉化研究与自用。使用前请自行备份相关文件。