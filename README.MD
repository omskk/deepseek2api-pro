# DeepSeek2API

[![](https://img.shields.io/github/license/omskk/deepseek2api.svg)](LICENSE)
![](https://img.shields.io/github/stars/omskk/deepseek2api.svg)
![](https://img.shields.io/github/forks/omskk/deepseek2api.svg)

## 免责声明

**本项目仅供学习交流使用，请勿用于任何非法用途。**

**使用本软件所产生的一切后果由使用者自行承担，本组织和个人不承担任何责任。**

**使用本软件所产生的一切后果由使用者自行承担，本组织和个人不承担任何责任。**

**使用本软件所产生的一切后果由使用者自行承担，本组织和个人不承担任何责任。**

## 配置说明

### 1. 克隆项目

```shell
git clone https://github.com/omskk/deepseek2api.git
cd deepseek2api
```

### 2. 配置环境变量

在项目根目录创建 `.env` 文件：

```shell
cp .env.example .env
```

编辑 `.env` 文件，配置以下内容：

```bash
# API Keys（逗号分隔多个 key）
API_KEYS=key1,key2

# 账号配置（JSON 格式数组）
# 每个账号必须包含 password，以及 email 或 mobile 其中之一
# token 字段可选，登录成功后会自动更新
ACCOUNTS=[{"email":"example1@example.com","password":"password1","token":""},{"email":"example2@example.com","password":"password2","token":""}]

# Claude 模型映射配置（可选）
CLAUDE_MODEL_MAPPING={"fast":"deepseek-chat","slow":"deepseek-chat"}
```

### 3. 安装依赖

```shell
pip install -r requirements.txt
```

### 4. 启动服务

```shell
python app.py
```

或使用 nohup 后台运行：

```shell
nohup uvicorn app:app --host 0.0.0.0 --port 5001 > uvicorn.log 2>&1 &
```

## Docker 部署

### 使用 Docker 命令

```shell
docker run -d -p 5001:5001 \
  -e API_KEYS="key1,key2" \
  -e ACCOUNTS='[{"email":"example1@example.com","password":"password1","token":""}]' \
  --name deepseek2api \
  ghcr.io/omskk/deepseek2api:latest
```

### 使用 Docker Compose

```shell
docker-compose up -d
```

## 注意事项

1. 请妥善保管您的账号密码信息，切勿泄露给他人
2. `.env` 和 `tokens.json` 文件已加入 `.gitignore`，请勿手动移除
3. 首次运行时会自动创建 `tokens.json` 文件用于存储登录 token

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=omskk/deepseek2api&type=Date)](https://star-history.com/#omskk/deepseek2api-pro&Date)