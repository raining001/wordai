# Word AI

一款使用自然语言处理辅助背单词的程序。

通过导入TMX翻译语料库，进行分词、词素分析、单词还原等操作自动生成各种不同语态、情态下的英语填空来进行单词学习。

*PS: 因为版权原因，不提供词典文件和TMX语料文件。需要自行下载导入。业余项目，分享出来供学习和交流，提供有限的技术支持，如有疑问欢迎Issue。*

## 功能特色

* 根据中文填写英文句子中的单词。
* 根据语料库自动生成题目，*拒绝重复*
* 根据艾宾浩斯记忆曲线重复出现需要复习的单词。
* 对于错误单词自动弹出词典，进行学习。
* 支持自定义词库。
* B/S架构，兼容移动端和PC端。




## Examples

### 单词学习

如遇到不会的单词，可以长按空格查看答案。

![练习](doc/word.gif?raw=true)

对于错误单词自动弹出词典以供学习。

![错误单词](doc/error.gif?raw=true)

### 自定义单词列表

文本框输入单词列表。一行一个，自动提示词典查询结果，以检查是否添加正确。

![单词列表](doc/newlist.gif?raw=true)

### 学习统计

提供简单的统计分析功能。

![单词列表](doc/analysis.gif?raw=true)

## 管理命令

因为是简单自用为目的设计的软件，没有单独做管理页面。系统管理通过命令行进行。

添加用户

```
# 普通用户
python manage.py useradd <用户名> <口令>
# 管理员
python manage.py useradd <用户名> <口令> admin
```


导入字典

```
python manage.py sync_dict
```

导入例句

```
python manage.py sync_sentence
```

分析词典

```
python manage.py wordlist # 标注 单词星级
python manage.py dict_parse # 拆分中英文解释
```