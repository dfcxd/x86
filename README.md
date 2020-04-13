# X86专用 openwrt固件编译工作流

## 介绍

使用Lean大代码编译，工作流使用P3TERX大模板改写；

增加安装依赖项，编译过程不报错（eg:antlr3 gperf）；

每周五定时编译，每周发布一份release；

固件仅包含combined格式，不包含uefi格式（如需，可修改config文件）；

手动启动，提交make.img，手动触发工作流；

## 编译范围变更过程

首先通过config工作流生成config，然后把config导出到根目录文件中，再定时（或手动）编译，实现长效机制；

## 插件范围

Lean大默认的插件全包含，增加aira2（用于常规下载）、miniDLNA（视频转码）、ttyd（网页版ssh终端）、CIFS-mount；

删除xlnetacc、zerotier、accesscontrol、openvpn、qbittorrent、arpbind、unblockmusic、vsftpd、vlmcsd、wol；

ssrp只保留v2ray、trojan；

删除vmware编译包、删除IPv6支持；
