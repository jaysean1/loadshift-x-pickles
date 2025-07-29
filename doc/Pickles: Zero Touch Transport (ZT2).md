# Pickles: Zero Touch Transport (ZT2)
# 泡菜：零接触运输（ZT2）

## Background 背景

Pickles has an internal logistics division to handle transport of inbound (source to Pickles) and outbound (Pickles to destination) transit.

*Pickles 有一个内部物流部门，负责处理入库（从货源到 Pickles）和出库（从 Pickles 到目的地）的运输。*

We have been told that this process is quite cumbersome and the team struggles to deliver quickly or cost-effectively. They use a mixture of preferred suppliers (including Loadshift), car movement pretty much sorted, at least for outbound.

*我们被告知这个过程相当繁琐，团队在快速或经济有效地交付方面面临困难。他们使用多个优选供应商（包括 Loadshift），汽车运输基本已经解决，至少在出库方面是这样。*

Our contact at Pickles (Andrew Harris) said that there could be opportunities in salvage but there is definitely an opportunity for Loadshift to help with industrial transport, both outbound and inbound.

*我们在 Pickles 的联系人（Andrew Harris）说在残值回收方面可能有机会，但 Loadshift 在工业运输方面绝对有机会，包括出库和入库。*

Pickles no longer run on-site auctions (except occasionally at trade shows etc) - all auctions are now run online.

*Pickles 不再举办现场拍卖（除非偶尔在贸易展览等场合）- 所有拍卖现在都在线进行。*

The goal here is to develop a proposal and demo to present to Joey at Pickles (based in the US, title?). The phrase "Zero Touch Transport" is a Joey-ism. Some of his key triggers will be efficiency, "cool technology" and AI. The ideal flows should show minimal (if any) intervention from the Pickles team, but should include a "god mode" where the Pickles logistics team can monitor the progress of their customers' loads.

*这里的目标是开发一个提案和演示，向 Pickles 的 Joey（位于美国，职位？）展示。"零接触运输"这个短语是 Joey 的用词。他的一些关键触发点是效率、"酷技术"和 AI。理想的流程应该显示 Pickles 团队的最少（如果有的话）干预，但应该包括一个"上帝模式"，让 Pickles 物流团队可以监控其客户货物的进度。*

The current Pickles transport request form is pretty basic (see below)

*目前 Pickles 的运输请求表单相当基础（见下文）* 



## Flow 1: Outbound Customer - Pre-purchase Estimate
## 流程 1：出库客户 - 购买前评估

### Scenario 场景

Customer John Smith from Temora, NSW is interested in a JDC Thomson Powerlite Generator at auction for his canola farm. His max budget is $20K. The auction details specify that he must collect the item within 3 days of purchase. The item is stored at Pickles warehouse in Belmore, Sydney NSW.

*来自新南威尔士州 Temora 的客户 John Smith 对拍卖中的 JDC Thomson Powerlite 发电机很感兴趣，用于他的油菜农场。他的最高预算是 2 万澳元。拍卖详情规定他必须在购买后 3 天内取走物品。该物品存储在悉尼新南威尔士州 Belmore 的 Pickles 仓库中。*

He is a bit worried about this, as he has no way of getting the item to his farm. It's big and he hasn't got a truck that is big enough to handle it.

*他对此有些担心，因为他没有办法把物品运到农场。物品很大，他没有足够大的卡车来处理。*

### Prior to the auction (Sunday)
### 拍卖前（周日）
#### Quote Process Steps

1. **Customer initiates quote request**
   - Customer locates the item on the Pickles website
   - *客户在 Pickles 网站上找到该物品*
   - Clicks the "Free Shipping Quote" button on the page
   - *点击页面上的"免费运输报价"按钮*

2. **Redirect to co-branded platform**
   - Customer is redirected to pickles.loadshift.com.au, a co-branded landing page
   - *客户被重定向到 pickles.loadshift.com.au，一个共同品牌的着陆页*
   - Form available to complete delivery details
   - *有表单可完成配送详情*

3. **Pre-populated data from Pickles website**
   - The load details *货物详情*
   - The origin address *起始地址*
   - Customer information (name, phone number, address)
   - *客户信息（姓名、电话号码、地址）*
   - Load specifications (item, dimensions, weight)
   - *货物规格（物品、尺寸、重量）*
   - Auction date and delivery timeframe
   - *拍卖日期和配送时间*

   **Note:** If dimensions and weight are missing, we use LLM to retrieve these details
   *注意：如果缺少尺寸和重量，我们会尝试用 LLM 检索这些详情*

4. **AI assistance and confidence building**
   - AI agent pops up to help complete any missing details we haven't been able to infer
   - *AI代理弹出来帮助客户完成我们无法推断的任何详情*
   - Interactive map showing the route with carriers dotted around the origin point (Uber style) to build confidence
   - *显示详细路线的地图，承运商分布在起始点周围（Uber风格）以建立信心*

5. **Initial quote generation**
   - Customer clicks "Get Free Quote" button
   - *客户点击"获取免费报价"按钮*
   - System instantly shows estimated range based on ML model
   - *基于ML模型立即显示估计范围*
   - System detects unusual items requiring additional transport licenses from photo analysis
   - *基于物品照片检测到不寻常物品需要额外运输许可证*

6. **Detailed estimate process**
   - Customer chooses to receive detailed estimate
   - *客户选择接收详细估计*
   - Triggers estimate-only load on Loadshift
   - *在Loadshift上触发仅估计的载货*
   - Customer informed of 60-minute quote turnaround
   - *告知客户60分钟内提供报价*

7. **Carrier matching and quote assembly**
   - Loadshift Pickles Ops Centre receives request
   - *Loadshift Pickles运营中心接收请求*
   - Contacts Pickles-certified carriers
   - *联系认证的Pickles承运商*
   - Within 60 minutes, assembles marketplace quotes
   - *60分钟内从市场收集报价*
   - Selects three options:
     - The cheapest *最便宜的*
     - The fastest (delivery) *最快的（配送）*
     - The highest-rated *评分最高的*

8. **Quote delivery and selection**
   - Customer receives SMS notification that quotes are ready with viewing link
   - *客户收到短信告知报价已准备好，附带查看链接*
   - Customer reviews quotes (driver, truck, rating)
   - *客户查看报价（司机、卡车、评分）*
   - Selects cheapest option: $927 (including Loadshift platform fees)
   - *选择最便宜选项：927澳元（包括Loadshift平台费用）*

**Result:** John is now ready to attend the auction with confidence.
*结果：John现在准备好满怀信心地参加拍卖。*

## Flow 2: Outbound Customer - Quote to Delivery
## 流程 2：出库客户 - 报价到配送

### After the auction (Monday)
### 拍卖后（周一）

**Context:** John has successfully purchased the generator at the Monday auction for $17,500. He is happy as this is going to solve a lot of problems on his farm, but is still a bit worried about the transport.

*背景：John 在周一的拍卖中以 17,500 澳元成功购买了发电机。他很高兴，因为这将解决他农场的许多问题，但对运输仍有些担心。*

#### Delivery Confirmation Process

1. **AI Agent Confirmation Call**
   - AI Agent calls the customer's phone to confirm:
   - *AI 代理致电客户确认：*
     - That he has bought the item *他已购买物品*
     - He still needs shipping *他仍需要运输*
     - He is happy with the provider that he previously selected (the cheapest option)
     - *他对之前选择的供应商（最便宜的选项）满意*

2. **Updated Requirements**
   - Customer indicates that he actually needs delivery by the weekend
   - *客户表示他实际上需要在周末前配送*
   - AI agent updates the load details and posts it as an "Urgent" load
   - *AI 代理更新货物详情并将其发布为"紧急"货物*

3. **Customer Portal Access**
   - Customer receives SMS confirming his load with a link to a standalone page
   - *向客户发送短信确认他的货物，附带独立页面的链接*
   - On this page he can:
   - *在此页面上他可以：*
     - View his load details *查看他的货物详情*
     - See a map of the route *查看路线地图*
     - See the number of bids and average bid amount *查看投标数量和平均投标金额*
     - See a countdown to when we will present quotes to him *查看我们向他提供报价的倒计时*
     - Chat with an AI agent to update any details *与 AI 代理聊天以更新任何详情*

4. **Carrier Matching and Quote Delivery**
   - Loadshift Pickles Ops Centre receives the request
   - *Loadshift Pickles 运营中心接收请求*
   - Contacts Pickles-certified carriers to make the match
   - *联系认证的 Pickles 承运商进行匹配*
   - Selects three carrier options:
     - Cheapest *最便宜*
     - Fastest *最快*
     - Highest-rated *评分最高*
   - Sends SMS notification that quotes are ready
   - *发送短信通知报价已准备好*

5. **Payment and Confirmation**
   - Customer selects preferred carrier and is forwarded to payment screen
   - *客户选择偏好的承运商并转向付款界面*
   - Customer prompted to enter payment details with UI explaining funds escrow
   - *客户被提示输入付款详情，UI解释资金托管运作方式*
   - After payment, redirected to confirmation page showing:
   - *付款后，重定向到确认页面显示：*
     - The load *货物*
     - The route *路线*
     - The driver *司机*
     - Estimated pickup time *预计取货时间*
     - Estimated delivery time *预计配送时间*
     - Button to get help *获取帮助按钮*

6. **Job Acceptance**
   - Carrier accepts job
   - *承运商接受工作*

### Day of Pickup (Wednesday)
### 取货日（周三）

#### Pickup Process Flow

1. **Pre-pickup Preparation**
   - Driver receives SMS reminder with pickup location and time details
   - *司机收到短信提醒，包含取货地点和时间详情*

2. **Arrival and Security Verification**
   - Driver arrives at Pickles facility
   - *司机到达 Pickles 设施*
   - At the gate, security guard scans QR code from driver's Loadshift app
   - *在门口，保安扫描司机 Loadshift 应用程序的二维码*

3. **QR Code Verification System**
   - QR code directs security guard to verification page showing:
   - *二维码将保安带到显示以下内容的验证页面：*
     - **Driver details** *司机详情*
       - Driver's license number *驾驶证号码*
       - Photo *照片*
       - Special certifications/licenses *特殊认证/许可证*
       - Pickles certification *Pickles 认证*
     - **Truck details** *卡车详情*
       - License plate *车牌号*
       - Description *描述*
       - Features *特征*
     - **Load details** *货物详情*

4. **Security Clearance and Direction**
   - Security guard confirms all details
   - *保安确认所有详情*
   - Directs driver to designated pickup bay
   - *指引司机到指定取货区*

5. **Load Documentation and Handling**
   - Driver opens Loadshift app and navigates to correct load
   - *司机打开 Loadshift 应用程序并导航到正确的货物*
   - Takes photo of load and uploads to Loadshift
   - *为货物拍照并上传到 Loadshift*
   - Loads item onto truck
   - *将物品装载到卡车上*
   - Uploads video of load on truck back, capturing all angles to show undamaged condition
   - *上传卡车后部货物的视频，拍摄所有角度显示货物未损坏*

6. **Departure and Customer Notification**
   - Driver taps "I'm on my way" button, initiating GPS tracking
   - *司机点击"我在路上"按钮，GPS 跟踪开始*
   - AI Agent calls customer to confirm delivery is en route
   - *AI 代理致电客户确认配送正在进行中*
   - Customer receives SMS with link to:
   - *客户收到带链接的短信以便：*
     - View photos and videos from pickup (including driver's thumbs-up selfie)
     - *查看取货的照片和视频（包括司机竖起大拇指的自拍）*
     - Track load location via GPS (departed Pickles yard, long journey ahead)
     - *通过 GPS 跟踪货物位置（已离开 Pickles 仓库，前方路程很长）*
### Day of Delivery (Thursday)
### 配送日（周四）

#### Delivery Process Flow

1. **Pre-delivery Coordination**
   - Customer receives phone call from driver (via Loadshift app) requesting access instructions to delivery site
   - *客户接到司机的电话（通过 Loadshift 应用程序）询问进入配送地点的指示*
   - Customer goes to meet driver at the gate
   - *客户到门口与司机会面*

2. **On-site Arrival Documentation**
   - Driver arrives on site
   - *司机到达现场*
   - Takes photos/videos of the load
   - *为货物拍照/录像*
   - Marks status as "Arrived" in app
   - *在应用程序中标记状态为"已到达"*

3. **Unloading and Placement**
   - Driver uses crane to lift load off truck and position into place
   - *司机用起重机将货物从卡车后部吊下并放置到位*
   - Takes comprehensive photos/videos of placed load
   - *为放置好的货物拍摄全面的照片/视频*
   - Marks job status as "Complete" in system
   - *在系统中标记工作状态为"完成"*

4. **Customer Sign-off Process**
   - Customer receives SMS with link for delivery sign-off
   - *客户收到带签收链接的短信*
   - Customer reviews images/videos of the delivered load
   - *客户查看已配送货物的图像/视频*
   - Confirms job completion satisfaction
   - *确认对工作完成的满意度*
   - Signs digitally with finger signature
   - *用手指进行数字签名*
   - Clicks 'Complete payment' button to release funds
   - *点击"完成付款"按钮释放资金*

5. **Payment Confirmation**
   - Driver receives confirmation that payment has been processed
   - *司机确认已收到款项*

6. **Post-delivery Feedback**
   - AI Agent makes follow-up call to customer for feedback and testimonial
   - *AI 代理致电客户获取反馈和推荐*
   - Customer expresses satisfaction with timely, damage-free delivery
   - *客户对按时且无损坏的配送表示满意*
   - Positive experience converts to 5-star driver review
   - *积极体验转化为司机的五星评价* 

## Flow 3: God-mode Dashboard
## 流程 3：上帝模式仪表板

### Overview
### 概述

Pickles will need to be able to view the status and location of any job that is passed through to us. We will build a comprehensive dashboard for their logistics team to use on a daily basis.

*Pickles 需要能够查看通过我们处理的任何工作的状态和位置。我们将为他们的物流团队构建一个全面的仪表板供日常使用。*

### Dashboard Components
### 仪表板组件

#### 1. Kanban-style Job Status Board
#### 1. 看板式工作状态面板

- **Job categorization by status:**
- **按状态分类工作：**
  - Estimate *估价*
  - Quote *报价*
  - In transit *运输中*
  - Delivered *已配送*
  - Cancelled *已取消*

- **Column summary metrics:**
- **列汇总指标：**
  - Number of loads *货物数量*
  - Total value *总价值*
  - Total distance *总距离*

#### 2. Real-time Location Tracking
#### 2. 实时位置跟踪

- Interactive map showing locations of in-transit loads
- *显示运输中货物位置的交互式地图*
- Live GPS tracking for active deliveries
- *活跃配送的实时 GPS 跟踪*

#### 3. Search and Filter Functionality
#### 3. 搜索和筛选功能

- **Search capabilities:**
- **搜索功能：**
  - Customer name *客户姓名*
  - Pickles item ID *Pickles 物品 ID*
  - Driver details *司机详情*
  - Date ranges *日期范围*

#### 4. Detailed Load View
#### 4. 详细货物视图

- Comprehensive load information matching customer portal view
- *与客户门户视图匹配的全面货物信息*
- Photo and video documentation from pickup and delivery
- *取货和配送的照片和视频文档*
- Timeline of all job activities
- *所有工作活动的时间线*

#### 5. Revenue Analytics Dashboard
#### 5. 收入分析仪表板

- **Financial tracking:**
- **财务跟踪：**
  - Money earned by Pickles from revenue share
  - *Pickles 从收入分成中赚取的资金*
  - Monthly/quarterly revenue trends
  - *月度/季度收入趋势*
  - Performance metrics by route and carrier
  - *按路线和承运商的绩效指标*

#### 6. Support and Communication
#### 6. 支持和沟通

- In-app hotline to the Loadshift Ops Centre
- *应用内 Loadshift 运营中心热线*
- Direct messaging with drivers and customers
- *与司机和客户的直接消息传递*
- Escalation protocols for issues
- *问题升级协议*

#### 7. Operational Intelligence
#### 7. 运营智能

- **Performance indicators:**
- **绩效指标：**
  - Average delivery times
  - *平均配送时间*
  - Customer satisfaction scores
  - *客户满意度评分*
  - Carrier reliability ratings
  - *承运商可靠性评级*
  - Issue resolution metrics
  - *问题解决指标*








