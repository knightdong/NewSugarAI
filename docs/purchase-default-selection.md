# Purchase页面默认选中250 Gems包

## 修改需求
1. 打开付费页面时默认选中250 Gems（Most Popular）包
2. 当不选择250 Gems时，它的边框应该是灰色而不是粉色

## 修改内容

### 1. HTML结构修改
在250 Gems包的HTML中添加`selected`类：
```html
<div class="gem-package popular selected" onclick="selectPackage('popular', this)">
```

### 2. CSS样式修改
修改popular类的边框颜色逻辑：
```css
.gem-package.popular {
    border-color: #666;  /* 未选中时为灰色 */
    background: linear-gradient(145deg, rgba(237, 127, 140, 0.05), rgba(237, 127, 140, 0.02));
}

.gem-package.popular:hover:not(.selected) {
    border-color: #999;  /* 鼠标悬停时为浅灰色 */
}

.gem-package.popular.selected {
    border-color: #ed7f8c;  /* 选中时为粉色 */
    background: linear-gradient(145deg, rgba(237, 127, 140, 0.1), rgba(237, 127, 140, 0.05));
}
```

### 3. JavaScript逻辑修改
1. 设置默认选中状态：
   ```javascript
   let selectedPackage = 'popular';
   ```

2. 页面加载时初始化：
   ```javascript
   document.addEventListener('DOMContentLoaded', function() {
       // 默认选中250 Gems包
       const pkg = packages['popular'];
       const totalGems = pkg.gems + pkg.bonus;
       document.getElementById('purchaseBtn').textContent = 
           `Purchase ${totalGems} Gems for $${pkg.price}`;
   });
   ```

## 实现效果
- 页面加载时250 Gems包默认选中，显示粉色边框和勾选标记
- 购买按钮默认显示"Purchase 300 Gems for $9.99"
- 选择其他包时，250 Gems包的边框变成灰色
- 重新选择250 Gems包时，边框变回粉色

## 用户体验改进
1. 用户打开页面时立即看到推荐的"Most Popular"包已被选中
2. 清晰的视觉反馈：选中时粉色边框，未选中时灰色边框
3. 购买按钮始终显示有效的选择信息，无需用户先点击选择 