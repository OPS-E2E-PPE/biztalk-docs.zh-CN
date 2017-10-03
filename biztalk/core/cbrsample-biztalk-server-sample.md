---
title: "CBRSample （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b772bc44d4a745d5bfa330e7df7fcadcf2c020db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cbrsample-biztalk-server-sample"></a>CBRSample （BizTalk Server 示例）
CBRSample 示例演示如何应用筛选器和出站映射，以便基于内容转换和路由实例消息。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示如何基于国家/地区代码将包含名称、地址和联系信息的消息路由到两个文件夹之一。 具体而言，本示例执行下列操作：  
  
1.  定义包含人员相关基本信息的示例消息格式，这些基本信息包括带有用户 ID 和全名的标识、带有国家/地区代码的地址以及电话联系信息。  
  
2.  提升**国家/地区代码**输入文档以便它可以用于控制转换和路由到的端口筛选器中的属性。  
  
3.  将消息转换成加拿大版本时**国家/地区代码**等于 200 或美国版本时**国家/地区代码**等于 100。 这两个转换通过除中间之外的所有数据初始 (**初始**)。 加拿大版本还会将映射**状态**到**省**和**ZipCode**到**PinCode**。  
  
4.  将来自美国的消息路由到 US 目录，将来自加拿大的消息路由到 CAN 目录。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 本设计依赖于 BizTalk Server 中的默认发送和接收 XML 管道、属性升级、订阅筛选器和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内的出站映射来路由消息。 下表显示了设计元素及其选入理由。  
  
|设计元素|选择的原因|  
|--------------------|--------------------------|  
|默认 XML 接收管道|-XMLReceive 管道支持属性提升;PassThruReceive 管道却没有。<br />-入站的消息已在 XML 格式，并且不需要基本反汇编和参与方解析之外的处理。|  
|属性提升|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]取决于要进行路由的属性字段。 业务流程使用可分辨字段，并且该字段不能用于路由。|  
|订阅筛选器|-订阅筛选器执行实际的路由通过捕获满足基于属性的字段的一个或多个条件的消息。|  
|出站映射|贴图转换到另一个从一种格式的数据。 本示例将入站消息映射为美国或加拿大格式。|  
|XMLTransmit|-执行基本的程序集的传出的 XML 消息;PassThruTransmit 管道提供任何额外的支持。|  
  
 可对此基本模式进行扩展，将其用于更加复杂的情形。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于 <`Samples Path>`\Messaging\CBRSample\\。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|CBRDataCAN.Xml、CBRDataUS.Xml|与文件 CBRInputSchema.xsd 中定义的架构相符的示例输入文件。|  
|CBRInput2CANMap.btm、CBRInput2USMap.btm|分别适用于加拿大和美国格式转换的映射文件。|  
|CBRInputSchema.xsd、CBROutputSchemaCAN.xsd 和 CBROutputSchemaUS.xsd|分别适用于输入格式、加拿大输出格式和美国输出格式的架构文件。|  
|CBRPromotedPropertySchema.xsd|对应于已提升属性的架构文件**国家/地区代码**元素在 XML 输入文件。|  
|CBRSample.btproj、CBRSample.sln|本示例的 BizTalk 项目和解决方案文件。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。 删除发送和接收端口。 根据需要删除 Internet 信息服务 (IIS) 虚拟目录。|  
|Setup.bat|用于生成和初始化本示例。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 本示例用作基于内容路由消息所需的操作的可运行示例。  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 若要生成并初始化 CBRSample 示例，您需要为本示例生成并部署 BizTalk 项目、配置接收端口和位置，并配置两个不同的发送端口。  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>为本示例生成并部署 BizTalk 项目  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     `<Samples Path>`**\Messaging\CBRSample**  
  
2.  运行**Setup.bat**，这将执行以下操作：  
  
    -   创建输入 (**中**) 和输出文件夹 (**美国**和**可以**) 此示例。  
  
    -   编译并部署本示例的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  
  
    > [!NOTE]
    >  此示例显示以下警告时创建和绑定的端口：  
    >   
    >  **警告： 收到未为指定的处理程序接收位置"CBRReceiveLocation";使用第一个更新接收具有匹配的传输类型的处理程序。**  
    >   
    >  可以安全地忽略此警告。 （考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）  
  
    > [!NOTE]
    >  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
    > [!NOTE]
    >  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat，必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用此密钥对生成的程序集进行签名。  
  
    > [!NOTE]
    >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a>准备配置接收端口和位置以及发送端口  
  
1.  在**Microsoft SQL Management Studio**，选择正确的 BizTalk 管理数据库。  
  
    > [!NOTE]
    >  BizTalk 管理数据库也称为 BizTalk 配置数据库。  
  
#### <a name="to-configure-enlist-and-start-the-us-send-port"></a>配置、登记并启动 U.S. 发送端口  
  
1.  在 BizTalk Server 管理控制台中，展开**发送端口**，右键单击**CBRUSSendPort**，然后单击**编辑**。  
  
2.  在**静态单向发送端口属性**对话框中，对话框中，左侧的文件夹树中选择**筛选器映射 &#124;筛选器**，然后通过设置中添加新行**属性**到**CBRSample.CountryCode**、 保留**运算符**列设置为**==** ，以及设置**值**列**100**。  
  
3.  在对话框左侧的文件夹树中，选择**筛选器映射 &#124;出站映射**，将其设置**要应用映射**属性**CBRSample.CBRInput2USMap**，然后单击**确定**。 您可能需要单击滚动按钮才能显示映射。  
  
#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a>配置、登记并启动 Canadian 发送端口  
  
1.  在 BizTalk Server 管理控制台中，展开**发送端口**，右键单击**CBRCANSendPort**，然后单击**编辑**。  
  
2.  在**静态单向发送端口属性**对话框中，对话框中，左侧的文件夹树中选择**筛选器映射 &#124;筛选器**，然后通过设置中添加新行**属性**到**CBRSample.CountryCode**、 保留**运算符**列设置为**==** ，以及设置**值**列**200**。  
  
3.  在对话框左侧的文件夹树中，选择**筛选器映射 &#124;出站映射**，将其设置**要应用映射**属性**CBRSample.CBRInput2CANMap**，然后单击**确定**。  
  
 以上步骤可将发送端口连接到接收端口。 此示例使用提升的属性，以将这些文档路由。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 现在便可使用本示例。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 CBRSample 示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  将输入的文件中，复制**CBRDataCAN.xml**和**CBRDataUS.xml**，到以下输入文件夹：  
  
     `<Samples Path>`**\Messaging\CBRSample\In**  
  
2.  观察如何转换每个文件和两个路由到以下项之一输出文件夹的值基于其**国家/地区代码**元素 (而不是 200 100):  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]转换并将路由输入的文件**CBRDataCAN.xml**的文件夹：  
  
         `<Samples Path>`**\Messaging\CBRSample\CAN**  
  
    -   BizTalk Server 转换并将路由输入的文件**CBRDataUS.xml**的文件夹：  
  
         `<Samples Path>`**\Messaging\CBRSample\US**  
  
## <a name="classes-or-methods-used-in-this-sample"></a>本示例中使用的类或方法  
 无。  
  
## <a name="see-also"></a>另请参阅  
 [默认管道](../core/default-pipelines.md)   
 [如何配置为发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [消息传递 （BizTalk Server 示例文件夹）](../core/messaging-biztalk-server-samples-folder.md)