<h1>16.9.26 部署项目到服务器</h1>


        project项目
        request请求
        response响应
        上传代码：ssh/git/github
        scp:ssh

    #后台服务器上修改
        1.上传代码
            scp -r 文件名 网址：（：必须）
            输入密码

        2.登陆服务器
            ssh 网址
            输密码

        3.安装（软件）服务器server
            sudo apt-get install nginx 安装
            nginx专门托管网站的软件

        4.配置服务器nginx
            cd /etc/nginx
            cd sites-enabled转到可用域名路径
            ls查看可以使用的域名
            修改创建配置文件
            sudo cp 文件名.conf(配置文件) 文件名.conf

        5.使用vim软件修改文件
            sodo vim 文件名.conf打开
            server-name 域名
            root /路径（修改入口文件）

        6.重启服务器
            sudo service nginx reload重启
            sudo nginx -t查看报错信息


    #本地模拟服务器
        1.安装服务器
            sudo apt-get install openssh-server
            ifconfig查看

        2.文件拷贝修改
            scp -r 本地文件名 计算机名@其IP:（：必须有）

        3.配置服务器
            cd /etc/nginx/跳到 niginx 的配置区域
            cd sites-enabled/打开添加新⺴网网站的配置文文件夹
            sudo vim 配置名.conf 新建并打开配置文件
            写入server {
                listen 80;
                server_name express.haoqicat.com;（域名）
                root /home/peter/express-api/;（网址在服务器的路径）
            }
            sudo service nginx reload 重载配置文文件
            sudo nginx -t 查看报错信息


        whoami查看本机用户
        ssh-keygen生成本机密钥
        ssh ssd线上输入密钥
        lsb_release -a 查看系统
        ctrl+D退出服务器

        vim命令：
        sudo vim 文件名
        i 插入模式
        Esc退出插入模式
        shift+z+z保存退出
        :q强制退出
        :q!强制不保存退出
        u撤销
        g+g回到顶部
        d删除
        G回到底部
        g+g+d+G删除所有
        y+y复制


<h1>16.9.27</h1>

    #后补9.26

        1.sudo vim /etc/hosts本机修改假域名
            添加内容 192.168.1.149    wwww.nuan

        2.免密码登陆自己的服务器
            在根目录.ssh 新建authorized_keys文件粘贴秘钥保存
