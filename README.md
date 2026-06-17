
## ai-to-cad-web 本地AI图纸转CAD网页
基于 FastAPI + Vue3 + BeesFPD API 开发，实现图片/PDF一键转换为DWG/DXF矢量CAD图纸
### 1. 环境前置要求
1. Python 3.11 及以上
2. Node.js 18 及以上
3. 自备 BeesFPD 平台API Key（转换核心密钥）
4. 可选：ngrok（用于外网分享本地网页）

### 2. 完整部署使用步骤
#### ① 拉取项目代码
打开终端执行克隆命令：
```bash
git clone https://github.com/Laoshuren666/ai-to-cad-web.git
cd ai-to-cad-web
```

#### ② 后端启动（FastAPI接口服务）
1. 进入后端文件夹
```bash
cd backend
```
2. 安装Python依赖
```bash
pip install -r requirements.txt
```
3. 修改配置文件，填入自己的 `BeesFPD API Key`
4. 启动后端服务
```bash
python main.py
```
后端默认运行地址：`http://127.0.0.1:8000`

#### ③ 前端启动（Vue网页界面）
1. 新开一个终端，回到项目根目录，进入前端文件夹
```bash
cd frontend
```
2. 安装前端依赖
```bash
npm install
```
3. 启动开发页面
```bash
npm run dev
```
前端访问地址：`http://localhost:5173`

### 3. 功能使用流程
1. 打开前端页面，上传图片/JPG/PNG/PDF图纸文件
2. 填写你的有效BeesFPD密钥
3. 点击转换，等待生成DWG/DXF矢量文件
4. 页面直接下载生成后的CAD图纸

### 4. 外网分享（可选，ngrok）
1. 安装ngrok，执行端口映射
```bash
ngrok http 5173
```
2. 复制ngrok生成的公网链接发给他人，对方即可远程访问你的转换网页

### 5. 注意事项
1. `frontend/node_modules` 不需要手动上传，他人克隆项目后执行 `npm install` 自动生成
2. BeesFPD密钥为付费接口，需自行注册平台申请，代码内无内置可用密钥
3. 后端会自动缓存上传图纸与生成文件，文件夹 `uploads` / `outputs` 可手动清空

---

