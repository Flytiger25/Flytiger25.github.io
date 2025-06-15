# 实习经历

## 中国船舶集团海舟系统技术有限公司

### 基于能量法的B样条曲线光顺算法

<div class="project-description">

#### 项目背景
- 为解决曲面构造中等参线曲率波动问题，基于能量函数的优化方法调整 B 样条控制点，提升曲面建模质量。

#### 主要工作
##### 弧长参数化
- 对 B 样条曲线进行弧长参数化处理，将曲线的二阶与三阶导数形式转化为曲率及其变化率的表达。
##### 曲线整体优化
- 在此基础上，构建以曲率变化率为核心的能量函数，并引入罚函数法对控制点进行迭代优化，旨在最小化整体曲率波动。
##### 局部连续约束
- 在每一节点向量处施加曲率变化率左右导数连续性的约束条件，以增强曲线在局部与整体上的光滑连续性。

</div>
<div class="project-grid">
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/CurveFair/1.png?raw=true" alt="CurveFair">
    </div>
</div>

### 基于引导线的Gordon曲面构造

<div class="project-description">

#### 项目背景
- 面向工程中大尺度、复杂边界的船壳设计需求，致力于解决高质量曲面生成的关键难题。

#### 主要工作
##### 曲面等参线构造
- 本项目采用 Coons 曲面构造方法，通过曲面与船舶内部线求交点并结合重构插值与拟合算法，引入切向约束条件，提升了曲面边界的连续性和整体光滑性，改善了生成曲面的质量。
##### 集成化几何函数库开发
- 基于 OCCT 几何开源库，自主开发并集成了涵盖曲线排序、采样、几何裁剪、自交检测等关键功能的数学函数库，成功完成了曲面构造的数据预处理与后期处理。
##### 项目成果
- 该算法已成功应用于船壳曲面构建，生成的曲面质量优秀，得到了良好的产品反馈，并有效提升了设计与制造效率。
</div>

<div id="gordon-surface" class="project-grid">
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Gordon/Gordon_1.png?raw=true" alt="Gordon1">
    </div>
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Gordon/Gordon_2.png?raw=true" alt="Gordon2">
    </div>
</div>

<div class="project-description">

### 基于离散曲线曲面的求交算法实现        

#### 项目背景
- 针对复杂几何造型中曲线与曲面、以及曲面间求交问题的普遍需求，实现通用的求交算法框架
#### 主要工作
##### 参数域离散化求交
- 采用基于参数域划分的离散化策略，将输入曲线及曲面分别转换为线段集合与三角面片集合。通过计算这些离散元素间的交点交线，来逼近原始连续几何体求交结果
##### R树空间索引优化
- 引入 R 树空间索引结构，对大规模三角面片集合间的求交过程进行加速。在面片数量急剧增加的复杂场景下，R 树能够显著提升求交运算的效率
##### 交互式可视化与自动化测试
- 基于 Qt 应用框架与 OCCT 几何造型内核，开发了交互式的可视化功能，实现了求交过程及结果的全流程动态展示与分析。结合 PostgreSQL 数据库与 Google Test 测试框架，构建了一套几何算法自动化测试框架，实现对用例的自动化测试
</div>
<!-- 图片预览模态框 -->
<div id="imagePreviewModal" class="image-preview-modal" onclick="closeImagePreview(event)">
    <span class="close-btn" onclick="closeImagePreview(event)">&times;</span>
    <img id="previewImage" src="" alt="Preview">
</div>

<div class="project-grid">
    <div class="project-card" onclick="showImagePreview(this)">
        <img src="https://github.com/BesTLP/bestlp.github.io/blob/main/static/assets/img/Intersect/Intersect_1.png?raw=true" alt="Intersect">
    </div>
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