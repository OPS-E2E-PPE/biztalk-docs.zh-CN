---
title: "提交通过消息接收位置和 InfoPath 窗体 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6cddeca2eb80fbeb7c9fb5742e2838a860079d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a><span data-ttu-id="2e1f2-102">通过提交消息接收位置和 InfoPath 窗体</span><span class="sxs-lookup"><span data-stu-id="2e1f2-102">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>
<span data-ttu-id="2e1f2-103">接收位置接收消息提交至[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-103">Receive locations receive messages for submission into [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] applications.</span></span> <span data-ttu-id="2e1f2-104">你可以定义接收位置作为物理终结点配置为接收使用指定的传输协议的消息。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-104">You can define receive locations as physical endpoints configured to receive messages using a specified transport protocol.</span></span> <span data-ttu-id="2e1f2-105">例如，接收位置可能配置为拖放到特定的文件系统文件夹使用文件传输的接收文件。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-105">For example, a receive location may be configured to receive files dropped to a particular file system folder using the FILE transport.</span></span>  
  
 <span data-ttu-id="2e1f2-106">你创建的逻辑分组，并管理的接收端口接收位置接收位置。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-106">You create receive locations for receive ports that logically group and manage receive locations.</span></span> <span data-ttu-id="2e1f2-107">对于每个接收位置中，你将指定接收管道，在该特定接收位置接收的消息的实际处理 （解码、 反汇编、 验证和等等） 的作用。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-107">For each receive location you specify a receive pipeline, which does the actual processing (decoding, disassembly, validation, and so on) of messages received at that particular receive location.</span></span> <span data-ttu-id="2e1f2-108">A4SWIFT 绑定接收位置接收逻辑分组，并管理的端口接收位置。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-108">A4SWIFT binds receive locations to receive ports that logically group and manage receive locations.</span></span>  
  
 <span data-ttu-id="2e1f2-109">若要提交到 A4SWIFT 应用程序接收位置通过 SWIFT 消息，消息必须是拖放到配置的接收位置、 通过使用 SWIFT 反汇编程序接收管道处理、 分析和通过 SWIFT 反汇编程序中，验证和发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-109">To submit a SWIFT message into an A4SWIFT application through a receive location, the message must be dropped to a configured receive location, processed by a receive pipeline using the SWIFT disassembler, parsed and validated by the SWIFT disassembler, and published to the MessageBox database.</span></span> <span data-ttu-id="2e1f2-110">消息发布到 MessageBox 数据库之后，你 A4SWIFT 的应用程序中的其他组件以进行其他处理检索 （使用订阅） 的消息。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-110">After messages are published to the MessageBox database, other components in your A4SWIFT application retrieve the messages (using subscriptions) for additional processing.</span></span> <span data-ttu-id="2e1f2-111">例如，可用于发送端口最终路由。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-111">For example, you can use send ports for final routing.</span></span>  
  
 <span data-ttu-id="2e1f2-112">有关创建和配置详细信息接收端口和接收位置，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-112">For more information about creating and configuring receive ports and receive locations, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="2e1f2-113">您还可以提交一条新消息通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，使用消息修复和新提交功能。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-113">You can also submit a new message through an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, using the Message Repair and New Submission feature.</span></span> <span data-ttu-id="2e1f2-114">若要执行此操作，你可以打开[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]该消息从 MRSR 网站的文件夹中的窗体。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-114">To do so, you open the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for that message from a folder in the MRSR site.</span></span> <span data-ttu-id="2e1f2-115">在中的数据填充[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体、 使用您的证书，其签名，然后提交它。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-115">You fill in the data in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, sign it using your certificate, and then submit it.</span></span> <span data-ttu-id="2e1f2-116">消息修复和新提交业务流程处理的消息。</span><span class="sxs-lookup"><span data-stu-id="2e1f2-116">The Message Repair and New Submission orchestration processes the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e1f2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e1f2-117">See Also</span></span>  
 [<span data-ttu-id="2e1f2-118">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="2e1f2-118">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)