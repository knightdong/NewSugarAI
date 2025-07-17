# Create Character - Step-by-Step Guide

## 概述
重新设计了Create角色创建模块，采用全英文界面和分步骤页面设计，提供更加直观和用户友好的角色创建体验。

## 7个步骤流程

### 第1步：Choose Style
- **目标**: 选择角色的艺术风格
- **选项**: 
  - Realistic (真实风格)
  - Anime (动漫风格)
- **界面**: 卡片式选择，带有图标和描述

### 第2步：Choose Ethnicity & Age
- **目标**: 选择种族和年龄
- **种族选项**:
  - Asian (亚洲人)
  - Caucasian (高加索人)
  - Latina (拉丁美洲人)
  - African (非洲人)
  - Mixed (混血)
- **年龄控制**: 18-40岁，通过输入框和+/-按钮调整

### 第3步：Choose Appearance
- **目标**: 选择外观特征
- **选项**:
  - Hair Color: 8种颜色选择
  - Skin Color: 6种肤色选择
  - Eye Color: 6种眼色选择
- **界面**: 颜色选择器，显示实际颜色

### 第4步：Choose Body Type
- **目标**: 自定义身体比例
- **调整项**:
  - Chest Size (胸部大小): 20-100%
  - Butt Size (臀部大小): 20-100%
  - Fitness Level (健身程度): 0-100%
- **界面**: 滑块控制器，实时显示数值

### 第5步：Choose Personality
- **目标**: 选择性格类型
- **12种性格选项**:
  - Caregiver (护理者)
  - Sage (智者)
  - Innocent (天真者)
  - Jester (小丑)
  - Temptress (诱惑者)
  - Dominant (支配者)
  - Submissive (顺从者)
  - Lover (恋人)
  - Nympho (色情狂)
  - Mean (刻薄者)
  - Confidant (知己)
  - Experimenter (实验者)
- **界面**: 卡片式选择，带有图标和详细描述

### 第6步：Choose Relationship
- **目标**: 定义关系类型
- **12种关系选项**:
  - Stranger (陌生人)
  - School Mate (同学)
  - Colleague (同事)
  - Mentor (导师)
  - Girlfriend (女朋友)
  - Sex Friend (性伴侣)
  - Wife (妻子)
  - Mistress (情妇)
  - Friend (朋友)
  - Best Friend (最好的朋友)
  - Step Sister (继妹)
  - Step Mom (继母)
- **界面**: 卡片式选择，带有图标和描述

### 第7步：Summary
- **目标**: 总结并确认创建
- **功能**:
  - 显示所有选择的总结
  - 输入角色名称
  - 最终创建按钮
- **界面**: 两列布局显示所有选项

## 技术特性

### 进度条系统
- 7个步骤的可视化进度条
- 当前步骤高亮显示
- 已完成步骤标记
- 连接线显示进度

### 导航系统
- Previous/Next按钮
- 第一步禁用Previous按钮
- 最后一步隐藏Next按钮
- 响应式按钮状态

### 数据管理
- 全局characterData对象存储所有选择
- 实时更新选择状态
- 本地存储保存最终数据
- 验证必填项完整性

### 界面特点
- 完全英文界面
- 暗色主题设计
- 粉色品牌色彩
- 响应式布局
- 流畅的过渡动画

## 文件结构

```
design/
├── create.html          # 主要创建页面
├── create-character-steps.md  # 本文档
└── ui-layout.html       # 整体布局
```

## 使用流程

1. 用户进入Create页面
2. 按步骤选择各项设置
3. 使用Next/Previous导航
4. 在Summary步骤确认所有选择
5. 输入角色名称
6. 点击Create Character完成创建
7. 自动跳转到聊天页面

## 数据结构

```javascript
characterData = {
    style: '',              // 'realistic' | 'anime'
    ethnicity: '',          // 'asian' | 'caucasian' | 'latina' | 'african' | 'mixed'
    age: 22,               // 18-40
    hairColor: '',         // 8种颜色选项
    skinColor: '',         // 6种肤色选项
    eyeColor: '',          // 6种眼色选项
    bodyType: {
        chestSize: 50,     // 20-100
        buttSize: 50,      // 20-100
        fitness: 50        // 0-100
    },
    personality: '',       // 12种性格选项
    relationship: '',      // 12种关系选项
    name: ''              // 用户输入的角色名称
}
```

## 更新日期
2024年12月 - 初始版本创建 