---
title: 步骤 8：配置参与方之间的贸易合作伙伴协议 |Microsoft Docs
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
ms.openlocfilehash: 01641d539f77c3cce60b11edee30ff81e7b43b80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244240"
---
# <a name="step-8-configure-the-trading-partner-agreement-between-the-parties"></a>步骤 8：配置参与方之间的贸易合作伙伴协议
![步骤 8 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")  

 在此步骤中，你可以配置 X12 贸易合作伙伴协议定义的参数的交换 X12 OrderSystem 和 Fabrikam 在两个贸易合作伙伴之间的消息。  

## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

### <a name="to-configure-an-agreement"></a>若要配置协议  

1. 单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**参与方和业务配置文件**页上，右键单击**Fabrikam_Profile**，指向**新建**，然后单击**协议**。  

3. 在**常规属性**页上，对于**名称**文字框中，输入协议的名称。  

4. 从**协议**下拉列表中，选择**X12**。  

5. 在中**第二方**部分中，从**方**下拉列表中，选择**OrderSystem**。  

6. 在中**第二方**部分中，从**业务**下拉列表中，选择**OrderSystem_Profile**。  

    你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向协议，每个单向协议代表消息 （包括消息传输和确认传输） 的一次完整事务。  

7. 在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。  

8. 在执行以下任务**Fabrikam-> OrderSystem**选项卡。  

   1. 上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

      |使用此选项|执行的操作|  
      |--------------|----------------|  
      |**发送方限定符 (ISA5)**|选择**ZZ-双方约定**。|  
      |**发送方标识符 (ISA6)**|输入**THEM**。|  
      |**接收方限定符 (ISA7)**|选择**ZZ-双方约定**。|  
      |**接收方标识符 (ISA8)**|输入**美国**。|  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要发送方和接收方限定符和标识符字段才能执行协议解析。 它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能解析协议，它将使用后备协议属性。  

   2. 上**确认**页面上，在**交换设置**部分中，单击**预期的 997**。 选中此复选框提示接收管道生成 997 确认收到 850 交换时...  

   3. 上**验证**页**交换设置**部分中，请确保**交换控制编号 （检查重复的 ISA13）** 选项处于未选中状态。  

      > [!NOTE]
      >  清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。  

   4. 上**本地主机设置**页面上，在**交换设置**部分中，清除**确认路由到发送管道请求-响应接收端口**。  

      > [!NOTE]
      >  清除**将确认路由到**属性是必需的因为此解决方案返回异步确认通过单独的发送端口，而不是通过与双向关联的发送端口同步确认接收端口。  

   5. 上**本地主机设置**页**事务集设置**部分中，选择要用于处理传入的交换的架构的命名空间。  


      |       使用此选项       |                           执行的操作                            |
      |----------------------|-----------------------------------------------------------------|
      |     **默认**      |                列中选中的复选框                |
      |     **对于 ST1**      |                选择**850 – 采购订单**。                 |
      |       **GS2**        |                         输入**THEM**。                         |
      | **目标 Namespace** | 选择 <http://schemas.microsoft.com/BizTalk/EDI/X12/2006>。 |

      > [!NOTE]
      >  设置属性后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来确定要处理传入 850 交换时使用的架构。 如果交换具有网格的行输入的 GS02 和 ST01 值，然后将使用在同一行的目标命名空间来确定要使用的架构。  

9. 在执行以下任务**OrderSystem-> Fabrikam**选项卡。  

   1. 上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  


      |            使用此选项            |            执行的操作             |
      |--------------------------------|-----------------------------------|
      |  **发送方限定符 (ISA5)**   | 选择**ZZ-双方约定**。 |
      |  **发送方标识符 (ISA6)**  |           输入**美国**。           |
      | **接收方限定符 (ISA7)**  | 选择**ZZ-双方约定**。 |
      | **接收方标识符 (ISA8)** |          输入**THEM**。          |


   2. 上**字符集和分隔符**页面上，在**交换设置**部分中，选择**CR LF**有关**后缀**属性。  

   3. 上**发送端口**页**交换设置**部分中，将会将确认发送回 Fabrikam 的发送端口相关联。 在中**发送端口**网格下**名称**列中，单击空单元格，并从下拉列表中，选择发送端口 (**toTHEM_997**) 创建用于发送 997到 Fabrikam 的确认。  

   4. 上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。  


      |       使用此选项       |                                                                                                                                               执行的操作                                                                                                                                               |
      |----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **默认**      | 选择中的复选框**默认**列。 **注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，并**GS8**是即使使用的值**事务类型**，**版本/发行版**，并**目标命名空间**不是消息的匹配项。 |
      | **事务类型** |                                                                                                                选择你的测试消息的消息类型**850 – 采购订单**。                                                                                                                 |
      | **版本/发行版**  |                                                                                                                                   输入 EDI 版本， **00401**。                                                                                                                                    |
      | **目标命名空间** |                                                                                                                           选择 <http://schemas.microsoft.com/Edi/X12>。                                                                                                                           |
      |       **GS1**        |                                                                                                                         确认**PO-采购订单 (850)** 处于选中状态。                                                                                                                         |
      |       **GS2**        |                                                                                                                       输入**1234567**。<br /><br /> **发件人应用程序 id。**                                                                                                                        |
      |       **GS3**        |                                                                                                                      输入**0000000**。<br /><br /> **接收方应用程序 id。**                                                                                                                       |
      |       **GS4**        |                    选择**CCYYMMDD**。 **注意：** 您必须下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。 如果您单击字段而无需从下拉列表中选择值，该值将不实际选择。                     |
      |       **GS5**        |                                                                                                                                            选择**HHMM**。                                                                                                                                            |
      |       **GS7**        |                                                                                                                           选择**X-公认的标准委员会 X12**。                                                                                                                           |
      |       **GS8**        |                                                                                                                                确认**00401**已输入。                                                                                                                                 |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将设置 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值对出站确认的 GS08**事务类型**，**版本/发行版**，和**目标命名空间**。 发送管道将尝试匹配事务集类型、 X12 版本和消息的标头中的相应值的目标命名空间。 如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，并**目标命名空间**值。  

10. 单击 **“应用”**。  

11. 单击“确定” 。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下启用新添加的协议。  

12. 重新启动 BizTalk 服务。 在 BizTalk Server 管理控制台中下**平台设置**，单击**主机实例**，右键单击**BizTalkServerApplication**，然后单击**重新启动**。  

    > [!NOTE]
    >  BizTalk 服务需要重新启动后 EDI 状态报告已激活或停用的更改才能生效。  

## <a name="next-steps"></a>后续步骤  
 测试 EDI 解决方案，如中所述[步骤 9:测试 EDI 解决方案](../core/step-9-test-the-edi-solution.md)  

## <a name="see-also"></a>请参阅  
 [配置编码协议属性](../core/configuring-encoding-agreement-properties.md)