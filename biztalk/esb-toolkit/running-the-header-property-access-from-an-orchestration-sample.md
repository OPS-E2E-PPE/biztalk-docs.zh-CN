---
title: "从业务流程示例运行标头属性访问 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2059eb2c-50a3-4618-a6ec-faa1a9e5d368
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ddbb2ea7ef978c0e5eae07835d5a9c1320bbc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a>从业务流程示例运行标头属性访问
本部分中的示例演示了如何 ESB 将 JMS 标头元数据升级到消息上下文属性，这些代码和在 Microsoft BizTalk 中的业务流程中的组件可以访问的属性。 此示例包括接收管道，其中包含将 JMS 标头元数据升级到消息上下文属性 ESB JMS 组件的实例。  
  
 接收端口从消息上下文属性将消息传递给业务流程检索的队列名称的命名的 JMSRouter 分配由 RfhUtil 实用工具 （和发送的标头元数据中）。 业务流程将此队列名称分配给动态发送端口，并将消息发送到该端口。  
  
 端口发送管道包含将消息上下文属性降级到 JMS 标头元数据 ESB JMS 组件的实例。  
  
 **若要运行标头属性访问示例**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
2.  运行 IBM RfhUtil 实用工具;选择名为 ESB 的队列管理器。JMS。在第一个下拉列表中连接到此队列管理器中，如下所示的此示例第 1 部分 Sample.QueueManager。  
  
3.  在第二个下拉列表中，选择名为 ESB 的目标出站队列。JMS。示例。SENDTOBIZTALK。  
  
4.  单击**ReadFile**在 RfhUtil 实用工具中，按钮，然后定位到名为测试 000128 测试消息文件。JMS 位于子文件夹中的名为 \Source\Samples\JMS\Test\Data\Load\\。 此文件包含一批 128 测试消息，但该实用程序将加载只有第一个。  
  
5.  单击**RFH**选项卡上，并确保该唯一**JMS**复选框处于选中状态。  
  
6.  单击**jms**选项卡，并请确保所选**回复**队列是 ESB。JMS。示例。答复，所选**目标队列**是 ESB。JMS。示例。DYNAMICQ2。  
  
7.  单击**Main**选项卡上，并依次**编写 Q**按钮，将消息写入到队列。  
  
8.  在延迟后时应用程序执行，ESB 输出消息会出现在 ESB。JMS。示例。DYNAMICQ2 队列。 打开 WebSphere 队列资源管理器并浏览队列为确认这一点。  
  
## <a name="how-the-sample-works"></a>此示例的工作原理  
 内部业务流程，代码可以访问加载到消息中的 JMS 标头的值**XmlDocument**实例，如下面的代码中所示。  
  
```csharp  
if (null != InboundMsg(  
    Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData))  
{     
  jmsInfo.LoadXml(InboundMsg(  
     Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData));  
  if (null != jmsInfo)  
  {  
    if (null != jmsInfo.SelectSingleNode("//Dst"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Dst");  
      destinationQueue = xElement.InnerText.ToUpper(  
                         System.Globalization.CultureInfo.CurrentCulture);  
    }  
    if (null != jmsInfo.SelectSingleNode("//Rto"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Rto");  
      replyToQueue = xElement.InnerText.ToUpper(  
                     System.Globalization.CultureInfo.CurrentCulture);  
    }  
  }  
}  
```  
  
 此外，则该代码可以访问的所有消息 MQMD 上下文属性。