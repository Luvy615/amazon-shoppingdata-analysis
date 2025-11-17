# amazon-shoppingdata-analysis
使用Python的Pandas对亚马逊购物产品信息进行数据清洗和分析，最后使用matplotlib将分析结果进行可视化展示。
## 使用方法
### 1.确保已安装必要的依赖库
```python
pip install numpy pandas matplotlib
```
### 2.修改代码中的数据路径
```python
df_cate = pd.read_csv(r'你的路径/amazon_categories.csv')
df_pro = pd.read_csv(r'你的路径/amazon_products.csv')
```
## 功能说明
### 1.数据读取与合并：读取商品信息和分类信息并进行合并
### 2.数据清洗：
  - 缺失值处理
  - 重复值去除
  - 异常值检测与处理（基于 IQR 方法）
  - 数据类型转换与合理性校验
### 3.特征工程：
  - 生成评级分类、价格分段等衍生特征
  - 计算折扣率和商品热度指标
### 4.数据可视化：通过饼图和柱状图展示关键指标分布
### 5.业务指标统计：计算并输出核心业务指标
### 6.数据保存：将清洗后的结果保存为 CSV 文件
## 数据字段说明
| 字段名               | 含义                |
| :------------------- | :------------------ |
| asin                 | 商品编号            |
| stars                | 评级                |
| reviews              | 评论数              |
| price                | 折后价格（售价）    |
| listPrice            | 折前价格（标价）    |
| boughtInLastMonth    | 月销量              |
## 衍生特征说明
`stars_categray`：评级分类（很差、合格、良好、很好、优秀）  
`price_rate`：折扣率（折前价与折后价的差值比例）  
`price_categray`：售价分段（低价、中低价、中价、中高价、高价）  
`listPrice_categray`：原价分段（同上）  
`popularity_score`：商品热度指标（评论数与月销量的平均值）  
`sale_category`：销售状态分类（标价异常、商品下架、商品上新、正常销售）  
## 可视化内容
- 评价星级占比饼图
- 商品售价分布柱状图
- 各分类月销量分布柱状图
- 畅销品占比饼图
<img width="2879" height="1592" alt="image" src="https://github.com/user-attachments/assets/5c7c3f9a-21cc-43be-823a-7c46e7d7bbbc" />
