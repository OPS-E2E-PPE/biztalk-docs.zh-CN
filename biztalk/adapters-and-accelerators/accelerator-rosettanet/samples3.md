---
title: Samples3 | Microsoft Docs
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
ms.openlocfilehash: 640b33a351aac79028e065215a31f1f536fad8c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282062"
---
# <a name="samples"></a>示例
本部分介绍的示例包含在 microsoft Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]软件开发工具包 (SDK)。 本部分提供有关每个示例，包括如何生成示例，如何运行它，以及所期望的结果的详细的信息。  

 这些示例包含在\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\ 文件夹。  

## <a name="in-this-section"></a>本节内容  

- 适配器示例文件夹  

  -   [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)。 演示如何包含消息通知机制。  

  -   [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)。 演示如何对消息运行特殊验证规则。  

- 消息传送示例文件夹  

  -   [FileTransport 示例](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)。 演示如何配置 btarn，让其使用文件端口。  

  -   [GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)。 演示如何从不可否认性表之一或业务线 (LOB) 表之一检索消息。  

  -   [消息提交 ASPX 示例](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)。 提供用于将提交给专用流程的服务内容的示例.aspx 代码。 此外提供了 HTML 合作伙伴接口流程 (PIP) 操作将消息提交给该服务内容。  

  -   [跟踪示例](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)。 提供用于查看状态的发送和接收的 BTARN 消息的示例.aspx 代码。  

- 业务流程示例文件夹  

  -   [使用业务规则的 3A4 专用响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。 演示如何来使包含 Pip 使用映射将转换为响应消息的请求消息的业务流程。  

  -   [双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)。 演示如何实现自动化业务流程，基于传入的消息类型的响应消息类型自动确定。  

  -   [3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)。 演示如何将 3A2 请求架构映射到 3A2 响应架构。  

  -   [3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)。 演示如何将 3A4 请求架构映射到 3A4 响应架构。  

  -   [PrivateInitiator 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)。 演示如何创建发起方专用业务流程。  

  -   [PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)。 演示如何创建响应方专用业务流程。  

  -   [HubScenario 示例](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)。 演示如何将转换为消息要发送到最终接收人发送到中间网络集线器的消息。  

- 管道示例文件夹  

  - [发送管道](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)。 演示如何使用将传出 XML 消息加工成等效的 RNIF 消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管道。  

  - [接收管道](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)。 演示如何通过将传入 RNIF 消息加工成等效的 XML 消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管道。  

  - [消息编辑器管道示例](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)。 演示如何创建用于编辑传入消息的自定义管道组件。  

- 架构示例文件夹  

  -   [架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。 介绍 SDK，其中包括 PIP XML 架构、 RosettaNet 下一代架构和 RNIF 架构中提供的示例架构。 包括的步骤使用这些架构的链接。  

- Web 应用程序示例文件夹  

  -   [RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)。 演示如何自定义从发起方向响应方发送 RNIF 消息的 ASPX 页。  

  -   [RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)。 演示如何自定义在响应方接收 RNIF 消息的 ASPX 页。  

- [停止和启动业务流程、 发送端口和接收位置以编程方式](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)。 演示如何停止和启动所有业务流程、 发送端口和接收作为一个组或单独的位置。
