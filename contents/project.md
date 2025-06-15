# 项目展示

## 汉语言文化宣传动画 - 中国大学生计算机设计大赛

- 使用 **PureRef** 收集动画概念参考素材，并编写详细的动画设计文档。  
- 基于 **Azure TTS** 实现文本对话转语音，增强动画沉浸感与互动性。  
- 利用 **Blender** 与 **Unreal Engine** 完成场景建模，使用 **Mixamo** 进行骨骼绑定与动画映射，最终通过 **Cycles 渲染器** 输出高质量动画序列。  
- 完成 4 分钟宣传动画，荣获 **中国大学生计算机设计大赛国家级三等奖**。

<div class="project-grid">
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Render/Animation.png?raw=true" alt="Animation">
    </div>
</div>

---

## 数字文物的三维制作与渲染 - 四川省博物院

- 在博物院现场使用多角度高清摄影采集文物图像，借助 **MetaShape** 完成三维重建与高保真模型生成。  
- 使用 **Blender** 对模型进行重拓扑，结合 **Substance Painter** 进行高精度材质制作与贴图处理。  
- 基于 **Cycles 渲染器** 输出写实效果，最终通过 **Three.js** 嵌入至展示平台，实现可交互的三维数字展示。

---

## 个人三维建模渲染项目

<div id="personal-render" class="project-grid">
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Render/1.jpg?raw=true" alt="Render 1">
    </div>
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Render/2.jpg?raw=true" alt="Render 2">
    </div>
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Render/3.jpg?raw=true" alt="Render 3">
    </div>
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Render/4.jpg?raw=true" alt="Render 4">
    </div>
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Render/5.jpg?raw=true" alt="Render 5">
    </div>
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Render/6.jpg?raw=true" alt="Render 6">
    </div>
</div>

<!-- 图片预览模态框 -->
<div id="imagePreviewModal" class="image-preview-modal" onclick="closeImagePreview(event)">
    <span class="close-btn" onclick="closeImagePreview(event)">&times;</span>
    <img id="previewImage" src="" alt="Preview">
</div>

<script>
function showImagePreview(element) {
    const modal = document.getElementById('imagePreviewModal');
    const previewImg = document.getElementById('previewImage');
    const img = element.querySelector('img');
    
    // 获取原始图片URL
    let originalUrl = img.src;
    // 移除 ?raw=true 参数
    originalUrl = originalUrl.replace(/\?raw=true$/, '');
    // 确保使用原始图片URL
    originalUrl = originalUrl.replace('/blob/', '/raw/');
    
    // 设置预览图片
    previewImg.src = originalUrl;
    
    // 显示模态框
    modal.style.display = 'block';
    document.body.style.overflow = 'hidden';
    
    // 添加过渡动画
    setTimeout(() => {
        modal.classList.add('active');
    }, 10);
}

function closeImagePreview(event) {
    // 防止事件冒泡
    if (event) {
        event.stopPropagation();
    }
    
    const modal = document.getElementById('imagePreviewModal');
    modal.classList.remove('active');
    
    // 等待过渡动画完成后再隐藏模态框
    setTimeout(() => {
        modal.style.display = 'none';
        document.body.style.overflow = 'auto';
    }, 300);
}

// 按ESC键关闭预览
document.addEventListener('keydown', function(event) {
    if (event.key === 'Escape') {
        closeImagePreview();
    }
});

// 阻止图片拖拽
document.querySelectorAll('.project-card img').forEach(img => {
    img.addEventListener('dragstart', (e) => e.preventDefault());
});
</script>

