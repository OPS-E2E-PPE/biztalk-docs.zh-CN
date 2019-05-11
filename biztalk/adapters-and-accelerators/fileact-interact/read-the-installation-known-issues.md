---
title: 阅读已知问题安装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26aaca5ce206e8ef320b61959f04f5e0fd5657a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366534"
---
# <a name="read-the-installation-known-issues"></a>阅读安装的已知问题
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] 具有以下各节中列出的已知的问题。  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a>SWIFT 不支持压力测试集成测试平台 (ITB) 和 SWIFTNet 存根 （stub） 环境  
 ITB 不在吞吐量方面提供服务级别协议 (SLA)，并且无法保证数据是完全传输还是一致。 应在试验环境中实现对生产网络进行压力测试。  
  
 此外，必须确保所有的节点 （服务器、 线条和带宽） 进行正确配置以避免丢失任何数据。 以下是典型的示例执行次数：  
  
- 交互/Fileact 发送用量较大的计算机下：20 消息/分钟  
  
- 交互/Fileact 接收用量较大的计算机下：300-400 消息/分钟  
  
  有关详细信息，请参阅 SWIFT 文档。  
  
## <a name="messages-not-pushed-when-queue-is-open"></a>当队列处于打开状态时，未推送的消息  
 使用时交互或 FileAct 存储和转发 (SnF) 模式下，如果与队列会话处于打开状态，并且不推送消息，然后必须重新启动 SNLreceiver.exe。 这样可避免 SWIFT 可能偶尔发生的问题。  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a>您必须使用 CDATA 时将传递字符如"<"和"&"消息中  
 有关不应由 XML 分析器进行分析的文本数据使用 CDATA 的术语。  字符如"<"和"&"是非法的 XML 元素中。 "<"将生成错误，因为分析器将其解释为新元素的开头。 "&"将生成错误，因为分析器将其解释为字符实体的开头。 分析器将忽略 CDATA 节内的所有内容。 CDATA 部分开头介绍"\<！ [CDATA ["结尾"]]\>"  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a>必须使用仅限有效负载的模式下使用直通管道  
 InterAct 适配器使用仅限有效负载的模式下，如果您必须使用直通管道在这两个发送和接收端口，如果不使用自定义管道。  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a>未创建 （SWIFTNet 存根 （stub） 计算机） 的多个安全上下文  
 SWIFTNet 存根 （stub） 在计算机上，多个安全上下文的不被创建不同的发送端口。 ITB 上创建多个安全上下文。