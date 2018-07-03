---
title: 增强了跟踪功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking
ms.assetid: 8adf78f0-ab0f-44d4-aa5b-9546e2bdf01f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f5fc6e16ebbdc8f76ff07c03742e3231025dc29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973342"
---
# <a name="enhanced-tracking"></a>增强的跟踪
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供流程和消息跟踪的增强的功能。 有关业务活动监视 (BAM) 中的本机功能[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]仅元数据进行跟踪。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 消息内容进行跟踪-服务内容和标头。  

 下表给出了 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 中数据跟踪的全面信息。 本主题介绍流程和消息跟踪。 有关不可否认性数据的详细信息，请参阅[RNIF 消息处理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md)。  


|           跟踪的信息           |                                                        功能                                                        |                                                                                   用户的访问权限                                                                                   |
|-----------------------------------------|-----------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RosettaNet 流程和消息跟踪 | 通过 BAM （与数据库表和数据的视图） 的元数据和消息正文的专有接口 |                                                                   BAM 用户界面或自定义用户界面                                                                   |
|            错误和事件            |                通过[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件日志                |                                                                                    事件日志                                                                                    |
|          不可否认性数据           |                         通过专用接口 （传输的消息的格式存储）                          | 中的 MessageStorageIn 和 MessageStorageOut 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]存档数据库，并通过 SDK |

## <a name="process-and-message-tracking"></a>进程和消息跟踪  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 跟踪两个基本活动： 进程活动和消息活动。 过程活动跟踪中公用业务流程的消息处理。 在中处理的消息活动跟踪消息发送或接收管道。  

 过程活动跟踪完整消息元数据。 消息活动跟踪流程活动元数据和消息的内容。  

### <a name="process-activity"></a>过程活动  
 每当实例化公用业务流程 （发起方或响应方） 时，公用流程将创建 BAM 跟踪数据库中的过程活动记录。 在公用流程中的各个点，该业务流程保存跟踪元数据。 过程活动将停止时停止业务流程。  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 对以下两个实例中流程的全部元数据进行跟踪：  

- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 作为响应方接收请求操作消息  

- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 作为发起方接收来自业务线 (LOB) 应用程序的请求消息。  

  只要 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送或接收消息，公用流程就更新流程活动的状态。  

### <a name="message-activity"></a>消息活动  
 消息活动跟踪消息通过发送和接收管道。 每当发送或接收管道处理消息、 管道创建消息的活动。 此外，该管道还会在 BAM 跟踪数据库中创建消息活动记录，并且在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive 数据库中创建消息记录。  

 消息活动将保存消息，包括服务内容和标头的内容。 在接收管道中，如果 MIME 解码器成功，该活动将保存消息内容的四个部分以 XML 形式 ContentXml 列的 MessageContent 表中的文本格式。 如果 MIME 解码器失败，该活动将消息内容保存在 ContentBinary 列的 MessageContent 表中的二进制格式。  

### <a name="use-of-tracking-data-in-correlation"></a>使用的跟踪相关的数据  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 对以下操作所需信息进行跟踪：该操作是将每个流程与特定 PIP 的所有已交换消息（正信号或负信号、请求信号和响应信号）进行关联的操作。 如果 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送该 PIP 的失败通知，则还要对用于关联 0A1 消息的信息进行跟踪。 PIP 实例 ID、 发起方参与方名称和目标参与方名称的组合确定的活动相关的消息。  

### <a name="tracking-databases"></a>跟踪数据库  
 流程活动和消息活动将跟踪的元数据保存在 BAMPrimaryImport [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库中。 在此数据库中，其名称以前缀"bam_Process"开头的表存储过程活动跟踪数据，并且其名称以前缀"bam_Message"开头的表存储消息活动的跟踪数据。 每个单独的进程或消息活动有与之对应的表中的单个记录。 有关两个活动和元数据跟踪的信息包含在其名称以前缀"bam_Metadata"开头的元数据表。  

 可以使用在 BAMPrimaryImport 跟踪数据库中使用以下视图数据。 Microsoft 中提供了这些和其他视图[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]节点的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。  

|跟踪视图|data|  
|-------------------|----------|  
|bam_Process_AllInstances|PIP 定义的 RosettaNet 流程的状态|  
|bam_Message_AllInstances|所有消息的状态|  
|bam_Process_CompletedInstances|已完成的进程的状态|  

 消息活动将消息内容保存在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive 数据库的 MessageContent 表中。 可以通过运行查询 MessageContent 表中，检查的内容，对消息使用的唯一标识符。 活动消息活动的跟踪表，请使用前缀"bam_Message ContentKey 列中存储唯一标识符。  

> [!IMPORTANT]
>  消息活动在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive 数据库的 MessageContent 表中共享明文形式的消息内容。 此错误出现在所有的跟踪方案，包括那些未加密或签名消息。 如果关心消息内容的可访问性，可以限制对 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive 数据库的访问。  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用 BAM 跟踪 API 来保存跟踪数据。  

### <a name="status-codes"></a>状态代码  
 BAMPrimaryImport 数据库中的 bam_Process_Active 和 bam_Process_Completed 表包含指示状态的进程的状态列。 下表显示了每个状态代码的值。  

|状态代码|进程状态|  
|-----------------|-------------------|  
|-1000|ActivityNotPresentFatalError|  
|-500|UnexpectedFatalError|  
|-100|Initiated0A1|  
|-99|TerminatedOnError<br /> （任何其他终止不是终止 0A1）|  
|-85|TerminatedBy0A1|  
|-75|TimedOutOnResponseSignal|  
|-50|TimedOutOnResponse|  
|-25|TimedOutOnActionSignal|  
|0|RegisteredActivity|  
|@shouldalert|ActivityToBeInitiated|  
|10|ReceivedAction 或 SentAction|  
|25|ReceivedActionSignal 或 SentActionSignal|  
|35|ReceivedActionSignal2 或 SentActionSignal2<br /> （信号 2 适用于 RNIF v11）|  
|50|ReceivedResponse 或 SentResponse|  
|75|ReceivedResponseSignal 或 SentResponseSignal|  
|85|ReceivedResponseSignal2 或 SentResponseSignal2<br /> （信号 2 适用于 RNIF v11）|  
|100|ActivityCompleted|  

### <a name="activity-definition-file"></a>活动定义文件  
 活动定义文件定义你跟踪的字段在 BAM 中，并查看它们。 有关此文件的详细信息，请参阅[使用跟踪活动定义文件](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md)。  

 有关 BAM 的详细信息，请参阅"业务活动监视 (BAM)"BizTalk Server 帮助中。  

## <a name="see-also"></a>请参阅  
 [使用跟踪活动定义文件](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md)   
 [BizTalk Accelerator for RosettaNet 向 BizTalk Server 添加的功能](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)