---
title: 步骤 3a:创建为 FileAct 存储和转发 （拉取） 方案的动态发送端口业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5675d476-ad36-4bbc-8e87-786edc9c805d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346c45e35609ab6c8f74fcc9b982b9b3f5e21aaf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365876"
---
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>步骤 3a:创建为 FileAct 存储和转发 （拉取） 方案的动态发送端口业务流程
在开始本部分中的步骤之前，必须完成中的步骤[步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)部分。  
  
### <a name="to-create-an-orchestration"></a>若要创建一个业务流程  
  
1.  创建订阅的所有消息类型 Sw ExchangeSnFRequest 的消息的接收形状。  
  
2.  添加表达式形状 ExchangeRequestSnF 消息中获取所有所需的值。 请参阅下面的表达式形状示例：  
  
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
  
3.  为动态发送构造类型 PullSnFRequest 的消息和 URL。 请参阅构造消息赋值形状示例：  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "FILEACT://localhost/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" + OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
  
    ```  
  
4.  在此示例中，PullMessage 是软件 PullSnFRequest 类型的消息。  
  
5.  添加发送形状发送 PullMessage （拉取请求）。  
  
6.  添加用于发送请求消息并使用动态绑定接收的请求响应的请求-响应端口。  
  
7.  发送形状连接上一步中创建的端口。  
  
8.  添加接收形状接收 PullResponse （消息类型 PullSnFResponse 的），并使用以前创建的端口连接接收形状。  
  
9. 将响应发送到使用发送形状的相应文件夹。  
  
10. 如果你想要将所有消息，请添加这些活动 （发送拉取请求和接收响应） 的所有循环。  
  
11. 添加表达式形状 CheckQueueEmpty 以保持拉动直到时间队列为空。 下面的表达式形状示例，请参阅：  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/Sw-PullSnFResponse/SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
  
    ```  
  
12. 这会设置 IsPull = false，一旦队列为空。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3b:将替换为 FileAct 存储和转发 （拉取） 方案的动态发送端口业务流程绑定](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-for-fileact-store-and-forward.md)