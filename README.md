## 代码步骤简要v0.1
1. 生成density map，会有很多个density值
2. 根据不同的density生成isoValue对应的contour
3. 找到应该保留的最外层contour
4. 根据最外层contour找到centroids，将最外城contour分成sampleNum份，再根据centroids和centroid对应的射线，求出与最外层contour的交集，根据交点插值生成里层的contourNum个contour
5. 遍历当前所有点，找到最近的contour上的最近的点，在contour上根据最近的点生成winglets的左边与右边（其实就是左右端点），然后根据向量计算，分别找到contour上左右点对应的原有点处的左右点，这样就可以根据原有点处的左右点生成满足对应contour弧度的位于原有点处的winglets
6. 根据第五步生成的点使用d3来画线段

## 要安装的python包
- tornado
- pymongo
- numpy
- scipy
- scikit-image
- sklearn
- shapely
- seaborn



## 接口

### 数据导入
- 数据库-mongodb
- 从传入相应格式的数组

### 效果
- 只展示散点图
