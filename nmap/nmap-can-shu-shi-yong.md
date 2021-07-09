---
description: 参数介绍
---

# Nmap参数使用

**目标选择**

```bash
nmap ip #单个扫描
nmap www.xxx.com #扫描主机
nmap 192.168.1.1-20 #扫描一系列IP
nmap 192.168.1.1/20 #扫描子网
nmap -iL list-of-ips.txt #从文本文件获得扫描目标
nmap -P0 ip #无Ping扫描（常用于防护墙禁止ping的情况）
```

**端口选择**

```bash
nmap -p port ip #扫描单个端口
nmap -p 1-100 192.168.1.1 #扫描一系列端口
nmap -F ip #扫描100个常见端口（快速）
nmap -p —ip #扫描所有65535端口
nmap -p 80,22,3306 ip #扫描指定端口
```

**操作系统和服务检测**

```bash
nmap -A ip #检测操作系统和服务
nmap -sV ip #标准服务检测
nmap -sV --version-intersity 5 ip #激进的服务检测
nmap -sV --version-intersity 0 ip #轻量Banner抓取检测
```

**输出格式**

```bash
nmap -oN outputfile.txt ip #将默认输出保存到文件
nmap -oX outputfile.xml ip #将结果保存为xml
nmap -oG outputfile.txt ip #为方便grep来保存格式
namp -oA outputfile ip #保存所有格式
```

**用NES脚本深入挖掘**

```bash
nmap -sV -sC ip #使用默认安全脚本扫描
nmap --script-help=ssl-heartbleed #获取脚本的帮助
nmap -sV -p 443 -script=ssl-heartbleed.nse ip #使用特定的NSE脚本进行扫描
nmap -sV --script=smb* ip #使用一组脚本进行扫描
nmap -sV -p- --script=all ip #使用全部NSE脚本进行扫描
```

**HTTP服务信息**

```bash
nmap --script=http-title 192.168.1.0/24 #从HTTP服务收集页面标题
nmap --script=http-headers 192.168.1.0/24 #获取Web服务的HTTP头
nmap --script=http-enum 192.168.1.0/24 #从已知路径查找网络应用程序
```

**检测SSL漏洞问题的主机**

```bash
nmap -sV -p 443 --script=ssl-heartbleed 192.168.1.0/24 #Heartbleed测试
```





