# Pickles ZT2 零接触运输平台 - HTML页面开发计划

## 项目概述

基于《Pickles_ZT2_PRD_中文版.md》产品需求文档，将零接触运输平台的完整用户流程分解为独立的HTML页面，用于产品演示和概念验证。

### 目标
- 创建独立HTML页面，完整展示ZT2平台核心功能
- 保持设计风格一致性，体现Pickles x Loadshift联合品牌
- 通过模拟数据和交互，展示完整的用户体验流程
- 支持移动端和桌面端响应式展示


## files
`pickles.au/Pickles_ZT2_PRD_中文版.md` 完整的prd文件，按照产品文档，进行设计
`pickles.au/Pickles ZT2 Proposal - Zero Touch Transport Platform.md` 对外的proposal文档
`pickles.au/Pickles: Zero Touch Transport (ZT2).md` 业务需求文档
`doc/Pickles_ZT2_HTML开发计划.md` 开发计划文档


## design
- 作为 UI 设计师，设计贴近真实规范的界面，使用现代化的 UI 元素，使其具有良好的视觉体验.
- 使用 HTML + Tailwind CSS (或 Bootstrap) 生成所有原型界面，并使用 FontAwesome (或其他开源 UI 组件) 让界更加精美、接近真实的 App 设计
- 只有通话界面尺寸应模拟 iPhone 15 Pro，并让界面圆角化，使其更像真实的手机界面
- 使用lucide icon 组件库为产品添加icon



## 主要任务分解

### Task 1: 项目基础架构搭建
**优先级：高**

#### Subtask 1.1: 创建项目目录结构
```
pickles-zt2-demo/
├── index.html                 # 主导航页面
├── css/
│   ├── common.css            # 共享样式
│   ├── mobile.css            # 移动端适配
│   └── components.css        # 组件样式
├── js/
│   ├── common.js             # 共享JavaScript
│   ├── data-mock.js          # 模拟数据
│   └── navigation.js         # 页面跳转逻辑
├── assets/
│   ├── images/               # 图片资源
│   └── icons/                # 图标资源
└── pages/                    # 独立页面目录
    ├── client_quote.html  # 拍卖客户 - 购买前阶段 - 自动报价
    ├── phonecall_confirm.html  # 认证承运商/司机 - 用户完成bid后 - 收到ai的询单电话 
    ├── order_confirmation.html  # 拍卖客户 - 购买后阶段 - 收到报价确认
    ├── pickup_auth.html  # 认证承运商/司机 - 用户完成订单确认后 - 取货认证
    ├── god_mode.html  # loadshift 物流运营团队 - 司机完成取货后 - god mode 
    ├── delivery_complete.html  # 拍卖客户 - 收到货物 - 当面完成订单完成确认


---

### Task 2: 核心用户流程页面开发
**优先级：高**

#### Subtask 2.1: client_quote.html - 客户自动报价页面

**页面功能需求：**
- 展示预填充的物品信息（JDC Thomson发电机）
- AI智能分析进度条和结果显示
- 交互式承运商分布地图
- 即时价格范围估算
- 获取详细报价按钮和SLA承诺

**技术实现要点：**
- 使用CSS动画模拟AI分析过程
- 集成地图API显示承运商位置
- 响应式卡片布局设计
- 表单验证和数据收集

**数据模拟需求：**
```json
{
  "item": {
    "name": "JDC Thomson Powerlite Generator",
    "auction_id": "PKL2023001",
    "location": "Pickles Belmore, Sydney NSW",
    "dimensions": "2.1m×1.2m×1.5m",
    "weight": "850kg",
    "estimated_value": 17500
  },
  "quote_estimate": {
    "min_price": 850,
    "max_price": 1200,
    "distance": "412km",
    "available_carriers": 12
  }
}
```

#### Subtask 2.2: phonecall_confirm.html - AI询单电话界面

**页面功能需求：**
- iPhone样式的通话界面模拟

**技术实现要点：**
- CSS模拟iPhone通话界面
- 音频波形动画效果

#### Subtask 2.3: order_confirmation.html - 订单确认页面

**页面功能需求：**
- 订单概要信息卡片
- 承运商详细资料展示
- 时间安排和路线信息
- 费用明细和付款说明
- 确认和修改操作按钮

**技术实现要点：**
- 多卡片布局设计
- 承运商评分星级显示
- 托管付款流程说明
- 倒计时确认机制

#### Subtask 2.4: pickup_auth.html - 取货认证页面

**页面功能需求：**
- 司机端QR码生成显示
- 保安验证界面模拟
- 多角度拍照上传界面
- 装车视频上传功能
- GPS跟踪启动确认

**技术实现要点：**
- QR码生成和显示
- 相机功能模拟
- 文件上传进度显示
- 地理位置服务集成

#### Subtask 2.5: god_mode.html - 运营监控仪表板

**页面功能需求：**
- 看板式订单状态管理
- 实时地图位置跟踪
- 订单详情信息面板
- 快速操作工具栏
- 性能指标数据展示

**技术实现要点：**
- 拖拽式看板界面
- 实时数据更新模拟
- 地图标记和路线显示
- 响应式仪表板布局

#### Subtask 2.6: delivery_complete.html - 配送完成确认

**页面功能需求：**
- 配送二维码扫描界面
- 数字签名输入功能
- 配送照片查看确认
- 付款确认

**技术实现要点：**
- Canvas手写签名功能
- 图片查看器组件
- 星级评分系统
- 支付流程模拟


---


#### Subtask 3.6: index.html - 主导航页面
**备注：预留页面，后续重新设计完整流程**

**页面功能需求：**
- 待后续设计完整的页面串联流程
- 预留文件位置

---

---

## 技术栈和工具

### 前端技术
- **HTML5**: 语义化标签结构
- **CSS3**: Flexbox/Grid布局，动画效果
- **JavaScript ES6+**: 模块化开发，异步处理
- **Bootstrap 5**: 响应式框架
- **Chart.js**: 数据可视化
- **Leaflet.js**: 地图服务

### 开发工具
- **VS Code**: 代码编辑器
- **Live Server**: 本地开发服务器
- **Git**: 版本控制
- **Chrome DevTools**: 调试工具

### 设计资源
- **Google Fonts**: 字体服务
- **Font Awesome**: 图标库
- **Unsplash**: 图片素材
- **Figma**: UI设计参考

## 交付物清单

### 代码文件
- [ ] 12个HTML页面文件
- [ ] 3个CSS样式文件
- [ ] 4个JavaScript功能文件
- [ ] 1个模拟数据文件
- [ ] 1个主导航页面

### 文档资料
- [ ] 项目部署说明
- [ ] 页面功能说明
- [ ] 数据结构文档
- [ ] 用户使用指南

### 测试报告
- [ ] 功能测试报告
- [ ] 兼容性测试报告
- [ ] 性能优化报告

## 任务优先级

| 任务 | 优先级 | 说明 |
|------|--------|------|
| Task 1: 基础架构搭建 | 高 | 基础样式和目录结构 |
| Task 2: 核心页面开发 | 高 | 主要业务流程页面 |
| Task 3: 支持页面开发 | 中 | 辅助功能页面 |
| Task 4: 交互逻辑集成 | 中 | 页面间数据流转 |
| Task 5: 测试和优化 | 中 | 质量保障和优化 |

## 风险评估和应对

### 技术风险
- **风险**：移动端兼容性问题
- **应对**：使用标准Web API，降级处理

### 设计风险  
- **风险**：品牌元素不统一
- **应对**：建立设计系统，统一审核

### 进度风险
- **风险**：功能范围过大
- **应对**：MVP优先，迭代完善

## 成功标准

### 功能完整性
- ✅ 所有12个页面正常运行
- ✅ 页面间跳转逻辑正确
- ✅ 模拟数据完整展示

### 用户体验
- ✅ 移动端和桌面端适配良好
- ✅ 交互响应流畅
- ✅ 视觉设计专业统一

### 演示效果
- ✅ 完整流程演示顺畅
- ✅ 核心功能展示清晰
- ✅ 技术能力体现充分

---

*此计划文档将作为Pickles ZT2 HTML页面开发的指导性文件，所有开发工作将严格按照此计划执行，确保项目按时高质量交付。*