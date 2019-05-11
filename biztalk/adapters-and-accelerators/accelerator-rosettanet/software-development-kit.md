---
title: 有关 BizTalk Server 中的 RosettaNet 加速器的软件开发工具包 |Microsoft Docs
description: 在 BizTalk Server 在 BTARN SDK 中的实用工具和示例列表
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
ms.openlocfilehash: 64585ba6078ff93201c37fcda2d31d7dcd43efbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281815"
---
# <a name="software-development-kit"></a>软件开发工具包
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]包括软件开发工具包 (SDK) 包括完整的程序员参考和指南。 此外，SDK 包括实用程序和示例，可以使您的操作和后端集成更轻松。  

## <a name="utilities"></a>实用程序  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包含了以下示例：  


|                                                                实用工具                                                                 |                                                                                                                    改用                                                                                                                    |
|----------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           [BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)                           | 若要取消部署所有[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]项目从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机计算机的组 |
|                          [BtarnConfig](../../adapters-and-accelerators/accelerator-rosettanet/btarnconfig.md)                          |                                                                                                  若要导入或导出配置数据                                                                                                   |
|                           [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)                           |                                                                                                          若要导入证书                                                                                                          |
|                       [LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)                       |                                                                                       若要提交给贸易合作伙伴的操作或响应消息                                                                                        |
|                    [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)                    |                                                                              若要提交操作或响应来自的消息的 ASPX 页向贸易合作伙伴                                                                               |
|                             [Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)                             |                                          若要生成环回协议，设置[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]向上一台计算机上                                          |
|    [消息编辑器管道组件](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-component.md)    |                                                                          若要自动编辑任何部分的多部分消息中发送或接收管道                                                                          |
| [消息检查器管道组件](../../adapters-and-accelerators/accelerator-rosettanet/message-inspector-pipeline-component.md) |                                                                                 若要检查的多部分消息和消息上下文的所有部分                                                                                  |
|                      [SchemaValidator](../../adapters-and-accelerators/accelerator-rosettanet/schemavalidator.md)                      |                                                                                             若要进行故障排除问题的消息实例                                                                                              |
|                           [TestCrypto](../../adapters-and-accelerators/accelerator-rosettanet/testcrypto.md)                           |                                                                                              若要排查在解密消息的失败                                                                                              |

## <a name="samples"></a>示例  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包含了以下示例：  


|                                                                                                            示例                                                                                                            |                                                                               演示                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                              [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)                                                              |                                                           如何将通知发送一条消息到达时                                                            |
|                                                               [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)                                                               |                                  如何对业务流程从贸易合作伙伴接收的消息运行特殊验证规则                                  |
|                                                            [FileTransport 示例](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)                                                            |                                                                如何使用文件端口而不是 SQL 端口                                                                |
|                                                              [GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)                                                              |                                如何从不可否认性表中的一个或一个 LOB 表中的易读形式检索消息                                |
|                                                  [消息提交 ASPX 示例](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)                                                  |                                                            如何提交给专用流程的服务内容                                                             |
|                                                                 [跟踪示例](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)                                                                 |                                                        如何显示消息和流程的当前状态                                                        |
|                       [使用业务规则的 3A4 专用响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)                       |                                                如何实现合并了业务规则的响应方专用流程                                                 |
|                                       [双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)                                       |                        如何实现为双操作合作伙伴接口流程 (Pip) 自动生成响应的业务流程                         |
|                                          [3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)                                          |                                                                如何将 3A2 请求映射到 3A2 响应                                                                 |
|                                          [3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)                                          |                                                                如何将 3A4 请求映射到 3A4 响应                                                                 |
|                                                         [PrivateInitiator 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)                                                         |                                                              如何实现发起方专用流程                                                               |
|                                                         [PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)                                                         |                                                              如何实现响应方专用流程                                                               |
|                                                              [HubScenario 示例](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)                                                              |                                                           如何管理中心方案中的消息传输                                                            |
|                                                                   [发送管道](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)                                                                   |                                                                     如何实现发送管道                                                                      |
|                                                                [接收管道](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)                                                                |                                                                    如何实现接收管道                                                                    |
|                                                  [消息编辑器管道示例](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)                                                  |                                                             如何修改传入消息的内容                                                             |
|                                                                  [架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)                                                                  |                                                                           如何修改架构                                                                           |
|                                                                        [RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)                                                                        |                             如何准备供 RNIF 处理的消息并将消息发送到响应方的 RNIFReceive.aspx 页                              |
|                                                                     [RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)                                                                     | 如何接收 RNIF 消息，并准备它以供处理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用流程 |
| [以编程方式停止和启动业务流程、发送端口和接收位置](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md) |                                                             如何停止和启动这些项目动态                                                             |

## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for RosettaNet 向 BizTalk Server 的添加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [示例](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)