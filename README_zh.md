# shiertier_i18n

## 简介

`shiertier_i18n` 是一个简单的 Python 国际化（i18n）库，旨在帮助开发者轻松地将他们的应用程序本地化成不同语言。该库基于 `gettext` 模块，支持通过环境变量自动检测语言和本地化目录，并提供一个简单的接口来翻译字符串。

## 安装

你可以通过以下方式安装 `shiertier_i18n`：

```bash
pip install git+https://github.com/shiertier-utils/shiertier_i18n.git
```

请注意，项目仍在开发中。

## 使用

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

你还可以传递一个字典，用于替换翻译字符串中的占位符：

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

默认情况下，`I18n` 类将从 `LANGUAGE` 环境变量中获取语言设置。如果 `LANGUAGE` 没有设置，它将默认为 `en_US`。

你也可以在初始化 `I18n` 类时指定语言：

```python
i18n = I18n(language_str='zh_CN')
```

### 本地化目录

默认情况下，`I18n` 类将从 `SHIERTIER_LOCALES_DIR` 环境变量中获取本地化目录。如果 `SHIERTIER_LOCALES_DIR` 没有设置，它将默认为用户主目录下的 `.shiertier/locales` 目录。

你也可以在初始化 `I18n` 类时指定本地化目录：

```python
i18n = I18n(locales_dir='/path/to/locales')
```

## 依赖

- `gettext`

## 许可证

本项目采用 MIT 许可证，详情请见 [LICENSE](LICENSE) 文件。