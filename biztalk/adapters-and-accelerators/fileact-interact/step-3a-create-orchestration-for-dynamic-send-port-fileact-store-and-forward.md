---
title: "步骤 3A： 创建 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5675d476-ad36-4bbc-8e87-786edc9c805d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c91f9054885de1d19b467646ee7b82b342a76d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="2baf0-102">步骤 3A： 创建 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程</span><span class="sxs-lookup"><span data-stu-id="2baf0-102">Step 3A: Create an orchestration for dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="2baf0-103">在开始此部分中的步骤之前，必须完成中的步骤[步骤 2c: FileAct 存储和转发 （请求） 方案的 FILEACT 发送端口添加](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)部分。</span><span class="sxs-lookup"><span data-stu-id="2baf0-103">Before you begin the steps in this section, you must complete the steps in the [Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md) section.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="2baf0-104">若要创建业务流程</span><span class="sxs-lookup"><span data-stu-id="2baf0-104">To Create an Orchestration</span></span>  
  
1.  <span data-ttu-id="2baf0-105">创建订阅的所有消息类型软件 ExchangeSnFRequest 的消息的接收形状。</span><span class="sxs-lookup"><span data-stu-id="2baf0-105">Create the Receive shape that subscribes to all of the messages of message type Sw-ExchangeSnFRequest.</span></span>  
  
2.  <span data-ttu-id="2baf0-106">添加从 ExchangeRequestSnF 消息中获取所有所需的值是表达式形状。</span><span class="sxs-lookup"><span data-stu-id="2baf0-106">Add an Expression shape to get all of the required values from the ExchangeRequestSnF message.</span></span> <span data-ttu-id="2baf0-107">请参阅下面的表达式形状示例：</span><span class="sxs-lookup"><span data-stu-id="2baf0-107">Refer to the following Expression Shape sample:</span></span>  
  
    ```  
    ExchangeSnFRequestDoc=ExchangeSnFRequest;  
    AcquireQueuePath="/Sw-ExchangeSnFRequest/Sw-SnFRequest/Sw-SnFOpRequest/Sw-AcquireSnFRequest/";  
  
    QueueNameNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath + "SwInt-Queue");  
    SessionModeNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-SessionMode");  
    ForceAcquireNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-ForceAcquire");  
    OrderByNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-OrderBy");  
    RecoveryModeNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-RecoveryMode");  
  
    QueueName=QueueNameNode.InnerText;  
    SessionMode=SessionModeNode.InnerText;  
    ForceAcquire=ForceAcquireNode.InnerText;  
    OrderBy=OrderByNode.InnerText;  
    RecoveryMode=RecoveryModeNode.InnerText;  
  
    MessageFormat="FileactMessage";  
    IsPull=true;  
  
    ```  
  
3.  <span data-ttu-id="2baf0-108">有关动态发送构造类型 PullSnFRequest 的消息和 URL。</span><span class="sxs-lookup"><span data-stu-id="2baf0-108">Construct a message of type PullSnFRequest and the URL for Dynamic Send.</span></span> <span data-ttu-id="2baf0-109">请参阅分配形状的构造消息示例：</span><span class="sxs-lookup"><span data-stu-id="2baf0-109">Refer to the Assignment Shape of Construct Message sample:</span></span>  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "FILEACT://localhost/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" + OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
  
    ```  
  
4.  <span data-ttu-id="2baf0-110">在此示例中，PullMessage 是类型软件 PullSnFRequest 的消息。</span><span class="sxs-lookup"><span data-stu-id="2baf0-110">In this sample, PullMessage is a message of type Sw-PullSnFRequest.</span></span>  
  
5.  <span data-ttu-id="2baf0-111">添加发送形状发送 PullMessage （拉取请求）。</span><span class="sxs-lookup"><span data-stu-id="2baf0-111">Add a Send shape to send the PullMessage (pull request).</span></span>  
  
6.  <span data-ttu-id="2baf0-112">添加用于发送请求消息或用于对动态绑定接收的请求响应的请求-响应端口。</span><span class="sxs-lookup"><span data-stu-id="2baf0-112">Add a request-response port for sending the pull message and for receiving the pull response with the dynamic binding.</span></span>  
  
7.  <span data-ttu-id="2baf0-113">连接到在上一步中创建的端口发送形状。</span><span class="sxs-lookup"><span data-stu-id="2baf0-113">Connect the Send shape with the port created in the previous step.</span></span>  
  
8.  <span data-ttu-id="2baf0-114">添加一个接收形状接收 PullResponse （类型 PullSnFResponse 的消息），然后将接收形状连接与以前创建的端口。</span><span class="sxs-lookup"><span data-stu-id="2baf0-114">Add a Receive shape to receive the PullResponse (message of type PullSnFResponse) and then connect the Receive shape with the port previously created.</span></span>  
  
9. <span data-ttu-id="2baf0-115">将响应发送到使用发送形状的相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="2baf0-115">Send the response to the respective folder using a Send shape.</span></span>  
  
10. <span data-ttu-id="2baf0-116">如果要拉取所有消息，请添加所有这些活动 （发送拉取请求和接收响应） 循环。</span><span class="sxs-lookup"><span data-stu-id="2baf0-116">Add all of these activities (sending a pull request and receiving the response) in a loop if you want to pull all of the messages.</span></span>  
  
11. <span data-ttu-id="2baf0-117">添加表达式形状 CheckQueueEmpty 以保留拉动直到时间队列为空。</span><span class="sxs-lookup"><span data-stu-id="2baf0-117">Add an Expression shape CheckQueueEmpty to keep pulling until the time queue is empty.</span></span> <span data-ttu-id="2baf0-118">请参阅下面的表达式形状示例：</span><span class="sxs-lookup"><span data-stu-id="2baf0-118">Refer the following Expression Shape sample:</span></span>  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/Sw-PullSnFResponse/SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
  
    ```  
  
12. <span data-ttu-id="2baf0-119">这便会设置 IsPull = false，一旦队列为空。</span><span class="sxs-lookup"><span data-stu-id="2baf0-119">This will set the IsPull = false, once the queue is empty.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2baf0-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2baf0-120">See Also</span></span>  
 [<span data-ttu-id="2baf0-121">步骤 3B： 将绑定与 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程</span><span class="sxs-lookup"><span data-stu-id="2baf0-121">Step 3B: Bind the orchestration with dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-for-fileact-store-and-forward.md)