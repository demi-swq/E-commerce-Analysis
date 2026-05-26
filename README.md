# E-commerce-Analysis
# 电商用户行为数据分析与优化策略

## 项目简介

本项目基于公开的电商点击流数据集，使用 **Python** 进行数据清洗、漏斗分析、流失诊断、RFM 用户分层，并使用 **Tableau** 制作交互式看板。项目旨在通过数据驱动的方法，识别用户转化瓶颈，挖掘高价值用户，并提出可落地的运营建议。

## 数据集

- **来源**：Kaggle – [E-commerce Transactions + Clickstream](https://www.kaggle.com/datasets/wafaaelhusseini/e-commerce-transactions-clickstream/)
- **时间范围**：2020-01-01 至 2025-11-01（模拟数据）
- **核心表**：events (76万行行为日志)、sessions、orders、order_items、products、customers、reviews

## 分析内容

1. **数据清洗与会话构建**  
   - 过滤有效事件类型（page_view, add_to_cart, checkout, purchase）  
   - 按 `session_id` 聚合，标记每个会话是否经历各漏斗阶段

2. **购买漏斗与转化率分析**  
   - 计算整体漏斗转化率（浏览→购买 27.98%）  
   - 识别最大流失环节：加购→结账（流失率 44.91%）  
   - 按设备、来源、国家拆解流失率，发现流失为通用性问题

3. **商品维度深度诊断**  
   - 筛选出 1197 个需要重点优化的商品（加购后无结账）  
   - 分析高流失商品的价格区间分布（均匀无聚集）  
   - 按品类统计加购流失率（45% 左右，差异微小）

4. **客单价分析**  
   - 国家维度：南非、波兰客单价最高（145+ USD）  
   - 设备与来源：移动端略高，推荐渠道用户消费能力最强

5. **RFM 用户分层**  
   - **传统 RFM**（基于订单金额）：高价值用户占 5.5%，低价值用户占 45.7%  
   - **行为 RFM**（基于行为总次数）：挖掘出 3.4% 的高活跃潜力用户  
   - 输出各层级画像及差异化运营策略

6. **可视化看板**  
   - 使用 Tableau 制作漏斗图、流失率条形图、客单价地图、RFM 分层饼图等  
   - 看板截图见 `dashboard/` 文件夹

## 目录结构

- `data/` - 原始数据（因文件较大未上传，可自行下载）
- `电商分析.ipynb` - Jupyter Notebook 主分析代码
- `output/` - 输出结果
  - `analysis_output.xlsx` - 汇总表（10个Sheet）
  - `funnel_analysis.csv`
  - `dashboard_data.csv`
- `dashboard/` - Tableau 看板文件及截图
- `电商分析报告.docx` - 完整分析报告
- `README.md` - 项目说明

