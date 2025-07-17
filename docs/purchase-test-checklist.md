# 购买页面功能测试清单

## 基本功能测试

### 页面加载测试
- [ ] 购买页面 (purchase.html) 正常加载
- [ ] 所有CSS样式正确应用
- [ ] 页面布局显示正常
- [ ] 所有图标和文本正确显示

### 导航功能测试
- [ ] 所有页面的"Top Up"按钮跳转到purchase.html
  - [ ] ui-layout.html 侧边栏Top Up按钮
  - [ ] chat.html 侧边栏Top Up按钮
  - [ ] create.html 侧边栏Top Up按钮
  - [ ] dashboard.html 侧边栏Top Up按钮
  - [ ] dashboard.html 主内容区Top Up Gems按钮
  - [ ] purchase.html 侧边栏Top Up按钮
- [ ] 购买页面左侧导航功能正常
  - [ ] Explore -> ui-layout.html
  - [ ] Chat -> chat.html
  - [ ] Create -> create.html
  - [ ] Dashboard -> dashboard.html
  - [ ] Logo点击返回首页

### 套餐选择功能测试
- [ ] 点击套餐能正确选中
- [ ] 选中状态视觉反馈正确（边框+✓图标）
- [ ] 只能选择一个套餐
- [ ] 购买按钮文本正确更新
- [ ] 各套餐价格和数量显示正确：
  - [ ] Starter: 100 Gems - $4.99
  - [ ] Popular: 250 Gems + 50 Bonus - $9.99
  - [ ] Premium: 500 Gems + 100 Bonus - $19.99
  - [ ] Ultimate: 1000 Gems + 200 Bonus - $39.99

### 购买流程测试
- [ ] 未选择套餐时点击Purchase按钮显示提示
- [ ] 选择套餐后Purchase按钮显示正确信息
- [ ] 点击Purchase按钮显示确认对话框
- [ ] 确认购买后显示成功消息
- [ ] 成功购买后跳转到首页

## 视觉效果测试

### 样式和动画
- [ ] 套餐卡片悬停效果正常
- [ ] 购买按钮悬停效果正常
- [ ] 选中状态颜色正确（#ed7f8c）
- [ ] "Most Popular"标签显示正确
- [ ] Bonus gems绿色高亮显示
- [ ] 所有渐变效果正确应用

### 响应式设计
- [ ] 桌面端双栏布局正常
- [ ] 平板端单栏布局正常
- [ ] 手机端布局适配正常
- [ ] 各设备上字体大小合适
- [ ] 按钮和卡片尺寸合适

## Premium Benefits显示测试

### 功能列表验证
- [ ] ✨ 创建专属AI女友
- [ ] 💬 无限制文本消息
- [ ] 🖼️ 移除图片模糊 + 高清质量
- [ ] 🎨 生成自定义图片
- [ ] 🎬 生成视频内容
- [ ] ⚡ 快速响应时间
- [ ] 🔄 优先支持和早期访问

### 视觉效果
- [ ] 图标正确显示
- [ ] 高亮文本颜色正确
- [ ] 列表项对齐正确
- [ ] 间距和边框正确

## 支付方式显示测试
- [ ] 💳 信用卡图标和文本
- [ ] 📱 PayPal图标和文本
- [ ] 🍎 Apple Pay图标和文本
- [ ] 🤖 Google Pay图标和文本

## 错误处理测试
- [ ] 未选择套餐时的错误提示
- [ ] JavaScript错误处理正常
- [ ] 页面加载失败时的处理

## 浏览器兼容性测试
- [ ] Chrome浏览器
- [ ] Firefox浏览器
- [ ] Safari浏览器
- [ ] Edge浏览器
- [ ] 移动端浏览器

## 性能测试
- [ ] 页面加载速度
- [ ] 交互响应时间
- [ ] 内存占用合理
- [ ] 无明显性能问题

## 集成测试
- [ ] 从不同页面进入购买页面
- [ ] 购买完成后返回原页面
- [ ] 用户状态保持正确
- [ ] 导航路径正确

## 用户体验测试
- [ ] 操作流程直观
- [ ] 错误提示友好
- [ ] 成功反馈清晰
- [ ] 界面美观现代

## 测试用例

### 用例1：完整购买流程
1. 打开ui-layout.html
2. 点击侧边栏"Top Up"按钮
3. 验证跳转到purchase.html
4. 选择"Popular"套餐
5. 验证按钮文本更新为"Purchase 300 Gems for $9.99"
6. 点击Purchase按钮
7. 在确认对话框中点击"确定"
8. 验证成功消息显示
9. 验证跳转回首页

### 用例2：套餐选择切换
1. 打开purchase.html
2. 点击"Starter"套餐
3. 验证选中状态
4. 点击"Ultimate"套餐
5. 验证之前选中状态取消
6. 验证新选中状态正确
7. 验证按钮文本更新正确

### 用例3：错误处理
1. 打开purchase.html
2. 直接点击"Select a Package"按钮
3. 验证错误提示显示
4. 选择任意套餐
5. 点击购买按钮
6. 在确认对话框中点击"取消"
7. 验证流程正确取消

## 测试记录

### 测试日期：_______
### 测试人员：_______
### 测试环境：_______

### 发现的问题：
1. 
2. 
3. 

### 修复建议：
1. 
2. 
3. 

### 测试结论：
- [ ] 通过 - 所有功能正常
- [ ] 有问题 - 需要修复
- [ ] 需要重测 - 修复后再测试

---

## 自动化测试建议

### 单元测试
```javascript
// 测试套餐选择功能
describe('Package Selection', () => {
  test('should select package correctly', () => {
    // 测试选择逻辑
  });
  
  test('should update purchase button text', () => {
    // 测试按钮文本更新
  });
});
```

### 集成测试
```javascript
// 测试页面跳转
describe('Navigation', () => {
  test('should navigate to purchase page from all pages', () => {
    // 测试从各页面跳转
  });
});
```

### E2E测试
```javascript
// 测试完整购买流程
describe('Purchase Flow', () => {
  test('should complete purchase successfully', () => {
    // 测试端到端购买流程
  });
});
``` 