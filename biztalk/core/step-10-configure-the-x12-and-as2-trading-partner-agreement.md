---
title: "步骤 10： 配置 X12 和 AS2 贸易合作伙伴协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fcdb3af-727a-4d20-9dcf-cf162e7d3398
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0ce0ef6fef056c52e06fc1843024cbcf683c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-10-configure-the-x12-and-as2-trading-partner-agreement"></a>步骤 10： 配置 X12 和 AS2 贸易合作伙伴协议
![步骤 10 11](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")  
  
 在此步骤中，你将 X12 和 AS2 贸易合作伙伴协议设置为通过 HTTP 传输 EDIINT/AS2 编码消息。 该 Fabrikam 参与方将 EDI 交换发送至 Contoso，后者向 Fabrikam 返回 997 确认和异步 MDN。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-create-an-as2-agreement"></a>创建 AS2 协议  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**方和业务配置文件**页上，右键单击**Fabrikam_Profile**，指向**新建**，然后单击**协议**。  
  
3.  在**常规属性**页上，为**名称**文本框中，输入协议的名称。  
  
4.  从**协议**下拉列表中，选择**AS2**。  
  
5.  在**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  
  
6.  在**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  
  
     你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向 AS2 协议。  
  
7.  在**常规**选项卡上，在**常规属性**页上，在**常见主机设置**部分中，选择**打开 reporting**。  
  
8.  在上执行以下任务**Fabrikam-> Contoso**选项卡。  
  
    1.  上**标识符**页上，输入值**AS2-从**和**AS2-到**。 有关**AS2-从**，输入`Fabrikam`。 有关**AS2-到**，输入`Contoso`。  
  
    2.  上**验证**页上，选择**使用验证和 MDN 的协议设置，而不是消息标头**复选框  
  
        > [!NOTE]
        >  设置本属性可以确保在生成 MDN 时会使用的参与方属性，而非接收的 AS2 消息的 AS2 标头。  
  
    3.  在**确认 (Mdn)**页上，执行以下操作：  
  
        1.  选择**请求 MDN**复选框。  
  
        2.  请确保**请求签名的 MDN**清除复选框。  
  
        3.  选择**请求异步 MDN**复选框。  
  
        4.  在**回执送达选项 (URL)**文本框中，输入`http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`。  
  
9. 在上执行以下任务**Contoso-> Fabrikam**选项卡。  
  
    1.  上**标识符**页上，输入值**AS2-从**和**AS2-到**。 有关**AS2-从**，输入`Contoso`。 有关**AS2-到**，输入`Fabrikam`。  
  
    2.  上**发送端口**下页上**交换设置**部分中，在**发送端口**列表中，为**名称**选择**Send_Async_997**。  
  
        > [!NOTE]
        >  Send_Async_997 发送端口需要在文本框中输入**发送端口**列表以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以解析为传出 997 消息参与方。 发送管道将发送端口的名称与协议属性中的发送端口进行匹配。 这是必要的，因为在这种情况下，揂“AS2 收件人”属性在消息上下文中是不会升级的，该属性是发送管道解析参与方时首先要尝试进行的匹配。 有关详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
10. 单击 **“应用”**。  
  
11. 单击 **“确定”**。 新添加的协议被列入**协议**部分**方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  
  
### <a name="to-create-an-x12-agreement"></a>创建 X12 协议  
  
1.  右键单击**Fabrikam_Profile**，指向**新建**，然后单击**协议**。  
  
2.  在**常规属性**页上，为**名称**文本框中，输入协议的名称。  
  
3.  从**协议**下拉列表中，选择**X12**。  
  
4.  在**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  
  
5.  在**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  
  
     你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡可用于配置一个单向 X12 协议。  
  
6.  在**常规**选项卡上，在**常规属性**页上，在**常见主机设置**部分中，选择**打开 reporting**，，然后选择**用于报告的应用商店消息负载**。  
  
7.  在上执行以下任务**Fabrikam-> Contoso**选项卡。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。 对于本教程中，设置**ISA5**到**ZZ**， **ISA6**到**7654321**， **ISA7**到**ZZ**，和**ISA8**到**1234567**。  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。 它将与匹配的值**ISA5**， **ISA6**， **ISA7**，和**ISA8**与协议的属性中的交换标头中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此外将匹配的发件人限定符和 （而不是收件人限定符和标识符） 的标识符来解析协议。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。  
  
    2.  上**确认**下页上**交换设置**部分中，选择**997 预期**复选框。  
  
    3.  上**验证**下页上**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。  
  
        > [!NOTE]
        >  清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。  
  
    4.  上**本地主机设置**下页上**交换设置**だ い 鶼**接收方设置**，清除**路由 ACK 发送管道请求-响应接收端口**。  
  
        > [!NOTE]
        >  清除此属性将使你可通过单独的发送端口发送 997 确认，而不是通过与双向接收端口关联的发送端口发送该确认。  
  
8.  在上执行以下任务**Contoso-> Fabrikam**选项卡。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。  对于本演练中，设置**ISA5**到**ZZ**， **ISA6**到**1234567**， **ISA7**到**ZZ**，和**ISA8**到**7654321**。  
  
    2.  上**字符集和分隔符**下页上**交换设置**部分中，为**后缀**，选择**CR LF**。  
  
    3.  上**包络线**下页上**事务设置设置**部分中，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**Default**|选择**默认**。 **注意：**当作为默认值的值选择此行**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，和**目标命名空间**不的匹配项消息。|  
        |**事务类型**|例如，选择你的测试消息的消息类型**864 – 短信**。|  
        |**版本/发行版**|输入**00401**。|  
        |**目标命名空间**|选择**http://schemas.microsoft.com/BizTalk/EDI/X12/2006**。|  
        |**GS1**|验证是否选择测试消息的消息类型，例如， **TX-短信 (864)**。|  
        |**GS2**|输入**01**。|  
        |**GS3**|输入**7654321**。|  
        |**GS4**|选择所需的日期格式。 选择**CCYYMMDD**。 **注意：**你需要在下拉列表中选择值，而不仅仅是在要显示默认值的字段中单击。 如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。|  
        |**GS5**|选择所需的时间格式。 选择**HHMMSSdd**。|  
        |**GS7**|选择**T-运输数据协调委员会 (TDCC)**。|  
        |**GS8**|验证已作为中输入的 EDI 版本**00401**。|  
  
9. 单击 **“应用”**。  
  
10. 单击 **“确定”**。 新添加的协议被列入**协议**部分**方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  
  
11. 重新启动 BizTalk 服务。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，在**平台设置**，单击**主机实例**，右键单击**BizTalkServerApplication**，然后单击**重新启动**。  
  
## <a name="next-steps"></a>后续步骤  
 中所述测试 AS2 解决方案[步骤 11： 测试 AS2 解决方案](../core/step-11-test-the-as2-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 AS2 属性](../core/configuring-as2-properties.md)   
 [配置 EDI 属性](../core/configuring-edi-properties.md)