# shiertier_i18n
中文 | [english](README_en.md)

## 简介

`shiertier_i18n` 是一个简单的 Python 国际化 (i18n) 库，旨在帮助开发者轻松地将应用程序本地化为不同的语言。该库基于 `gettext` 模块，支持从环境变量中自动检测语言和本地化目录，并提供了一个简单的接口来翻译字符串。

## 安装

你可以通过 `pip` 安装 `shiertier_i18n`：

```bash
pip install shiertier_i18n
```

## 使用方法

### 初始化

首先，你需要初始化 `I18n` 类：

```python
from shiertier_i18n import I18n

# 使用默认语言和本地化目录
i18n = I18n()

# 或者指定语言和本地化目录
i18n = I18n(language_str='zh_CN', locales_dir='/path/to/locales')
```

### 翻译字符串

你可以使用 `translate` 方法来翻译字符串：

```python
translated_str = i18n.translate("Hello, world!")
print(translated_str)
```

你还可以传递一个字典来替换翻译后的字符串中的占位符：

```python
translated_str = i18n.translate("Hello, $$name$$!", replace_dict={'$$name$$': 'Alice'})
print(translated_str)
```

### 快捷方式

如果你只需要快速翻译一个字符串，可以使用 `easy_i18n` 快捷方式：

```python
from shiertier_i18n import easy_i18n

translated_str = easy_i18n("Hello, world!")
print(translated_str)
```

## 配置

### 语言

默认情况下，`I18n` 类会从环境变量 `LANGUAGE` 中获取语言设置。如果没有设置 `LANGUAGE`，则默认使用 `en_US`。

你也可以在初始化 `I18n` 类时指定语言：

```python
i18n = I18n(language_str='zh_CN')
```

### 本地化目录

默认情况下，`I18n` 类会从环境变量 `SHIERTIER_LOCALES_DIR` 中获取本地化目录。如果没有设置 `SHIERTIER_LOCALES_DIR`，则默认使用用户主目录下的 `.shiertier/locales` 目录。

你也可以在初始化 `I18n` 类时指定本地化目录：

```python
i18n = I18n(locales_dir='/path/to/locales')
```

## 依赖

- `gettext`

## 许可证

本项目基于 MIT 许可证发布。详情请参阅 [LICENSE](LICENSE) 文件。