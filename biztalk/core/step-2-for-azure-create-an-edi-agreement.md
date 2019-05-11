---
title: 步骤 2 （适用于 Azure):创建 EDI 协议 |Microsoft Docs
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
ms.openlocfilehash: 38150af85186ec811383e52a455bd5591edbbb02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392761"
---
# <a name="step-2-for-azure-create-an-edi-agreement"></a>步骤 2 （适用于 Azure):创建 EDI 协议
在本主题中，您将创建使用 Azure BizTalk 门户可用作合作伙伴的一部分[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]。 此外将创建两个合作伙伴 （Northwind 和 Contoso） 来处理发送的 X12 销售订单消息通过 Contoso 向 Northwind 之间的协议。  
  
### <a name="to-create-partners"></a>若要创建合作伙伴  
  
1.  使用你的 Microsoft 帐户，登录到门户网站，网址[ http://go.microsoft.com/fwlink/p/?LinkId=235056 ](http://go.microsoft.com/fwlink/p/?LinkId=235056)。  
  
2.  创建 Northwind 的合作伙伴。 遵循的步骤[合作伙伴和配置文件](http://msdn.microsoft.com/library/windowsazure/hh689791)创建合作伙伴。  
  
    > [!IMPORTANT]
    >  将为托管合作伙伴此合作伙伴标记。  
  
3.  重复步骤来为 Contoso 创建合作伙伴。 ***不这样做***将为托管合作伙伴此合作伙伴标记。  
  
### <a name="to-create-an-agreement"></a>若要创建协议  
  
1.  在门户的主页上，单击**协议**。  
  
2.  上**协议**页上，单击**X12**选项卡上，如果您尚不在该选项卡上。然后单击**创建协议**。  
  
3.  在中**新协议**页上，输入以下详细信息：  
  
    |||  
    |-|-|  
    |**字段**|**说明**|  
    |“属性”|输入协议的名称。 对于本教程，将名称指定为`DemoAgreement`。<br /><br /> **注意：** 这是必填字段。 协议名称必须是唯一的。|  
    |Description|输入注释或协议的说明。|  
    |合作伙伴 1 配置文件 （托管）|选择协议的托管的合作伙伴。 托管的合作伙伴是托管服务提供商合作伙伴，在协议部署期间为该合作伙伴部署管道。 通常由服务提供商托管的合作伙伴配置为托管合作伙伴而企业合作伙伴未标记为托管合作伙伴。<br /><br /> **注意：** 对于本教程中，托管的合作伙伴是**Northwind**。<br /><br /> **注意：** 配置文件字段中显示的默认配置文件。 选择所需的配置文件已配置的合作伙伴。|  
    |合作伙伴 2 配置文件|选择合作伙伴协议 （不是托管的合作伙伴）。<br /><br /> **注意：** 配置文件字段中显示的默认配置文件。 选择所需的配置文件已配置的合作伙伴。|  
  
     **标识**  
  
    |**字段**|**说明**|  
    |---------------|---------------------|  
    |合作伙伴 1 ID 限定符|选择向贸易合作伙伴提供唯一业务标识的身份验证限定符。 对于本教程中，选择**ZZ-双方约定**。|  
    |ReplTest1|输入`Northwind`。|  
    |合作伙伴 2 ID 限定符|选择向贸易合作伙伴提供唯一业务标识的身份验证限定符。 对于本教程中，选择**ZZ-双方约定**。|  
    |ReplTest1|输入`Contoso`。|  
  
     **跟踪**  
  
    |**字段**|**说明**|  
    |---------------|---------------------|  
    |跟踪发送端消息属性|选中此项可向合作伙伴发送 EDI 消息时，存储消息属性。 存储后，您可以通过单击查询此数据**跟踪**Azure BizTalk 门户的左窗格中。<br /><br /> 启用时，您还可以通过检查来存储消息正文**跟踪发送端消息正文**。|  
    |跟踪接收端消息属性|选中此项可从合作伙伴接收 EDI 消息时，存储消息属性。 存储后，您可以通过单击查询此数据**跟踪**Azure BizTalk 门户的左窗格中。<br /><br /> 启用时，您还可以通过检查来存储消息正文**跟踪接收端消息正文**。|  
  
4.  单击 **“继续”**。  
  
     单击**继续**添加两个新选项卡，一个用于接收设置，另一个用于发送设置。 每个选项卡是两个合作伙伴，一个用于接收消息，另一个用于发送消息之间的单向协议。  
  
5.  指定接收设置。  
  
    1.  上**传输**页上，将**传输类型**为 HTTP。  
  
         **终结点**字段显示的 URL，Contoso 必须向其发送 X12 销售订单消息。  
  
    2.  上**协议**页上，指定以下值。  
  
        1.  如果需要，请为 ISA1、 ISA2、 ISA3 和 ISA4 指定值。  
  
        2.  下**确认**，选择**预期的 TA1**并**预期的 997**如果你想要接收的响应中生成技术和功能确认消息。  
  
        3.  下**架构**，单击**上载**按钮并上载**X12 840 架构**(从下载[ http://go.microsoft.com/fwlink/p/?LinkId=235057 ](http://go.microsoft.com/fwlink/p/?LinkId=235057)) 和**SalesOrder**架构 (你在中创建[若要创建 EDI 项目中的架构](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema))。  
  
             设置下的以下属性**架构**部分。  
  
            |||  
            |-|-|  
            |版本|00401|  
            |事务类型 (ST1)|840|  
            |架构|/X12_00401_840.xsd|  
  
    3.  上**转换**页上，上载你在中创建的转换[创建 EDI 项目中的转换](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm)。  
  
         下**选择你想要为此协议的一部分执行的映射**，选择 **/X12_00401_840.xsd**有关**架构**和 **/EDI840TOSALESORDER。TRFM**有关**转换文件名称**。  
  
    4.  上**路由**页上，选择**路由到服务总线队列**并提供消息发送到队列的相对地址。 对于本教程中，指定相对地址作为`queueordersedi`，以便完整的 URL 是`https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`。  
  
        > [!NOTE]
        >  本教程会覆盖在消息挂起设置中指定的失败的消息发送到终结点你的方案。 但是，对于成功部署该协议，必须为此设置提供一个值。 您可以输入一个非空值。  
  
6.  指定发送设置。  
  
    > [!NOTE]
    >  在本教程中所述的方案，不需要针对该协议的任何发送端配置。 但是，协议不能部署而无需指定发送设置中，即使它们是虚拟值。 而且，在**发送设置**选项卡上，您无需提供任何虚拟值**入站 URI**，**转换**，以及**批处理**。  
  
    1.  上**协议**页面上，在**架构**，单击**上载**按钮并上载架构代表 X12 840 消息。  
  
         设置**版本**到**00401**，**事务类型**到**840**，并**架构**到**X12_00401_840**。  
  
    2.  上**传输**页上，指定终结点向合作伙伴发送响应消息或确认。 您必须指定终结点每个成功处理的消息，以及由于处理失败的挂起的消息。  
  
7.  单击**部署协议**以部署协议。 在中显示的 URL 现在部署协议**传输**页**接收设置**选项卡。  
  
## <a name="see-also"></a>请参阅  
 [教程 4：创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)