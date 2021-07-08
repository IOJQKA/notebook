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



