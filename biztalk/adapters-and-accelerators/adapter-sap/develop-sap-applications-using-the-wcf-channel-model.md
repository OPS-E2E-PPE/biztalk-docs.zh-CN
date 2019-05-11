---
title: 开发 SAP 应用程序使用 WCF 通道模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, developing applications by using
ms.assetid: 1ce70c8b-5eeb-4585-97af-b0a7b4398dac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7eadb0d0564fe1cec246c91c28ff192dac17f28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373514"
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a><span data-ttu-id="27eab-102">开发 SAP 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="27eab-102">Develop SAP applications using the WCF Channel Model</span></span>
<span data-ttu-id="27eab-103">可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过直接通过使用 SAP 绑定创建通道实例发送 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="27eab-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] by sending XML messages directly over a channel instance created with the SAP Binding.</span></span>  
  
 <span data-ttu-id="27eab-104">通过使用强类型化类和方法，WCF 服务模型公开了使用 WCF 通道模型的一个优点是通道模型提供更精细地控制在 SAP 系统执行的操作。</span><span class="sxs-lookup"><span data-stu-id="27eab-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the SAP system.</span></span> <span data-ttu-id="27eab-105">原因是什么？</span><span class="sxs-lookup"><span data-stu-id="27eab-105">Why?</span></span> <span data-ttu-id="27eab-106">WCF 通道模型直接控制在通道上发送的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="27eab-106">In the WCF channel model you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="27eab-107">WCF 通道模型提供了对 WCF 服务模型的另一个主要优点是对数据进行流式处理的更全面支持。</span><span class="sxs-lookup"><span data-stu-id="27eab-107">Another key advantage that the WCF channel model provides over the WCF service model is more comprehensive support for data streaming.</span></span> <span data-ttu-id="27eab-108">通过使用 WCF 通道模型，你可以执行：</span><span class="sxs-lookup"><span data-stu-id="27eab-108">By using the WCF channel model you can perform:</span></span>  
  
- <span data-ttu-id="27eab-109">你的代码和适配器之间交换的所有消息流式处理的消息节点。</span><span class="sxs-lookup"><span data-stu-id="27eab-109">Message node streaming on all messages exchanged between your code and the adapter.</span></span>  
  
- <span data-ttu-id="27eab-110">消息节点值 SendIdoc 和 ReceiveIdoc 操作流式处理。</span><span class="sxs-lookup"><span data-stu-id="27eab-110">Message node-value streaming on the SendIdoc and ReceiveIdoc operations.</span></span>  
  
  <span data-ttu-id="27eab-111">这是因为 WCF 通道模型中您可以直接控制如何提供向适配器发送的消息的消息正文和如何使用从适配器接收的消息的消息正文。</span><span class="sxs-lookup"><span data-stu-id="27eab-111">This is because in the WCF channel model you directly control how you provide the message body on messages that you send to the adapter and how you consume the message body on messages that you receive from the adapter.</span></span>  
  
  <span data-ttu-id="27eab-112">与此相反，该适配器不提供支持的 WCF 服务模型中的流式处理。</span><span class="sxs-lookup"><span data-stu-id="27eab-112">In contrast, the adapter provides no support for streaming in the WCF service model.</span></span> <span data-ttu-id="27eab-113">因为在 WCF 服务模型中，WCF 运行时序列化和反序列化其 XML 和托管的代码对象表示形式之间的消息，由完整的内存中副本的每个适配器与交换的消息。</span><span class="sxs-lookup"><span data-stu-id="27eab-113">Because, in the WCF service model, the WCF runtime serializes and deserializes messages between their XML and managed code object representations, a complete in-memory copy of each message that you exchange with the adapter is made.</span></span>  
  
  <span data-ttu-id="27eab-114">本主题中的各节说明如何执行操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="27eab-114">The sections in this topic explain how to perform operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27eab-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="27eab-115">In This Section</span></span>  
  
-   [<span data-ttu-id="27eab-116">使用 SAP 适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="27eab-116">Overview of the WCF Channel Model with the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="27eab-117">创建一个通道，使用 SAP</span><span class="sxs-lookup"><span data-stu-id="27eab-117">Create a channel using SAP</span></span>](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [<span data-ttu-id="27eab-118">SAP 系统的操作使用调用的 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="27eab-118">Invoking Operations on the SAP System by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="27eab-119">通过使用 WCF 通道模型接收来自 SAP 系统的入站的操作</span><span class="sxs-lookup"><span data-stu-id="27eab-119">Receiving Inbound Operations from the SAP System by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [<span data-ttu-id="27eab-120">SAP 使用 WCF 通道模型中的流式处理平面文件 Idoc</span><span class="sxs-lookup"><span data-stu-id="27eab-120">Streaming Flat-File IDOCs in SAP using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)