# @https://hub.docker.com/r/superng6/bilibili-helper

# 使用方法：https://mp.weixin.qq.com/s/xXSHMrHjZsBcMKLPABZsjQ

# 1、首先，你要有一个青龙面板……
# 2、为青龙面版安装openjdk
#  （1）使用任意工具链接到你安装青龙面板的设备（服务器、软路由等）
#  （2）运行以下命令
#          docker exec -it qinglong bash
#          cd scripts
#          apk add openjdk8
#  （3）上述命令中，
#          qinglong是你的容器名，青龙面板项目的默认名字就是这个，如果你自定义过，对应修改；
#          cd  scripts 指的是进入青龙面板的scripts文件夹（脚本目录），默认就是这个路径，如果自定义过路径对应修改就可以了。
#  （4）上述代码跑完就可以了。
# 3、下载脚本文件备用
#  （1）下载第一个文件，jar格式
#      「BILIBILI-HELPER-v2.1.0.jar」
#  （2）下载第二个文件，json格式
#    「config.json」
# 4、修改json文件添加你的bilibili账号信息
#  （1）打开config.json文件，首先修改账号信息和登录信息
#          ①浏览器登录b站账号，在b站首页按F12打开调试页面
#          ②点击控制台的“网络”标签（英文版叫network好像），然后f5刷新当前页面
#          ③ 在下方的名称（name）栏中找到“nav”
#          ④点开nav文件，点击标头（header），找到cookie，右键点击选择“复制值”，即可。
#          ⑤回到config.json文件，将复制的值粘贴到bilicookies后面的引号里即可
#      获取user-agent
#          ①还是在刚才的nav文件中，找到usr-agent
#          ②复制值，并替换到config.json文件中即可
#  （2）在config.json中设置推送方式并填写信息，根据自己的需求填写就可以了，不废话，和青龙面板机器人的推送填写等基本一样
# 5、将jar文件，和修改好的json文件，一起上传到青龙面板的脚本文件夹ql/scripts
# 6、青龙拉取自动化脚本
#    命令为：
#        ql raw https://raw.githubusercontent.com/JunzhouLiu/BILIBILI-HELPER-PRE/main/bilibili_helper.sh
#    运行拉取成功后进行下一步。
# 7、在青龙面板脚本目录中新建文件，命名为bili.sh
#        可以用命令行方式创建，也可以用shell工具直接操作，下方以finalshell为例
# 8、在新建的这个空文件中写入如下代码，并保存
#        java -jar /ql/scripts/BILIBILI-HELPER-v2.1.0.jar /ql/scripts/config.json
# 9、在青龙面板中添加自动化任务就完成了。
