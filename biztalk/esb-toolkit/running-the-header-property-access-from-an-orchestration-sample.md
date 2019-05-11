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
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a><span data-ttu-id="063e8-102">从业务流程示例运行 Header 属性</span><span class="sxs-lookup"><span data-stu-id="063e8-102">Running the Header Property Access from an Orchestration Sample</span></span>
<span data-ttu-id="063e8-103">本部分的示例演示了 ESB 如何将 JMS 标头元数据升级到消息上下文属性，可以访问代码和在 Microsoft biztalk 业务流程中的组件。</span><span class="sxs-lookup"><span data-stu-id="063e8-103">This part of the sample demonstrates how the ESB promotes JMS header metadata into message context properties, which code and components in orchestrations within Microsoft BizTalk can access.</span></span> <span data-ttu-id="063e8-104">该示例包括接收管道，其中包含将 JMS 标头元数据升级到消息上下文属性的 ESB JMS 组件的实例。</span><span class="sxs-lookup"><span data-stu-id="063e8-104">The sample includes a receive pipeline that contains an instance of the ESB JMS component that promotes JMS header metadata into message context properties.</span></span>  
  
 <span data-ttu-id="063e8-105">接收端口将消息传递到业务流程检索的队列名称的命名的 JMSRouter 分配由 RfhUtil 实用程序 （和在标头元数据中发送），从消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="063e8-105">The receive port passes the message to an orchestration named JMSRouter that retrieves the queue name assigned by the RfhUtil utility (and sent in the header metadata) from the context properties of the message.</span></span> <span data-ttu-id="063e8-106">业务流程将此队列名称分配给动态发送端口，并将消息发送到该端口。</span><span class="sxs-lookup"><span data-stu-id="063e8-106">The orchestration assigns this queue name to a dynamic send port and sends the message to that port.</span></span>  
  
 <span data-ttu-id="063e8-107">该端口的发送管道包含将消息上下文属性降级到 JMS 标头元数据的 ESB JMS 组件的实例。</span><span class="sxs-lookup"><span data-stu-id="063e8-107">A send pipeline for the port contains an instance of the ESB JMS component that demotes the message context properties into the JMS header metadata.</span></span>  
  
 <span data-ttu-id="063e8-108">**若要运行 Header 属性示例**</span><span class="sxs-lookup"><span data-stu-id="063e8-108">**To run the Header Property Access sample**</span></span>  
  
1.  <span data-ttu-id="063e8-109">如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="063e8-109">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="063e8-110">运行 IBM RfhUtil 实用程序;选择名为 ESB 的队列管理器。JMS。若要连接到此队列管理器中，如本示例的第 1 部分中所示的第一个下拉列表 Sample.QueueManager。</span><span class="sxs-lookup"><span data-stu-id="063e8-110">Run the IBM RfhUtil utility; select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager, as in Part 1 of this sample.</span></span>  
  
3.  <span data-ttu-id="063e8-111">在第二个下拉列表中，选择名为 ESB 的出站目标队列。JMS。示例。SENDTOBIZTALK。</span><span class="sxs-lookup"><span data-stu-id="063e8-111">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
4.  <span data-ttu-id="063e8-112">单击**ReadFile**在 RfhUtil 实用程序中，按钮，然后定位到名为测试 000128 测试消息文件。位于名为 \Source\Samples\JMS\Test\Data\Load 子文件夹中的 JMS\\。</span><span class="sxs-lookup"><span data-stu-id="063e8-112">Click the **ReadFile** button in the RfhUtil utility, and then navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="063e8-113">此文件包含一批 128 测试消息，但该实用程序将加载只有第一个。</span><span class="sxs-lookup"><span data-stu-id="063e8-113">This file contains a batch of 128 test messages, but the utility loads only the first one.</span></span>  
  
5.  <span data-ttu-id="063e8-114">单击**RFH**选项卡，并确保只有**JMS**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="063e8-114">Click the **RFH** tab, and then make sure that only the **JMS** check box is selected.</span></span>  
  
6.  <span data-ttu-id="063e8-115">单击**jms**选项卡，并请确保所选**答复**队列是 ESB。JMS。示例。答复和的所选**目标队列**是 ESB。JMS。示例。DYNAMICQ2。</span><span class="sxs-lookup"><span data-stu-id="063e8-115">Click the **jms** tab, and then make sure that the selected **Reply To** queue is ESB.JMS.SAMPLE.REPLY and that the selected **Destination Queue** is ESB.JMS.SAMPLE.DYNAMICQ2.</span></span>  
  
7.  <span data-ttu-id="063e8-116">单击**Main**选项卡，然后依次**编写 Q**按钮可将消息写入到队列。</span><span class="sxs-lookup"><span data-stu-id="063e8-116">Click the **Main** tab, and then click the **Write Q** button to write the message into the queue.</span></span>  
  
8.  <span data-ttu-id="063e8-117">后一段延迟时应用程序执行，ESB 输出消息将出现在 ESB。JMS。示例。DYNAMICQ2 队列。</span><span class="sxs-lookup"><span data-stu-id="063e8-117">After a delay while the application executes, the ESB output message appears in the ESB.JMS.SAMPLE.DYNAMICQ2 queue.</span></span> <span data-ttu-id="063e8-118">打开 WebSphere 队列资源管理器并浏览队列来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="063e8-118">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>  
  
## <a name="how-the-sample-works"></a><span data-ttu-id="063e8-119">示例工作原理</span><span class="sxs-lookup"><span data-stu-id="063e8-119">How the Sample Works</span></span>  
 <span data-ttu-id="063e8-120">在业务流程中，代码可以访问通过加载到已在 JMS 标头的值**XmlDocument**实例，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="063e8-120">Inside the orchestration, code can access the values that were in the JMS headers by loading the message into an **XmlDocument** instance, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="063e8-121">此外，代码可以访问的所有消息的 MQMD 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="063e8-121">In addition, the code can access all of the MQMD context properties of the message.</span></span>