# 项目介绍
实现mac本地与服务器进行便捷的文件上传和下载操作

# 步骤
- 安装支持rz和sz命令的lrzsz：brew install lrzsz

- 在本地/usr/local/bin/目录下保存iterm2-send-zmodem.sh 和iterm2-recv-zmodem.sh两个脚本

- 设置一下两个脚本的权限，一般 chmod 777 就行了
chmod 777 /usr/local/bin/iterm2-*

- 设置Iterm2的Tirgger特性，profiles->default->editProfiles->Advanced中的Tirgger

# 添加两条trigger
分别设置 Regular expression，Action，Parameters，Instant如下：

- 第一条
        Regular expression: rz waiting to receive./\*/\*B0100<br/>
        Action: Run Silent Coprocess<br/>
        Parameters: /usr/local/bin/iterm2-send-zmodem.sh<br/>
        Instant: checked<br/>
- 第二条
        Regular expression: /\*/\*B00000000000000<br/>
        Action: Run Silent Coprocess<br/>
        Parameters: /usr/local/bin/iterm2-recv-zmodem.sh<br/>
        Instant: checked<br/>
