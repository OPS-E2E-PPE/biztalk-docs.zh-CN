---
title: 提交消息通过接收位置和 InfoPath 窗体 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf95acf08084f7382e166efdace182a4464178c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377010"
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a><span data-ttu-id="4b1a3-102">提交消息通过接收位置和 InfoPath 窗体</span><span class="sxs-lookup"><span data-stu-id="4b1a3-102">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>
<span data-ttu-id="4b1a3-103">接收位置接收消息提交到[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-103">Receive locations receive messages for submission into [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] applications.</span></span> <span data-ttu-id="4b1a3-104">您可以定义接收位置作为物理终结点配置为使用指定的传输协议接收消息。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-104">You can define receive locations as physical endpoints configured to receive messages using a specified transport protocol.</span></span> <span data-ttu-id="4b1a3-105">例如，接收位置可能配置为接收文件拖放到特定的文件系统文件夹，使用文件传输。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-105">For example, a receive location may be configured to receive files dropped to a particular file system folder using the FILE transport.</span></span>  
  
 <span data-ttu-id="4b1a3-106">创建接收端口，以逻辑方式分组和管理接收位置的接收位置。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-106">You create receive locations for receive ports that logically group and manage receive locations.</span></span> <span data-ttu-id="4b1a3-107">对于每个接收位置指定接收管道，它会在该特定的接收位置接收消息的实际处理 （解码、 拆装、 验证等）。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-107">For each receive location you specify a receive pipeline, which does the actual processing (decoding, disassembly, validation, and so on) of messages received at that particular receive location.</span></span> <span data-ttu-id="4b1a3-108">A4SWIFT 绑定接收位置接收端口的逻辑分组并管理接收位置。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-108">A4SWIFT binds receive locations to receive ports that logically group and manage receive locations.</span></span>  
  
 <span data-ttu-id="4b1a3-109">以将 SWIFT 消息提交到 A4SWIFT 应用程序，通过接收位置，消息必须进行拖放到已配置的接收位置，由接收管道使用 SWIFT 反汇编程序进行处理、 分析并由 SWIFT 反汇编程序、 验证和发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-109">To submit a SWIFT message into an A4SWIFT application through a receive location, the message must be dropped to a configured receive location, processed by a receive pipeline using the SWIFT disassembler, parsed and validated by the SWIFT disassembler, and published to the MessageBox database.</span></span> <span data-ttu-id="4b1a3-110">消息发布到 MessageBox 数据库后，A4SWIFT 应用程序中的其他组件中检索进行其他处理 （使用订阅） 的消息。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-110">After messages are published to the MessageBox database, other components in your A4SWIFT application retrieve the messages (using subscriptions) for additional processing.</span></span> <span data-ttu-id="4b1a3-111">例如，可用于发送端口最终路由。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-111">For example, you can use send ports for final routing.</span></span>  
  
 <span data-ttu-id="4b1a3-112">详细了解创建和配置接收端口和接收位置，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-112">For more information about creating and configuring receive ports and receive locations, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="4b1a3-113">您还可以提交新消息通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，使用消息修复和新提交功能。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-113">You can also submit a new message through an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, using the Message Repair and New Submission feature.</span></span> <span data-ttu-id="4b1a3-114">若要执行此操作，打开[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体从 MRSR 网站的文件夹中，该消息。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-114">To do so, you open the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for that message from a folder in the MRSR site.</span></span> <span data-ttu-id="4b1a3-115">在中的数据填充[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体，它使用证书，请登录，然后将其提交。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-115">You fill in the data in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, sign it using your certificate, and then submit it.</span></span> <span data-ttu-id="4b1a3-116">消息修复和新提交业务流程处理消息。</span><span class="sxs-lookup"><span data-stu-id="4b1a3-116">The Message Repair and New Submission orchestration processes the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b1a3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b1a3-117">See Also</span></span>  
 [<span data-ttu-id="4b1a3-118">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="4b1a3-118">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)