---
title: 从业务流程示例运行 Header 属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2059eb2c-50a3-4618-a6ec-faa1a9e5d368
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b785157d4d3a03e25bc80b1a370f419de72822f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242768"
---
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a>从业务流程示例运行 Header 属性
本部分的示例演示了 ESB 如何将 JMS 标头元数据升级到消息上下文属性，可以访问代码和在 Microsoft biztalk 业务流程中的组件。 该示例包括接收管道，其中包含将 JMS 标头元数据升级到消息上下文属性的 ESB JMS 组件的实例。  
  
 接收端口将消息传递到业务流程检索的队列名称的命名的 JMSRouter 分配由 RfhUtil 实用程序 （和在标头元数据中发送），从消息上下文属性。 业务流程将此队列名称分配给动态发送端口，并将消息发送到该端口。  
  
 该端口的发送管道包含将消息上下文属性降级到 JMS 标头元数据的 ESB JMS 组件的实例。  
  
 **若要运行 Header 属性示例**  
  
1.  如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  
  
2.  运行 IBM RfhUtil 实用程序;选择名为 ESB 的队列管理器。JMS。若要连接到此队列管理器中，如本示例的第 1 部分中所示的第一个下拉列表 Sample.QueueManager。  
  
3.  在第二个下拉列表中，选择名为 ESB 的出站目标队列。JMS。示例。SENDTOBIZTALK。  
  
4.  单击**ReadFile**在 RfhUtil 实用程序中，按钮，然后定位到名为测试 000128 测试消息文件。位于名为 \Source\Samples\JMS\Test\Data\Load 子文件夹中的 JMS\\。 此文件包含一批 128 测试消息，但该实用程序将加载只有第一个。  
  
5.  单击**RFH**选项卡，并确保只有**JMS**复选框处于选中状态。  
  
6.  单击**jms**选项卡，并请确保所选**答复**队列是 ESB。JMS。示例。答复和的所选**目标队列**是 ESB。JMS。示例。DYNAMICQ2。  
  
7.  单击**Main**选项卡，然后依次**编写 Q**按钮可将消息写入到队列。  
  
8.  后一段延迟时应用程序执行，ESB 输出消息将出现在 ESB。JMS。示例。DYNAMICQ2 队列。 打开 WebSphere 队列资源管理器并浏览队列来确认这一点。  
  
## <a name="how-the-sample-works"></a>示例工作原理  
 在业务流程中，代码可以访问通过加载到已在 JMS 标头的值**XmlDocument**实例，如以下代码所示。  
  
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
  
 此外，代码可以访问的所有消息的 MQMD 上下文属性。