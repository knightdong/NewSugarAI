# Purchase页面选择逻辑修复

## 问题描述
当用户选择第三个gem包时，第二个包仍然显示红色边框，选择状态没有正确更新。

## 问题原因
在`selectPackage`函数中，代码使用了`event.target.closest('.gem-package')`来获取当前点击的元素，但是`event`对象并不是函数的参数，这导致在某些情况下选择状态不能正确更新。

## 修复方案
1. **修改HTML调用方式**：将onclick调用从`selectPackage('packageId')`改为`selectPackage('packageId', this)`，直接传递当前元素引用。

2. **修改JavaScript函数**：更新`selectPackage`函数接收element参数，直接使用传入的元素引用而不是依赖event对象。

## 修复前的代码
```javascript
function selectPackage(packageId) {
    // 移除之前的选中状态
    document.querySelectorAll('.gem-package').forEach(pkg => {
        pkg.classList.remove('selected');
    });
    
    // 选中当前包
    event.target.closest('.gem-package').classList.add('selected');
    selectedPackage = packageId;
    
    // 更新购买按钮
    const pkg = packages[packageId];
    const totalGems = pkg.gems + pkg.bonus;
    document.getElementById('purchaseBtn').textContent = 
        `Purchase ${totalGems} Gems for $${pkg.price}`;
}
```

## 修复后的代码
```javascript
function selectPackage(packageId, element) {
    // 移除之前的选中状态
    document.querySelectorAll('.gem-package').forEach(pkg => {
        pkg.classList.remove('selected');
    });
    
    // 选中当前包
    element.classList.add('selected');
    selectedPackage = packageId;
    
    // 更新购买按钮
    const pkg = packages[packageId];
    const totalGems = pkg.gems + pkg.bonus;
    document.getElementById('purchaseBtn').textContent = 
        `Purchase ${totalGems} Gems for $${pkg.price}`;
}
```

## 修复效果
- 现在选择任何gem包时，都会正确移除之前的选择状态
- 当前选择的包会正确显示红色边框和勾选标记
- 购买按钮会正确更新显示选中包的信息

## 测试验证
1. 依次点击不同的gem包
2. 确认每次只有一个包显示为选中状态
3. 确认购买按钮文本正确更新 