# BD7OVY 个人站点

GitHub Pages 用户站点，根目录为个人主页，子目录承载独立项目。

## 目录结构
- `/` — 个人主页（某的自留地）：`index.html` + `style.css`
- `/STR Analysis/` — 短租经营分析工作台（STR Analysis）

## STR Analysis 工作台
汽车短租租赁业务的经营分析单页应用。

- 纯前端单文件应用，数据在浏览器本地解析与计算，不上传任何服务器。
- 顶部导航：`导入数据` / `订单分析` / `周数据环比` / `月数据环比` / `城市平台订单明细`，点击平滑滚动到对应板块。
- 月份筛选：切换任意月份，实时计算该月的订单数、GMV、客单价、环比、Top 城市/平台、状态分布、日趋势。
- 导入数据：上传归一化后的订单 Excel（统一表头）或 JSON 即可替换示例数据。

访问地址：https://bd7ovy.github.io/STR%20Analysis/

### 文件
- `STR Analysis/index.html` — 应用本体（内联 CSS/JS，零构建）。
- `STR Analysis/data.json` — 示例数据（四平台归一化订单），由本地 Python 管线生成。

### 刷新数据
示例数据来自本地管线 `数据分析工作台/2_运行脚本/generate_dashboard.py`。
重新生成 `data.json` 后提交即可更新线上数据：
```
python generate_dashboard.py   # 生成 3_报表产出/unified_orders.json
cp 3_报表产出/unified_orders.json "STR Analysis/data.json"
git add "STR Analysis/data.json" && git commit -m "update STR data" && git push
```
