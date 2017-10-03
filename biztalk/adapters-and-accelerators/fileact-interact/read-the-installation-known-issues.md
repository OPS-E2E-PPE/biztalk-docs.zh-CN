---
title: "读取的已知问题的安装 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f11e713d09ca8babcf7622710fd63bde9980373
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="read-the-installation-known-issues"></a>读取安装的已知问题
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]具有下列部分中列出已知的问题。  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a>SWIFT 不支持集成的测试平台上 (ITB) 和 SWIFTNet 存根 （stub） 环境中测试的压力  
 ITB 不会根据吞吐量，提供服务级别协议 (SLA)，并且不能保证数据是完全传输还是一致。 你应在生产环境实现网络在试验环境中的压力测试。  
  
 此外，你必须确保对所有节点 （服务器、 线条和带宽） 将进行正确配置，为了避免丢失任何数据。 以下是典型示例吞吐量：  
  
-   交互/Fileact 发送重音计算机下： 20 的邮件/分钟  
  
-   交互/Fileact 接收重音计算机下： 每分钟 300-400 消息数  
  
 有关详细信息，请参阅 SWIFT 文档。  
  
## <a name="messages-not-pushed-when-queue-is-open"></a>打开队列时未推送的消息  
 如果你使用交互或 FileAct 应用商店和进 (SnF) 模式下，如果与队列会话保持打开状态，不被推送消息，然后你必须重启 SNLreceiver.exe。 这样就避免了 SWIFT 可能偶尔发生的问题。  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a>你必须使用 CDATA 时将传递字符，例如"<"和"&"消息中  
 CDATA 使用有关不应由 XML 分析器分析的文本数据的术语。  字符，例如"<"和"&"在 XML 元素中是非法。 "<"将生成错误，因为分析器将其解释为新元素的开头。 "&"将生成错误，因为分析器将其解释为字符实体的开头。 分析器会忽略所有内容在 CDATA 节内。 CDATA 部分开头介绍"\<！ [CDATA ["和结束的"]] >"  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a>你必须使用带有仅负载模式传递管道  
 如果为交互适配器使用仅负载模式，必须传递管道使用这两个发送和接收端口，如果你不使用自定义管道。  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a>未创建 （SWIFTNet 存根 （stub） 计算机） 的多个安全上下文  
 SWIFTNet 存根 （stub） 在计算机上，多个安全上下文的不被创建不同发送端口。 ITB 上创建多个安全上下文。