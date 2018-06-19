---
title: RosettaNet 快捷键 BizTalk Server 中的软件开发工具包 |Microsoft 文档
description: BizTalk Server BTARN SDK 中的实用程序和示例列表
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36a1b283-26e1-407e-afc4-8879ef0d1672
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81bf0f7f0947875540d835ced3726224525f23a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211277"
---
# <a name="software-development-kit"></a>软件开发工具包
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]包括包括完整程序员参考和指南软件开发工具包 (SDK)。 还包括便于操作和后端集成的实用工具和示例。  
  
## <a name="utilities"></a>实用程序  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括下列示例：  
  
|实用工具|改用|  
|-------------|---------|  
|[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)|取消部署主机的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 组中的所有 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 项目|  
|[BtarnConfig](../../adapters-and-accelerators/accelerator-rosettanet/btarnconfig.md)|导入或导出配置数据|  
|[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)|导入证书的步骤|  
|[LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)|向贸易合作伙伴提交操作消息或响应消息|  
|[LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)|从 ASPX 页向贸易合作伙伴提交操作消息或响应消息|  
|[环回](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)|生成环回协议，在一台计算机上安装 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]|  
|[消息编辑器管道组件](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-component.md)|在发送或接收管道内自动编辑多部分消息的任何部分|  
|[消息检查器管道组件](../../adapters-and-accelerators/accelerator-rosettanet/message-inspector-pipeline-component.md)|检查多部分消息的所有部分和消息上下文|  
|[SchemaValidator](../../adapters-and-accelerators/accelerator-rosettanet/schemavalidator.md)|在消息实例中排除故障|  
|[TestCrypto](../../adapters-and-accelerators/accelerator-rosettanet/testcrypto.md)|在解密消息时排除故障|  
  
## <a name="samples"></a>示例  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括下列示例：  
  
|示例|演示|  
|------------|------------------|  
|[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)|如何在消息到达时发送通知|  
|[ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)|如何对业务流程从贸易合作伙伴接收的消息运行特殊的验证规则|  
|[FileTransport 示例](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)|如何使用文件端口而不是 SQL 端口|  
|[GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)|如何以可读形式在一个不可否认性表或一个 LOB 表中检索消息|  
|[消息提交 ASPX 示例](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)|如何向专用流程提交服务内容|  
|[跟踪示例](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)|如何显示消息和流程的当前状态|  
|[使用业务规则 3A4 私有响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)|如何实现并入业务规则的响应方专用流程|  
|[Double 操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)|如何实现能够自动生成双操作合作伙伴接口流程 (PIP) 响应的业务流程|  
|[3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)|如何将 3A2 请求映射到 3A2 响应|  
|[3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)|如何将 3A4 请求映射到 3A4 响应|  
|[PrivateInitiator 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)|如何实现发起方专用流程|  
|[PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)|如何实现响应方专用流程|  
|[HubScenario 示例](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)|如何管理中心方案中的消息传输|  
|[发送管道](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)|如何实现发送管道|  
|[接收管道](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)|如何实现接收管道|  
|[消息编辑器管道示例](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)|如何修改传入消息的内容|  
|[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)|如何修改架构|  
|[RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)|如何为 RNIF 处理准备消息，并将该消息发送到响应方的 RNIFReceive.aspx 页|  
|[RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)|如何接收 RNIF 消息并准备它，以供 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 公用流程处理|  
|[停止和启动业务流程，发送端口，并以编程方式接收位置](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)|如何动态停止和启动这些项目|  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for RosettaNet 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [示例](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)