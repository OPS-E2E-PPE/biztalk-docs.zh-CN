---
title: （适用于 Azure) 中的步骤 2： 创建一个 EDI 协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8003697-4955-45c0-ba0b-e7c293a050a2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc2db7361aef663c70c7227febfea5fc08dc699a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280069"
---
# <a name="step-2-for-azure-create-an-edi-agreement"></a>（适用于 Azure) 中的步骤 2： 创建一个 EDI 协议
在本主题中，你将使用 [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] 中的 Azure BizTalk 门户创建合作伙伴。 你还将在两个合作伙伴（Northwind 和 Contoso）之间创建协议，以处理 Contoso 发送给 Northwind 的 X12 销售订单消息。  
  
### <a name="to-create-partners"></a>若要创建合作伙伴  
  
1.  使用你的 Microsoft 帐户，登录到门户中，在[http://go.microsoft.com/fwlink/p/?LinkId=235056](http://go.microsoft.com/fwlink/p/?LinkId=235056)。  
  
2.  为 Northwind 创建合作伙伴。 遵循的步骤[合作伙伴和配置文件](http://msdn.microsoft.com/library/windowsazure/hh689791)创建合作伙伴。  
  
    > [!IMPORTANT]
    >  将此合作伙伴标记为托管合作伙伴。  
  
3.  重复上述步骤，为 Contoso 创建合作伙伴。 ***不这样做***将标记为托管合作伙伴此合作伙伴。  
  
### <a name="to-create-an-agreement"></a>创建协议  
  
1.  在门户的主页上，单击**协议**。  
  
2.  上**协议**页上，单击**X12**选项卡上，如果你尚不在该选项卡上。然后单击**创建协议**。  
  
3.  在**新协议**页上，输入以下详细信息：  
  
    |||  
    |-|-|  
    |**字段**|**Description**|  
    |Name|输入协议的名称。 对于本教程，将名称指定为`DemoAgreement`。<br /><br /> **注意：** 这是必填字段。 协议的名称必须唯一。|  
    |Description|输入协议的注释或说明。|  
    |合作伙伴 1 配置文件（托管）|为协议选择托管合作伙伴。 托管合作伙伴是由服务提供商托管的合作伙伴，在协议部署期间会为该合作伙伴部署管道。 在未将企业合作伙伴标记为托管合作伙伴时，通常会将服务提供商托管的合作伙伴配置为托管合作伙伴。<br /><br /> **注意：** 对于本教程中，托管的合作伙伴是**Northwind**。<br /><br /> **注意：** 的默认配置文件将显示在配置文件字段。 选择已为合作伙伴配置的所需配置文件。|  
    |合作伙伴 2 配置文件|为协议选择合作伙伴（不是托管合作伙伴）。<br /><br /> **注意：** 的默认配置文件将显示在配置文件字段。 选择已为合作伙伴配置的所需配置文件。|  
  
     **标识**  
  
    |**字段**|**Description**|  
    |---------------|---------------------|  
    |合作伙伴 1 ID 限定符|选择可向贸易合作伙伴提供唯一业务标识的身份验证限定符。 对于本教程中，选择**Zz-mutually Defined**。|  
    |值|输入`Northwind`。|  
    |2 合作伙伴 ID 限定符|选择可向贸易合作伙伴提供唯一业务标识的身份验证限定符。 对于本教程中，选择**Zz-mutually Defined**。|  
    |值|输入`Contoso`。|  
  
     **跟踪**  
  
    |**字段**|**Description**|  
    |---------------|---------------------|  
    |跟踪发送端消息属性|选中此项，以便在向合作伙伴发送 EDI 消息时存储消息属性。 存储后，您可以查询此数据，通过单击**跟踪**从在 Azure BizTalk 门户的左窗格。<br /><br /> 启用时，你还可以通过检查来存储消息正文**跟踪发送端消息正文**。|  
    |跟踪接收端消息属性|选中此项，以便在接收来自合作伙伴的 EDI 消息时存储消息属性。 存储后，您可以查询此数据，通过单击**跟踪**从在 Azure BizTalk 门户的左窗格。<br /><br /> 启用时，你还可以通过检查来存储消息正文**跟踪接收端消息正文**。|  
  
4.  单击 **“继续”**。  
  
     单击**继续**添加两个新选项卡，一个用于接收设置，另一个用于发送设置。 每个选项卡用于两个合作伙伴之间的单向协议，一个用于接收消息，另一个用于发送消息。  
  
5.  指定接收设置。  
  
    1.  上**传输**页上，设置**传输类型**为 HTTP。  
  
         **终结点**字段显示的 URL，Contoso 必须向其发送 X12 销售订单消息。  
  
    2.  上**协议**页上，指定以下值。  
  
        1.  如果需要，请指定 ISA1、ISA2、ISA3 和 ISA4 的值。  
  
        2.  下**确认**，选择**预期的 TA1**和**997 预期**如果你想要接收的响应中生成技术和功能确认消息。  
  
        3.  下**架构**，单击**上载**按钮，然后上载**X12 840 架构**(从下载[http://go.microsoft.com/fwlink/p/?LinkId = 235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)) 和**SalesOrder**架构 (你在中创建[创建 EDI 项目中的架构](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema))。  
  
             设置以下属性下的**架构**部分。  
  
            |||  
            |-|-|  
            |版本|00401|  
            |事务类型 (ST1)|840|  
            |架构|/X12_00401_840.xsd|  
  
    3.  上**转换**页上，上载你在中创建转换[创建 EDI 项目中的转换](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm)。  
  
         下**选择你想要作为此协议的一部分执行的映射**，选择 **/X12_00401_840.xsd**为**架构**和 **/EDI840TOSALESORDER。TRFM**为**转换文件名**。  
  
    4.  上**路由**页上，选择**路由到服务总线队列**并提供消息发送到队列的相对地址。 对于本教程中，指定的相对地址与`queueordersedi`以便完整的 URL 是`https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`。  
  
        > [!NOTE]
        >  本教程不涵盖将失败的消息发送至你在消息挂起设置中指定的终结点这一情况。 但是，为了成功部署协议，必须为此设置提供一个值。 可以输入一个非空值。  
  
6.  指定发送设置。  
  
    > [!NOTE]
    >  对于本教程描述的情况，无需为协议进行任何发送端配置。 但是，如果不指定发送设置，即使这些设置为虚拟值，也无法部署协议。 此外，在**发送设置**选项卡上，你不需要提供的任何 dummy 值**入站 URI**，**转换**，和**批处理**。  
  
    1.  上**协议**页上，在**架构**，单击**上载**按钮，然后上载 x12 架构 840 消息。  
  
         设置**版本**到**00401**，**事务类型**到**840**，和**架构**到**X12_00401_840**。  
  
    2.  上**传输**页上，指定向合作伙伴发送确认或响应消息的终结点。 必须为每条成功处理的消息以及因处理失败而挂起的消息指定一个终结点。  
  
7.  单击**部署协议**以部署协议。 在中显示的 URL 现在部署协议**传输**页**接收设置**选项卡。  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 创建使用 BizTalk Server 2013 的混合应用程序](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)