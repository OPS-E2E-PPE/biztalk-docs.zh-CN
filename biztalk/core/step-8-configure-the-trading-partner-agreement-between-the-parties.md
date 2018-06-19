---
title: 步骤 8： 配置参与方之间贸易合作伙伴协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f532f85-3f09-4b60-b7bb-817ee3c79899
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25e49bf5dcae7324fa3b68fe5080d094b4a2f603
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280013"
---
# <a name="step-8-configure-the-trading-partner-agreement-between-the-parties"></a>步骤 8： 配置参与方之间贸易合作伙伴协议
![步骤 8 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")  
  
 在此步骤中，你可以配置 X12 贸易合作伙伴协议，以为两个贸易合作伙伴 OrderSystem 和 Fabrikam 之间交换 X12 消息定义参数。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-an-agreement"></a>配置协议  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**方和业务配置文件**页上，右键单击**Fabrikam_Profile**，指向**新建**，然后单击**协议**。  
  
3.  在**常规属性**页上，为**名称**文本框中，输入协议的名称。  
  
4.  从**协议**下拉列表中，选择**X12**。  
  
5.  在**第二个方**部分中，从**方**下拉列表中，选择**OrderSystem**。  
  
6.  在**第二个方**部分中，从**业务**下拉列表中，选择**OrderSystem_Profile**。  
  
     你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。  
  
7.  在**常规**选项卡上，在**常规属性**页上，在**常见主机设置**部分中，选择**打开 reporting**，，然后选择**用于报告的应用商店消息负载**。  
  
8.  在上执行以下任务**Fabrikam-> OrderSystem**选项卡。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**发件人限定符 (ISA5)**|选择**ZZ-双方约定**。|  
        |**发件人标识符 (ISA6)**|输入**THEM**。|  
        |**接收方限定符 (ISA7)**|选择**ZZ-双方约定**。|  
        |**接收方标识符 (ISA8)**|输入**美国**。|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。 它将与匹配的值**ISA5**， **ISA6**， **ISA7**，和**ISA8**与协议的属性中的交换标头中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此外将匹配的发件人限定符和 （而不是收件人限定符和标识符） 的标识符来解析协议。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。  
  
    2.  上**确认**页上，在**交换设置**部分中，单击**997 预期**。 选择此复选框可以在收到 850 交换时提示接收管道生成 997 确认。  
  
    3.  上**验证**下页上**交换设置**部分中，请确保**交换控制编号 （检查重复的 isa13）** 选项处于未选中状态。  
  
        > [!NOTE]
        >  清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。  
  
    4.  上**本地主机设置**页上，在**交换设置**部分中，清除**路由 ACK 发送管道请求-响应接收端口**。  
  
        > [!NOTE]
        >  清除**路由 ACK**属性是必需的因为此解决方案返回通过单独的异步确认发送端口，而不是通过与双向关联的发送端口将同步确认接收端口。  
  
    5.  上**本地主机设置**下页上**事务设置设置**部分中，选择要用于处理传入的交换的架构命名空间。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**Default**|选中列中的复选框|  
        |**有关 ST1**|选择**850-采购订单**。|  
        |**GS2**|输入**THEM**。|  
        |**目标 Namespace**|选择**http://schemas.microsoft.com/BizTalk/EDI/X12/2006**。|  
  
        > [!NOTE]
        >  设置属性可以使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定处理传入 850 交换时使用的架构。 如果某一交换的 GS02 和 ST01 的值是在网格行上输入的，则将使用同一行的目标命名空间来确定要使用的架构。  
  
9. 在上执行以下任务**OrderSystem-> Fabrikam**选项卡。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**发件人限定符 (ISA5)**|选择**ZZ-双方约定**。|  
        |**发件人标识符 (ISA6)**|输入**美国**。|  
        |**接收方限定符 (ISA7)**|选择**ZZ-双方约定**。|  
        |**接收方标识符 (ISA8)**|输入**THEM**。|  
  
    2.  上**字符集和分隔符**页上，在**交换设置**部分中，选择**CR LF**为**后缀**属性。  
  
    3.  上**发送端口**下页上**交换设置**部分中，将会将确认发送回 Fabrikam 发送端口相关联。 在**发送端口**网格下**名称**列中，单击空单元格，然后从下拉列表列表中，选择发送端口 (**toTHEM_997**) 创建用于发送 997到 Fabrikam 的确认。  
  
    4.  上**包络线**下页上**事务设置设置**部分中，输入网格的第一行中的所有列的值。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**Default**|选择中的复选框**默认**列。 **注意：** 当作为默认值的值选择此行**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，和**目标命名空间**不的匹配项消息。|  
        |**事务类型**|选择你的测试消息的消息类型**850-采购订单**。|  
        |**版本/发行版**|输入的 EDI 版本中， **00401**。|  
        |**目标命名空间**|选择**http://schemas.microsoft.com/Edi/X12**。|  
        |**GS1**|验证**PO-采购订单 (850)** 选择。|  
        |**GS2**|输入**1234567**。<br /><br /> **发件人应用程序 id。**|  
        |**GS3**|输入**0000000**。<br /><br /> **接收方应用程序 id。**|  
        |**GS4**|选择**CCYYMMDD**。 **注意：** 你需要在下拉列表中选择值，而不仅仅是在要显示默认值的字段中单击。 如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。|  
        |**GS5**|选择**HHMM**。|  
        |**GS7**|选择**X 的公认的标准委员会 X12**。|  
        |**GS8**|验证**00401**已输入。|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将为 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值的出站确认 GS08 设置值**事务类型**，**版本/发行版**，和**目标命名空间**。 发送管道尝试将事务集类型、X12 版本和目标命名空间与消息标头中的对应值相匹配。 如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，和**目标命名空间**值。  
  
10. 单击 **“应用”**。  
  
11. 单击 **“确定”**。 新添加的协议被列入**协议**部分**方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  
  
12. 重新启动 BizTalk 服务。 在 BizTalk Server 管理控制台中，在**平台设置**，单击**主机实例**，右键单击**BizTalkServerApplication**，然后单击**重新启动**。  
  
    > [!NOTE]
    >  激活或停用 EDI 状态报告功能后，需要重新启动 BizTalk 服务，以使更改生效。  
  
## <a name="next-steps"></a>后续步骤  
 测试 EDI 解决方案中所述[步骤 9： 测试 EDI 解决方案](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a>另请参阅  
 [配置编码协议属性](../core/configuring-encoding-agreement-properties.md)