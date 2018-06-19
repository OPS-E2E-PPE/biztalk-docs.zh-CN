---
title: Samples3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SDK samples
- examples, developing
- developing, examples
ms.assetid: b940111e-4f71-494b-b7a3-d2e8310bea51
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d81e5fe477aca032714ca124d8300c9b6c2d5ba
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965755"
---
# <a name="samples"></a>示例
本节介绍 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 软件开发工具包 (SDK) 中包含的示例。 本节提供有关每个示例的详细信息，其中包括如何生成示例，如何运行它以及所期望的结果。  
  
 这些示例都将纳入\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>Accelerator for RosettaNet\SDK\ 文件夹。  
  
## <a name="in-this-section"></a>本节内容  
  
-   适配器示例文件夹  
  
    -   [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)。 演示如何包含消息通知机制。  
  
    -   [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)。 演示如何对消息运行特殊验证规则。  
  
-   消息传送示例文件夹  
  
    -   [FileTransport 示例](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)。 演示如何配置 BTARN，让其使用文件端口。  
  
    -   [GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)。 演示如何从不可否认性表之一或业务线 (LOB) 表之一检索消息。  
  
    -   [消息提交 ASPX 示例](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)。 提供用于将服务内容提交给专用流程的示例 .aspx 代码。 此外，还提供用于将合作伙伴接口流程 (PIP) 操作消息提交给该服务内容的 HTML。  
  
    -   [跟踪示例](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)。 提供用于查看 BTARN 所发送和接收的消息的状态的示例 .aspx 代码。  
  
-   业务流程示例文件夹  
  
    -   [使用业务规则 3A4 私有响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。 演示如何使用将请求消息转换为响应消息的映射来使包含 PIP 的业务流程自动运行。  
  
    -   [Double 操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)。 演示如何基于传入消息类型自动确定响应消息类型来使业务流程自动运行。  
  
    -   [对 3A2 响应映射示例 3A2 请求](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)。 演示如何将 3A2 请求架构映射到 3A2 响应架构。  
  
    -   [对 3A4 响应映射示例 3A4 请求](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)。 演示如何将 3A4 请求架构映射到 3A4 响应架构。  
  
    -   [PrivateInitiator 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)。 演示如何创建发起方专用业务流程。  
  
    -   [PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)。 演示如何创建响应方专用业务流程。  
  
    -   [HubScenario 示例](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)。 演示如何将发送到中间网络集线器的消息转换为发送到最终接收人的消息。  
  
-   管道示例文件夹  
  
    -   [发送管道](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)。 演示如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 管道将传出 XML 消息加工成等效的 RNIF 消息。  
  
    -   [接收管道](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)。 演示如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 管道将传入 RNIF 消息加工成等效的 XML 消息。  
  
    -   [消息编辑器管道示例](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)。 演示如何创建用于编辑传入消息的自定义管道组件。  
  
-   架构示例文件夹  
  
    -   [架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。 介绍 SDK 中提供的示例架构，其中包括 PIP XML 架构、RosettaNet 下一代架构和 RNIF 架构。 包含关于使用这些架构的步骤的链接。  
  
-   Web 应用程序示例文件夹  
  
    -   [RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)。 演示如何自定义从发起方向响应方发送 RNIF 消息的 ASPX 页。  
  
    -   [RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)。 演示如何自定义在响应方接收 RNIF 消息的 ASPX 页。  
  
-   [停止和启动业务流程，发送端口，并以编程方式接收位置](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)。 演示如何按组或逐个停止和启动所有业务流程、发送端口和接收位置。