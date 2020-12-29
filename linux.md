# Linux笔记

## 网络

### Nmap

* 检查开放的端口 `nmap -A 192.168.31.1`
* 检查网络下能连接的所有IP `namp -sP 192.168.31.1/24`

### 同步目录

- 一般同步：`/usr/bin/rsync -avPz root@20.100.60.80:/var/www/html/fiction /home/pi/dataBk/`
- ssh端口修改：`/usr/bin/rsync -avPz -e'ssh -p28224' wanxx@20.100.60.80:/var/www/html/fiction /home/pi/dataBk/`

-----------------------------------------------------------------------------------------------------------------------------------------



## 软件

### icdiff 
`文件内容对比`
可以左右直观显示，

### youtube-dl 
`下载youtube视频`
* 使用代理下载
  
  `youtube-dl --proxy 127.0.0.1:1080 '视频链接'`

### jupyter设置

 - **允许远程访问** : `--ip='0.0.0.0'`

 - **指定端口** : `--port= 6000`

 - **设置密码** : `jupyter-notebook password`

### 温度显示
 - **安装** :`apt-get install lm-sensors`
 - **使用**:`sensors`
 
### 画图(dot)
 - `sudo apt-get install graphviz`
 - `brew install graphviz`
-----------------------------------------------------------------------------------------------------------------------------------------




## 命令

### nc
检查一段端口状态
```bash
nc -vz 104.160.40.250 5000-5025
```
### sed                                                                                                                                                                                                                                                                      
批量替换，删除一些文字                                                                                                                                                                                                                                                        
```bash                                                                                                                                                                                                                                                                      
sed -i '/192.168/d;/10.147/d' ./hosts-restricted                                                                                                                                                                                                                             
sed -i 's/aaa/AAA/g;s/bbb/BBB/;s/ccc/CCC/' file.txt                                                                                                                                                                                                                          
```                                                                                                                                                                                                                                                                          
查看指定行数的文件内容
```bash
sed 'n,m!d' file

```
### xargs                                                                                                                                                                                                                                                                    
批量删除文件里的多个字符                                                                                                                                                                                                                                                     
```bash                                                                                                                                                                                                                                                                      
ls ./* | xargs -i sed -i '/192.168/d;/10.147/d' {} 

### systemctl

* 常用命令
```
 # 所有状态
 systemctl list-unit-files | grep suninfo
 # 激活开机启动
 systemctl enable suninfo-dbaudit.service
 # 关闭开机启动
 systemctl disenable suninfo-dbaudit.service
```

* 简单模板
```bash
[Unit]
 Description=Aria2
 After=network-online.target
 Wants=network-online.target
 
 [Service]
 Type=simple
 PIDFile=/var/run/aria2.pid
 ExecStart=/usr/bin/aria2c --conf-path /root/conf/aria.conf
 ExecStop=/bin/kill $MAINPID
 Restart=on-failure
 RestartPreventExitStatus=23
 
 [Install]
 WantedBy=multi-user.target
```

## vim 

### vim 安装YCM后python版本不正确
```bash
"设置全局Python路径
let g:ycm_server_python_interpreter='/usr/bin/python3.6'"
```
