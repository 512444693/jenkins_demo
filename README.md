# jenkins_demo
## 介绍
该项目是个demo，是将编译、Ant运行Jmeter、单元测试、生成报告与jenkins结合起来的一个示例

- jmetertest目录下是ant运行jmeter所需的文件
- unittest目录是[unittest](https://github.com/512444693/unittest)项目下*mxrsessionapply*分支的文件

## 思路
平时测试过程中会有许多有用的文件以后会用得到，比如说Jmeter用到的jmx文件、数据库sql文件、配置文件等等。
这些重要的文件希望能够保存下来供以后使用，最方便和安全的方式便是保存到版本控制系统。
本项目即有三个功能
- 将测试mxrsessionapply过程中的重要文件保存下来
- 方便与jenkins做持续集成
- 作为示例

## 持续集成示例
- 先安装一个名为*HTML Publisher plugin*的插件，用来展示报告，其它插件默认安装即可
- 邮件服务器、git、ant等工具要配置正确(注意配置邮件时需要将*系统管理员邮件地址*和smtp中的*User Name*配置一致，否则可能会认证失败)
1. 在jenkins中创建一个名为mxrsessionapply_ant_jmeter_and_unittest_and_mail的任务
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step1.jpg)
2. 配置源码管理，即将本项目中的文件拉下来
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step2.jpg)
3. 配置构建过
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step3.jpg)
4. 配置构建后操作
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step4.jpg)
5. 若构建失败发送邮件
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step5_1.jpg)
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step5_2.jpg)


## 效果展示
- 项目概览
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step6.jpg)
- 代码覆盖率报告
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step7.jpg)
- jmeter测试过程报告
![image](https://raw.githubusercontent.com/512444693/resources/master/jenkins_demo/step8.jpg)


## 展望
以后可将jmeter的性能测试也加入进来
