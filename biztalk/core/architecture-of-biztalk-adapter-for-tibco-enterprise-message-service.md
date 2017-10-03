---
title: "BizTalk 适配器 TIBCO 企业消息服务的体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transmit adapter
- one-way receive operations
- architecture
- one-way send operations
- receive adapter
ms.assetid: 304c7236-aacd-4761-8c33-e876b53e84ff
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c7bc6420efb67085e4f3a05f6daf0c5dbd2feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="0eb8a-102">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器的体系结构</span><span class="sxs-lookup"><span data-stu-id="0eb8a-102">Architecture of BizTalk Adapter for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="0eb8a-103">用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供在 TIBCO EMS 系统和 BizTalk Server 之间交换实时业务数据的方式。</span><span class="sxs-lookup"><span data-stu-id="0eb8a-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="0eb8a-104">该适配器能够在 XML 应用程序和 TIBCO EMS 之间进行交互。</span><span class="sxs-lookup"><span data-stu-id="0eb8a-104">The adapter enables interaction between an XML application and TIBCO EMS.</span></span>  
  
 <span data-ttu-id="0eb8a-105">该适配器使用下列适配器之一接受使 BizTalk 应用程序与 TIBCO EMS 进行通信的 XML 消息：</span><span class="sxs-lookup"><span data-stu-id="0eb8a-105">The adapter accepts XML messages that enable BizTalk applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="0eb8a-106">**传输适配器**： 使用静态单向发送端口将消息发送到 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="0eb8a-106">**Transmit Adapter**: Uses a static one-way send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="0eb8a-107">**接收适配器**： 使用静态单向接收端口从 TIBCO EMS 接收消息。</span><span class="sxs-lookup"><span data-stu-id="0eb8a-107">**Receive Adapter**: Uses a static one-way receive port to receive messages from TIBCO EMS.</span></span>  
  
## <a name="one-way-send-operation"></a><span data-ttu-id="0eb8a-108">单向发送操作</span><span class="sxs-lookup"><span data-stu-id="0eb8a-108">One-Way Send Operation</span></span>  
 <span data-ttu-id="0eb8a-109">下图显示使用用于 TIBCO EMS 的 BizTalk 适配器进行的单向发送操作的体系结构。</span><span class="sxs-lookup"><span data-stu-id="0eb8a-109">The following figure shows the architecture of a one-way send operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a><span data-ttu-id="0eb8a-110">单向接收操作</span><span class="sxs-lookup"><span data-stu-id="0eb8a-110">One-Way Receive Operation</span></span>  
 <span data-ttu-id="0eb8a-111">下图显示使用用于 TIBCO EMS 的 BizTalk 适配器进行的单向接收操作的体系结构。</span><span class="sxs-lookup"><span data-stu-id="0eb8a-111">The following figure shows the architecture for a one-way receive operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a><span data-ttu-id="0eb8a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eb8a-112">See Also</span></span>  
 <span data-ttu-id="0eb8a-113">[适配器功能](../core/adapter-features.md) </span><span class="sxs-lookup"><span data-stu-id="0eb8a-113">[Adapter Features](../core/adapter-features.md) </span></span>  
 [<span data-ttu-id="0eb8a-114">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="0eb8a-114">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)