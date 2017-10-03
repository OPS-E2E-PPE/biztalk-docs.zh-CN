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
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>步骤 3A： 创建 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程
在开始此部分中的步骤之前，必须完成中的步骤[步骤 2c: FileAct 存储和转发 （请求） 方案的 FILEACT 发送端口添加](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)部分。  
  
### <a name="to-create-an-orchestration"></a>若要创建业务流程  
  
1.  创建订阅的所有消息类型软件 ExchangeSnFRequest 的消息的接收形状。  
  
2.  添加从 ExchangeRequestSnF 消息中获取所有所需的值是表达式形状。 请参阅下面的表达式形状示例：  
  
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
  
3.  有关动态发送构造类型 PullSnFRequest 的消息和 URL。 请参阅分配形状的构造消息示例：  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "FILEACT://localhost/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" + OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
  
    ```  
  
4.  在此示例中，PullMessage 是类型软件 PullSnFRequest 的消息。  
  
5.  添加发送形状发送 PullMessage （拉取请求）。  
  
6.  添加用于发送请求消息或用于对动态绑定接收的请求响应的请求-响应端口。  
  
7.  连接到在上一步中创建的端口发送形状。  
  
8.  添加一个接收形状接收 PullResponse （类型 PullSnFResponse 的消息），然后将接收形状连接与以前创建的端口。  
  
9. 将响应发送到使用发送形状的相应文件夹。  
  
10. 如果要拉取所有消息，请添加所有这些活动 （发送拉取请求和接收响应） 循环。  
  
11. 添加表达式形状 CheckQueueEmpty 以保留拉动直到时间队列为空。 请参阅下面的表达式形状示例：  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/Sw-PullSnFResponse/SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
  
    ```  
  
12. 这便会设置 IsPull = false，一旦队列为空。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3B： 将绑定与 FileAct 应用商店应用和向前 （请求） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-for-fileact-store-and-forward.md)