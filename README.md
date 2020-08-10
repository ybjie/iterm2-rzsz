# 项目介绍
实现mac本地与服务器进行便捷的文件上传和下载操作

# 步骤
- 安装支持rz和sz命令的lrzsz：brew install lrzsz

- 在本地/usr/local/bin/目录下保存iterm2-send-zmodem.sh 和iterm2-recv-zmodem.sh两个脚本

- 设置一下两个脚本的权限，一般 chmod 777 就行了


- iterm2添加两条tirgger

    - 路径:profiles->default->editProfiles->advanced中的tirgger

    - 分别设置 Regular expression，Action，Parameters，Instant

    - 第一条
        Regular expression: rz waiting to receive.\*\*B0100
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-send-zmodem.sh
        Instant: checked
    - 第二条<br/>
        Regular expression: \*\*B00000000000000
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
        Instant: checked
