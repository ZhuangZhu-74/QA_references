## JMeter的JSR223，Beanshell等脚本编写的思路

当你阅读JMeter的`component_reference.html`时，你会发现`JSR223`，`Beanshell`等元件提供了可操作的几个变量，只是当你想进一步了解它们的用法时，浩瀚的`api`文档让我这个能力一般的人感到无所适从，那么该怎么解决问题呢？

我们以`JSR223 postprocessor`为例分析:

1. 在JMeter官网下载源代码包。
2. 在你喜欢的IDE（`Eclipse`，`vscode`等）导入解压后的文件夹。
3. 关于源代码的目录结构的参考消息，可参考[这里](https://blog.csdn.net/zuozewei/article/details/85042829)；
4. 使用`Everything`在解压后的文件夹查找"JSR223postprocessor"，找到`JSR223PostProcessor.java`并记下路径，在IDE中查找，它位于源代码文件夹`src/components/src/main/java`下的包`org.apache.jmeter.extractor`。
5. 在`JSR223PostProcessor.java`文件中，只有`log`被找到而且还没有绑定的语句，接着从继承和接口找线索。
6. 在继承的父类`JSR223TestElement.java`，我们顺利找到了所有绑定的变量。

最后，我整理的参考表格为本目录下所有的 `*.xlsx` 文件。
