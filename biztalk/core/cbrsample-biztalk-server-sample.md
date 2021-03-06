---
title: CBRSample （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, routing
- messages, filters
- outbound maps
- examples, messages
- messages, routing
- examples, outbound maps
- examples, filters
- messages, examples
ms.assetid: 8fba494c-9257-4eed-8b6a-867056147c2c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f850f3f64fbc13596c5548fadf57c5055052a244
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357587"
---
# <a name="cbrsample-biztalk-server-sample"></a>CBRSample （BizTalk Server 示例）
CBRSample 示例演示如何应用筛选器和出站映射来转换和基于内容的路由实例消息。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示一个包含名称、 地址和联系人信息与基于国家/地区代码的两个文件夹之一的消息的路由。 具体而言，此示例执行以下任务：  

1.  定义示例消息格式包含有关的基本信息包括用户 ID 和完整的名称，与国家/地区代码和电话联系信息的地址的标识，一个人。  

2.  促进**国家/地区代码**这样它可以在端口筛选器控制转换和路由中使用的输入文档中的属性。  

3.  消息转换为加拿大版本时**国家/地区代码**等于 200 或美国版本时**国家/地区代码**等于 100。 这两个转换传递除中间的所有数据初始 (**初始**)。 加拿大版本还会将映射**状态**到**省**并**ZipCode**到**PinCode**。  

4.  将美国的消息路由到 US 目录，将来自加拿大的消息到 CAN 目录。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 本设计依赖于默认发送和接收 XML 管道、 属性升级、 订阅筛选器和出站映射内的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来路由消息。 下表显示了设计元素及其选入理由。  


|        设计元素        |                                                                                                          选择的原因                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 默认 XML 接收管道 | XMLReceive 管道支持属性升级;PassThruReceive 管道却没有。<br />-入站的消息已采用 XML 格式，并且不需要除基本拆装和参与方解析之外的处理。 |
|      属性升级      |          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]根据属性字段进行路由。 可分辨的字段由业务流程使用，并且不能用于路由。           |
|     订阅筛选器      |                                                -订阅筛选器执行实际的路由通过捕获符合基于属性的字段的一个或多个条件的消息。                                                |
|         出站映射         |                                                     -映射将数据从一种格式之间转换。 该示例将入站的消息映射到美国或加拿大格式。                                                      |
|         XMLTransmit          |                                                         -执行基本组装传出 XML 消息;PassThruTransmit 管道未提供其他支持。                                                          |

 此基本模式可以进行扩展和用于更复杂的方案。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于 <`Samples Path>`\Messaging\CBRSample\\。  

 下表显示了本示例中的文件及其用途说明：  

|文件|Description|  
|---------------|-----------------|  
|CBRDataCAN.Xml, CBRDataUS.Xml|与文件 CBRInputSchema.xsd 中定义的架构相符的示例输入的文件。|  
|Cbrinput2canmap.btm、cbrinput2usmap.btm|分别映射文件适用于加拿大和美国格式转换。|  
|CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd|架构文件的输入的格式、 加拿大输出格式和美国输出格式，分别。|  
|CBRPromotedPropertySchema.xsd|与相对应的升级属性架构文件**国家/地区代码**元素在 XML 输入文件。|  
|CBRSample.btproj, CBRSample.sln|此示例的 BizTalk 项目和解决方案文件。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除。 删除发送和接收端口。 根据需要删除 Internet 信息服务 (IIS) 虚拟目录。|  
|Setup.bat|用于生成和初始化本示例。|  

## <a name="how-to-use-this-sample"></a>如何使用此示例  
 本示例用作基于内容将消息路由所需的操作的可运行示例。  

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 生成并初始化 CBRSample 示例，您需要生成和部署本示例中，在 BizTalk 项目配置接收端口和位置，并配置两个不同的发送端口。  

#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>若要生成和部署此示例的 BizTalk 项目  

1. 在命令窗口中，导航到以下文件夹：  

    `<Samples Path>` **\Messaging\CBRSample**  

2. 运行**Setup.bat**，该文件将执行以下操作：  

   - 创建输入 (**中**) 和输出文件夹 (**美国**并**可以**) 为本示例。  

   - 编译并部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  

   > [!NOTE]
   >  本示例将显示以下警告时创建并绑定端口：  
   > 
   >  **警告：接收处理程序没有为指定接收位置"CBRReceiveLocation;更新第一个接收处理程序具有匹配传输类型。**  
   > 
   >  可以放心地忽略此警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  
   > 
   > [!NOTE]
   >  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
   > 
   > [!NOTE]
   >  如果你选择打开并生成本示例中的项目不运行 Setup.bat 的情况下，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
   > 
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a>若要准备配置接收端口和位置，以及发送端口  

1.  在中**Microsoft SQL Management Studio**，选择正确的 BizTalk 管理数据库。  

    > [!NOTE]
    >  BizTalk 管理数据库也称为 BizTalk 配置数据库。  

#### <a name="to-configure-enlist-and-start-the-us-send-port"></a>若要配置、 登记并启动 U.S.发送端口  

1.  在 BizTalk Server 管理控制台中，展开**发送端口**，右键单击**CBRUSSendPort**，然后单击**编辑**。  

2.  在中**静态单向发送端口属性**对话框中，对话框中，左侧的文件夹树中选择**筛选器和映射&#124;筛选器**，然后通过设置将添加一个新行**属性**到**CBRSample.CountryCode**、 离开**运算符**列设置为**==**，并设置**值**列与**100**。  

3.  在文件夹树中左侧的对话框中，选择**筛选器和映射&#124;出站映射**，将**要应用的映射**属性设置为**CBRSample.CBRInput2USMap**，然后单击**确定**。 您可能需要单击滚动按钮才能显示映射到视图。  

#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a>若要配置、 登记并启动 Canadian 发送端口  

1. 在 BizTalk Server 管理控制台中，展开**发送端口**，右键单击**CBRCANSendPort**，然后单击**编辑**。  

2. 在中**静态单向发送端口属性**对话框中，对话框中，左侧的文件夹树中选择**筛选器和映射&#124;筛选器**，然后通过设置将添加一个新行**属性**到**CBRSample.CountryCode**、 离开**运算符**列设置为**==**，并设置**值**列与**200**。  

3. 在文件夹树中左侧的对话框中，选择**筛选器和映射&#124;出站映射**，将**要应用的映射**属性设置为**CBRSample.CBRInput2CANMap**然后单击**确定**。  

   以下步骤连接到接收端口的发送端口。 此示例使用升级属性，以将这些文档路由。  

   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是现在便可使用本示例。  

## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 CBRSample 示例。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1. 将输入的文件中，复制**CBRDataCAN.xml**并**CBRDataUS.xml**，到以下输入文件夹：  

    `<Samples Path>` **\Messaging\CBRSample\In**  

2. 观察如何转换每个文件和两个路由到下列任一输出值的基础的文件夹及其**国家/地区代码**元素 (100 与 200):  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将转换并将输入的文件的路由**CBRDataCAN.xml**文件夹：  

      `<Samples Path>` **\Messaging\CBRSample\CAN**  

   - BizTalk Server 将转换并将输入的文件的路由**CBRDataUS.xml**文件夹：  

      `<Samples Path>` **\Messaging\CBRSample\US**  

## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 无。  

## <a name="see-also"></a>请参阅  
 [默认管道](../core/default-pipelines.md)   
 [如何配置发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [消息传送（BizTalk Server 示例文件夹）](../core/messaging-biztalk-server-samples-folder.md)