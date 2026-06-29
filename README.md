# 📖 青春档案

一个存青春回忆的静态网页。有密码锁，输入"邓香凝"才能看。

## 项目结构

```
laoda-page/
├── index.html      # 主页面（密码锁 + 全部内容）
├── background.jpg  # 背景图
└── README.md       # 本文件
```

## 更新内容怎么操作

### 方法一：直接在服务器上改

```bash
ssh root@你的VPS_IP
cd /root/laoda_page
nano index.html          # 改内容
# 改完后保存（Ctrl+X, Y, Enter）
# 改的是静态文件，不用重启，刷新网页就能看到
```

### 方法二：本地改完再推

```bash
# 1. 先克隆到本地
git clone https://github.com/PaytonJu/laoda-page.git
cd laoda-page

# 2. 修改 index.html

# 3. 推送
git add .
git commit -m "更新了什么"
git push

# 4. 到服务器上拉取
ssh root@你的VPS_IP
cd /root/laoda_page
git pull
```

## 部署

部署到 VPS 的话，用 `vps-deploy` 项目的一键脚本：

```bash
git clone https://github.com/PaytonJu/vps-deploy.git
cd vps-deploy
# 改配置（IP、域名）
./deploy.sh
```

## 备注

- 页面有密码锁，答案用星号藏在 JS 里
- 背景图 1280×720
- 服务方式：`python3 -m http.server 5003`（已做成 systemd 服务，开机自启）
