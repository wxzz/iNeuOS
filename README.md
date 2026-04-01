# iNeuOS 基本功能介绍 V5

> 文档来源：manual/iNeuOS_基本功能介绍_V5_20260401.docx

# 框架设计

## 整体框架

根据项目需求，整体包括：边缘设备、物联网服务、前后端框架和系统应用模块。框架如下图：

![整体框架](https://github.com/wxzz/iNeuOS/blob/master/image/1.%E6%95%B4%E4%BD%93%E6%A1%86%E6%9E%B6.png)

图 整体框架

# 技术路线

## 工业互联网系统平台

系统平台具备操作系统的特点：即接、即用、即分析、即显示，开放式的二次开发；从以数据为中心的角度看，数据流程化应用：设备驱动（数据交互驱动）、服务驱动（数据事务处理驱动）、设备模型（设备实时通信及处理）、业务模型（数据分组建模）、资产模型（数据空间规则提取）、计算平台（数据计算与预警）、数据分析、数据转发、视图建模（2D/3D数据展示）、视频转换（视频数据展示）、流程控制（数据反向操作）、算法分析（数据算法分析）、Excel报表设计（数据报表模板设计与应用）、表单应用开发（应用界面功能开发）、大模型应用、设备运维、能源管理和用户权限等。

![整体框架](https://github.com/wxzz/iNeuOS/blob/master/image/2.%E5%B7%A5%E4%B8%9A%E4%BA%92%E8%81%94%E7%BD%91%E7%B3%BB%E7%BB%9F%E5%B9%B3%E5%8F%B0.png)

### 设备驱动

支持物联网设备驱动的二次开发和设备驱动上传、编辑和删除等管理。如下图：

![设备驱动](https://github.com/wxzz/iNeuOS/blob/master/image/3.%E8%AE%BE%E5%A4%87%E9%A9%B1%E5%8A%A8.png)

图 设备驱动管理和上传

### 服务驱动

支持物联网服务驱动的二次开发和服务驱动上传、编辑和删除等管理，主要面向复杂数据处理、分析等应用场景。如下图：

![设备驱动管理和上传](https://github.com/wxzz/iNeuOS/blob/master/image/4.%E6%9C%8D%E5%8A%A1%E9%A9%B1%E5%8A%A8.png)

图 服务驱动管理和上传

### 设备模型

支持以物理世界构建物联网映射系统，支持设备驱动和服务驱动的配置、管理和运行，包括设备信息、数据点、计算预警。如下图：

![服务驱动管理和上传](https://github.com/wxzz/iNeuOS/blob/master/image/5.%E8%AE%BE%E5%A4%87%E6%A8%A1%E5%9E%8B.png)

图 设备数据采集

### 业务模型

支持根据业务重构设备及数据逻辑关系，支持复杂业务模型，如下图：

![设备数据采集](https://github.com/wxzz/iNeuOS/blob/master/image/6.%E4%B8%9A%E5%8A%A1%E6%A8%A1%E5%9E%8B.png)

图 业务模型

### 计算平台

支持数学运算符和函数对数据点进行复杂的计算，支持创建多个计算任务，支持逻辑规划推理，并对结果进行消息推送，如下图：

![业务模型](https://github.com/wxzz/iNeuOS/blob/master/image/7.%E8%AE%A1%E7%AE%97%E5%B9%B3%E5%8F%B0.png)

图 实时计算

### 实时预警

实现数据点、设备和计算平台的计算预警，数据点只对单独数据点、设备是对当前设备范围的数据点、计算平台是对当前平台的所有数据点。数据点和设备的计算，只要数据更新就会触发计算。

预警间隔：多长时间（秒）执行一次逻辑判断脚本。

预警延迟：逻辑判断脚本为真的次数大于等于预警延迟才进行消息推送，如果小于预警延迟期间逻辑判断脚本为假，那么重新计数。

预警提示：预警推送的提示信息。

![实时计算](https://github.com/wxzz/iNeuOS/blob/master/image/8.%E5%AE%9E%E6%97%B6%E9%A2%84%E8%AD%A6.png)

### 数据查询

支持以图型和列表的形式查询数据，支持图型和列表数据的导出，如下图：

![数据查询](https://github.com/wxzz/iNeuOS/blob/master/image/9.%E6%95%B0%E6%8D%AE%E6%9F%A5%E8%AF%A2.png)

![数据查询](https://github.com/wxzz/iNeuOS/blob/master/image/10.%E6%95%B0%E6%8D%AE%E6%9F%A5%E8%AF%A2.png)

图 数据查询

### 数据转发

可以选择自定义数据点，把数据点通过网络转发到其他系统中，如下图：

![数据查询](https://github.com/wxzz/iNeuOS/blob/master/image/11.%E6%95%B0%E6%8D%AE%E8%BD%AC%E5%8F%91.png)

图 数据转发

### 视图建模

以物联网的数据为基础，视图建模负责构建数据的监测和应用，其主要特点包括：

支持5500多个行业矢量图元元素

支持配置第三方数据接口与图元联动

支持对外接口，推送数据到平台与图元联动

支持适配不同屏幕的分辨率，构建组态显示页

支持自定义规则，进行预警、改变颜色、跳动、旋转等

支持配置右键菜单打开内部应用和外部链接

支持编辑好的页面分享二维码和链接

支持下发控制命令，与设备容器联动控制设备

丰富的图表功能

支持3D模型的导入和绑定数据点

视图建模应用，如下图：

![数据转发](https://github.com/wxzz/iNeuOS/blob/master/image/12.%E8%A7%86%E5%9B%BE%E5%BB%BA%E6%A8%A1.png)

### 机器学习

支持通用机器学习算法（决策树和聚类）和集成自定义模型算法，对工况的多维数据空间训练模型，提取工况对应的规则，结合数据空间的实时数据预测对应的工况。如下图：

![机器学习](https://github.com/wxzz/iNeuOS/blob/master/image/13.%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0.png)

图 机器学习

### 视频转换

提供了在线实时视频流转换服务，把rtsp协议转换成rtmp协议或websocket协议，满足低延时实时在组态上显示视频流的需求。工业场景矢量园元、图表和视频可以集成到一个组态页面上展示。如下图：

![机器学习](https://github.com/wxzz/iNeuOS/blob/master/image/14.%E8%A7%86%E9%A2%91%E8%BD%AC%E6%8D%A2.png)

图 视频服务

### 消息管理

支持预警和系统消息查询，如下图：

![视频服务](https://github.com/wxzz/iNeuOS/blob/master/image/15.%E6%B6%88%E6%81%AF%E7%AE%A1%E7%90%86.jpeg)

图 消息管理

### 流程控制

工艺优化联动控制支持在线开发业务脚本，支持多个生产过程联动控制任务， 脚本引擎支持内置函数：控制命令（ctrl）、控制延迟（delay）、获得当前参数（getpara）、保存中间变量值（save）、控制启动（start）、控制停止（stop）、最新数值（getvalue）和打印日志（log）。如下图：

![消息管理](https://github.com/wxzz/iNeuOS/blob/master/image/16.%E6%B5%81%E7%A8%8B%E6%8E%A7%E5%88%B6.png)

图 流程控制

### 控制日志

可以查询手动和自动控制操作过程记录信息。如下图：

![流程控制](https://github.com/wxzz/iNeuOS/blob/master/image/17.%E6%8E%A7%E5%88%B6%E6%97%A5%E5%BF%97.png)

### 用户权限

增加、编辑和删除用户，权限有：工具权限、应用权限和数据点权限。如下图：

![用户权限](https://github.com/wxzz/iNeuOS/blob/master/image/18.%E7%94%A8%E6%88%B7%E6%9D%83%E9%99%90.png)

图 用户权限

### 实时日志

可以实时查看后台服务运行和调试过程，如下图：

![用户权限](https://github.com/wxzz/iNeuOS/blob/master/image/19.%E5%AE%9E%E6%97%B6%E6%97%A5%E5%BF%97.png)

### 算法分析

选择[算法分析]按钮，会对当前数据点进行数据的基本汇总统计：数据量、均值、最大值和最小值等。还会对数据点的原始值和算法分析结果进行图形化展示，支持傅里叶变换、倒频谱、自相关、包络分析等算法。快速傅里叶变换分析结果如下图：

![算法分析](https://github.com/wxzz/iNeuOS/blob/master/image/20.%E7%AE%97%E6%B3%95%E5%88%86%E6%9E%90.jpeg)

### 在线报表

可以打开在线Excel报表，自定义配置数据展示的模板，绑定数据源及配置数据的小数位、数据显示方向、填充数位（显示多少条数据）、统计（均值、和值、最小值、最大值、中位数和众数）。如下图：

![在线报表](https://github.com/wxzz/iNeuOS/blob/master/image/21.%E5%9C%A8%E7%BA%BF%E6%8A%A5%E8%A1%A8.png)

### 表单开发

“低代码”在线表单开发工具，支持的表单组件丰富。可让用户通过拖拽配置的方式配置表单的增删查改，支持添加\更新数据唯一性验证，解放用户对于基础表，父子表、多表关联父子表的开发编辑工作。如下图

![表单开发](https://github.com/wxzz/iNeuOS/blob/master/image/22.%E8%A1%A8%E5%8D%95%E5%BC%80%E5%8F%91.png)

### 大模型应用

在【模型配置】->【新增模型】，配置Api Url和模型名称，DeepSeek默认API地址为：http://localhost:11434，本机测试的模型为：deepseek-r1:32b。如下图：

![大模型应用](https://github.com/wxzz/iNeuOS/blob/master/image/23.%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%BA%94%E7%94%A8.png)

可以配置多个智能体，每个智能体可以理解为一个具体的业务分析应用场景，例如增加一个智能体为：设备状态分析；针对该智能体再配置一个分析应用场景的提示词：正常设备温度范围是105到115；分析设备温度数据，给出设备运行状态分析结果；每个智能体可以配置不同的模型，这个智能体模型选择：deepseek-r1:32b。选择保存，就创建好了一个智能体应用。如下图：

![大模型应用](https://github.com/wxzz/iNeuOS/blob/master/image/24.%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%BA%94%E7%94%A8.png)

进入数据查询功能，查询时间范围的数据，如下图：

![大模型应用](https://github.com/wxzz/iNeuOS/blob/master/image/25.%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%BA%94%E7%94%A8.png)

单击【模型分析】，选择创建好的【智能体】：设备状态分析，会自动关联出来模型和提示词，也可以自定义选择其他模型。如下图：

![大模型应用](https://github.com/wxzz/iNeuOS/blob/master/image/26.%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%BA%94%E7%94%A8.png)

### 设备运维

设备运维业务大屏统计功能主要统计当前系统设备数量、预警设备数量、通讯正常、通讯干扰、通讯中断及按设备区域统计和统计预警信息。展示效果，如下图：

![设备运维](https://github.com/wxzz/iNeuOS/blob/master/image/27.%E8%AE%BE%E5%A4%87%E8%BF%90%E7%BB%B4.png)

### 能源管理

增加和配置工厂基本信息，并且增加该工厂的生产工序，规划工序粒度由精细化管理程序决定。如下图:

![能源管理](https://github.com/wxzz/iNeuOS/blob/master/image/28.%E8%83%BD%E6%BA%90%E7%AE%A1%E7%90%86.jpeg)

配置该工厂班制，例如一天三班制管理，主要用于统计班组数据使用。如下图：

![能源管理](https://github.com/wxzz/iNeuOS/blob/master/image/29.%E8%83%BD%E6%BA%90%E7%AE%A1%E7%90%86.jpeg)

经过上面的配置，基本实现了能源管理的实时监测统计、能源查询等功能。能源实时监测，如下图：

![能源管理](https://github.com/wxzz/iNeuOS/blob/master/image/30.%E8%83%BD%E6%BA%90%E7%AE%A1%E7%90%86.jpeg)

能源数据查询，如下图：

![能源管理](https://github.com/wxzz/iNeuOS/blob/master/image/31.%E8%83%BD%E6%BA%90%E7%AE%A1%E7%90%86.jpeg)

# 联系方式
**QQ**:504547114。<br/>
**网站**:[https://www.ineuos.net](https://www.ineuos.net)<br/>
**开发团队**：iNeuOS Team。<br/>