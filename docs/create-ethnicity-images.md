# Create页面 - 人种图片功能更新

## 更新概述
在"Choose Ethnicity & Age"步骤中，将原有的emoji图标替换为更直观的人种图片，提供更好的用户体验。

## 主要更改

### 1. 图片替换
- **原有设计**: 使用emoji图标 (🌸, 🌹, 🌺, 🌻, 🌷)
- **新设计**: 使用SVG图片展示不同人种特征

### 2. 新增人种选项
- **Asian** (亚洲人): 东亚人种特征
- **Caucasian** (高加索人): 欧洲人种特征  
- **Latina** (拉丁裔): 拉丁美洲人种特征
- **African** (非洲人): 非洲人种特征
- **Middle Eastern** (中东人): 中东人种特征 (新增)
- **Mixed** (混血): 混血人种特征

### 3. 样式优化
- 圆形图片显示 (80x80像素)
- 选中状态边框高亮 (#ed7f8c)
- 鼠标悬停效果
- 响应式设计兼容

### 4. 文件结构
```
design/assets/ethnicity/
├── README.md           # 图片说明文档
├── asian.svg          # 亚洲人种图片
├── caucasian.svg      # 高加索人种图片
├── latina.svg         # 拉丁裔人种图片
├── african.svg        # 非洲人种图片
├── middle_eastern.svg # 中东人种图片
└── mixed.svg          # 混血人种图片
```

## 技术实现

### CSS样式
```css
.option-card.icon-card .option-image {
    width: 80px;
    height: 80px;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    border-radius: 50%;
    margin-bottom: 15px;
    border: 3px solid #444;
    transition: all 0.3s ease;
}

.option-card.icon-card.selected .option-image {
    border-color: #ed7f8c;
}
```

### JavaScript功能
- 更新`getEthnicityContent()`函数使用图片
- 新增`middle_eastern`选项的映射
- 保持原有的选择逻辑和验证

## 占位符图片特点
- 使用SVG格式，支持缩放不失真
- 简洁的面部特征表现
- 不同肤色和发色体现人种差异
- 统一的设计风格和尺寸

## 使用说明
1. 用户可以用真实的人像照片替换当前的SVG占位符
2. 建议使用200x200像素或更高分辨率的图片
3. 支持JPG、PNG、SVG等格式
4. 需要保持一致的视觉风格

## 后续改进建议
- 考虑添加更多人种细分选项
- 支持用户自定义上传图片
- 添加图片预览功能
- 优化移动端显示效果 