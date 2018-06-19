---
title: 步骤 9： 测试解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df446ccc-add3-4dd3-b674-253dda385541
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89a3722d6d8e1d4b730341dfaf16d60af1686f21
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973067"
---
# <a name="step-9-test-the-solution"></a>步骤 9： 测试解决方案
在本主题中，你将通过向部署 EDI 协议所在的 HTTP 终结点发送 X12 840 销售订单消息来测试混合应用程序。 销售订单消息示例如下所示：  
  
```  
ISA*00*          *00*          *ZZ*CONTOSO        *ZZ*NORTHWIND      *991221*1226*U*00401*000000025*0*T*:~  
GS*PO*THEM*US*19991221*1226*1*X*004010~  
ST*840*0002~  
BQT*00*BQT02*20120619*001*20120719~  
PER*1A*John*EM*John@contoso.com~  
N1*001~  
N2*co~  
N3*Contoso*One Contoso Way~  
N4*Redmond*WA*98052*US~  
PO1*PO101*121*01*10*AA*A1*1~  
CTT*475~  
SE*10*0002~  
GE*1*1~  
IEA*1*000000025~  
```  
  
 在此消息中，突出显示的段 (与开头的行**PO1**) 包含订单数量。 此消息中的订单数量是*121*。 因此，如果你发送此消息，它必须插入到**SalesOrder**表。 可将该数量更新为小于 100 并重新发送消息，然后必须将其发送到你在 FILE 发送端口中指定的文件位置。  
  
 若要将此消息发送到 EDI 协议中，可以使用**MessageSender**工具附带的示例[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]。 您可以下载示例从[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)。  
  
### <a name="to-send-a-message"></a>发送消息的步骤  
  
1.  找到**MessageSender**示例包中的项目并生成代码。  
  
2.  使用生成**MessageSender**命令行可执行文件 （在项目的 \bin\Debug 文件夹） 将消息发送到部署的 EDI 协议。 此工具接受以下格式的命令行参数：  
  
    ```  
    MessageSender.exe <ServiceBusNamespace> <IssuerName> <IssuerKey> <EDI agreement endpoint> <MessageFilepath> <ContentType>  
    ```  
  
     其中，  
  
    |参数名称|Description|  
    |--------------------|-----------------|  
    |ServiceBusNamespace|Service Bus 命名空间|  
    |IssuerName|指定命名空间的发布者名称|  
    |IssuerKey|指定命名空间的发布者密钥|  
    |EDI 协议终结点|部署 EDI 协议所在的终结点。 你可以获取此终结点 URL，从接收设置选项卡 （和其中，传输页） 中部署的 EDI 协议[步骤 2 (为 Azure): 创建 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)。|  
    |MessageFilePath|包含请求消息示例的文件的路径。|  
    |ContentType|对于本教程中，将此参数设置为**文本/无格式**。|  
  
     打开命令提示符并导航到在其中生成该解决方案**MessageSender**项目。 运行以下命令，以发送订单数量大于 100 的请求消息：  
  
    ```  
    MessageSender.exe <service bus namespace> owner <issuer key>https://<namespace>.servicebus.appfabriclabs.com/7576ff3d-a0f3-4a46-a4f6-f5be4a50616a/DemoAgreement<path to the sample message> "text/plain"  
    ```  
  
3.  打开 SQL Server Management Studio，连接到包含的数据库**SalesOrder**表，，然后验证新记录插入表。 请注意中的值**Qty**列; 它必须是*121*。  
  
4.  使用**MessageSender**发送另一条消息，但这次设置的值的数量的排序将邮件中*99*。 你将注意到该现在，在中插入任何记录**SalesOrder**表。 相反，消息将复制到用于接收与订单数量小于 100 的消息指定的文件位置。 收到的消息如下所示：  
  
    ```  
    <ns1:SalesOrder xmlns:ns0="http://schemas.microsoft.com/BizTalk/EDI/X12/2006" xmlns:ns1="http://ECommerceSalesOrder.Inbound">  
      <CompanyCode>co</CompanyCode>  
      <PartID>1</PartID>  
      <Quantity>99</Quantity>  
      <AskPrice>10</AskPrice>  
      <RequestShipmentDate>2012-07-19</RequestShipmentDate>  
      <Address>  
        <Line1>Contoso</Line1>  
        <Line2>One Contoso Way</Line2>  
        <City>Redmond</City>  
        <State>WA</State>  
        <Country>US</Country>  
        <Zipcode>98052</Zipcode>  
      </Address>  
      <Contact>  
        <Firstname>John</Firstname>  
        <Lastname>John@contoso.com</Lastname>  
      </Contact>  
      <Comments>Order from Partnerco</Comments>  
      <DateNow>2012-06-19</DateNow>  
    </ns1:SalesOrder>  
  
    ```  
  
     请注意中的值**数量**元素。 它是*99*。  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 创建使用 BizTalk Server 2013 的混合应用程序](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)