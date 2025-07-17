# Sugar.AI 开发指南 🍭

## 项目结构

```
SugarAI/
├── 📄 index.html       # 首页 (Explore)
├── 📄 auth.html        # 登录注册页面
├── 📄 chat.html        # 聊天页面
├── 📄 create.html      # 创建角色页面
├── 📄 dashboard.html   # 用户面板
├── 📄 generate.html    # 生成页面
├── 📄 purchase.html    # 购买页面
├── 📁 assets/          # 静态资源文件
│   ├── pic_1.jpeg ~ pic_10.jpeg  # 角色图片
│   ├── ethnicity/      # 种族选择图片
│   └── placeholder.txt
├── 📁 docs/            # 项目文档
│   ├── README.md       # 项目说明
│   ├── design-spec.md  # 设计规范
│   └── *.md           # 其他开发文档
├── 🔧 dev-server.sh    # 开发服务器脚本
├── 🔧 deploy.sh        # 部署脚本
├── 📋 .gitignore       # Git忽略文件
└── 📋 *.md            # 项目文档
```

## 开发流程 🔄

### 1. 启动开发服务器

```bash
# 启动本地开发服务器
./dev-server.sh

# 访问地址: http://localhost:8000
```

### 2. 开发和调试

- 直接在根目录的HTML文件中开发
- 实时预览：浏览器自动刷新查看效果
- 调试工具：使用浏览器开发者工具

### 3. 资源管理

- 图片资源放在 `assets/` 目录下
- 使用相对路径引用：`assets/pic_1.jpeg`
- 保持文件命名规范和统一

### 4. 部署到GitHub Pages

```bash
# 检查并部署更改
./deploy.sh

# 手动部署流程
git add .
git commit -m "更新描述"
git push
```

## 页面功能说明 📄

### index.html (首页/Explore)
- 展示AI角色卡片
- 瀑布流布局
- 点击进入聊天

### auth.html (登录注册)
- 用户登录界面
- 注册功能
- 密码重置

### chat.html (聊天页面)
- 实时聊天界面
- 消息历史记录
- 媒体文件支持

### create.html (创建角色)
- 自定义角色创建
- 多步骤向导
- 实时预览

### dashboard.html (用户面板)
- 用户信息管理
- 历史记录查看
- 会员管理

### generate.html (生成页面)
- 图像生成功能
- 视频生成
- 合影功能

### purchase.html (购买页面)
- 会员购买
- 点数充值
- 支付处理

## 开发规范 📋

### HTML结构
- 使用语义化HTML5标签
- 保持良好的代码缩进
- 添加适当的注释

### CSS样式
- 使用Tailwind CSS框架
- 保持响应式设计
- 主题色彩：`#212121` (背景), `#ed7f8c` (强调色)

### JavaScript
- 使用现代ES6+语法
- 模块化代码结构
- 错误处理和用户反馈

## 常用命令 🛠️

```bash
# 启动开发服务器
./dev-server.sh

# 部署到GitHub Pages
./deploy.sh

# 查看Git状态
git status

# 查看提交历史
git log --oneline -10

# 回滚到上一个提交
git reset --hard HEAD~1

# 强制推送 (谨慎使用)
git push -f
```

## 故障排除 🔧

### 开发服务器无法启动
```bash
# 检查端口占用
lsof -i :8000

# 使用不同端口
python3 -m http.server 8001
```

### 文件路径问题
- 确保使用相对路径
- 检查文件名大小写
- 验证文件确实存在

### Git推送失败
```bash
# 拉取最新代码
git pull

# 解决冲突后再推送
git push
```

### 样式不生效
- 检查CSS文件路径
- 清除浏览器缓存
- 验证CSS语法

## 测试清单 ✅

### 开发环境测试
- [ ] 所有页面能正常加载
- [ ] 响应式设计在不同设备上正常
- [ ] 图片资源正确显示
- [ ] 交互功能正常工作

### 部署前检查
- [ ] 代码已提交到Git
- [ ] 没有语法错误
- [ ] 所有资源文件已包含
- [ ] 路径引用正确

### 线上验证
- [ ] GitHub Pages正常部署
- [ ] 所有功能在线上正常
- [ ] 移动端兼容性良好
- [ ] 加载速度可接受

## 性能优化 🚀

### 图片优化
- 压缩图片大小
- 使用适当的图片格式
- 实现懒加载

### 代码优化
- 压缩CSS和JavaScript
- 减少HTTP请求
- 使用CDN加速

### 用户体验
- 添加加载动画
- 提供错误反馈
- 优化交互响应

## 联系方式 📧

如有问题，请：
1. 查看 `docs/` 目录中的相关文档
2. 检查Git提交历史
3. 联系开发团队

---

**记住：开发→测试→部署** ��

Happy Coding! 🎉 