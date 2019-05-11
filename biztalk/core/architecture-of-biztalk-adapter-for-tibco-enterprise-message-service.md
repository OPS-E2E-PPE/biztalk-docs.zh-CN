---
title: 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器的体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transmit adapter
- one-way receive operations
- architecture
- one-way send operations
- receive adapter
ms.assetid: 304c7236-aacd-4761-8c33-e876b53e84ff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d1f6735ec5fee445fa5f2403f7ca48d32dfae2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359015"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="bf0e9-102">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器的体系结构</span><span class="sxs-lookup"><span data-stu-id="bf0e9-102">Architecture of BizTalk Adapter for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="bf0e9-103">用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供了一种方法来交换 TIBCO EMS 系统和 BizTalk Server 之间的实时业务数据。</span><span class="sxs-lookup"><span data-stu-id="bf0e9-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="bf0e9-104">适配器允许 XML 应用程序与 TIBCO EMS 之间的交互。</span><span class="sxs-lookup"><span data-stu-id="bf0e9-104">The adapter enables interaction between an XML application and TIBCO EMS.</span></span>  
  
 <span data-ttu-id="bf0e9-105">适配器接受 XML 消息，使 BizTalk 应用程序与 TIBCO EMS 使用以下方法之一进行通信：</span><span class="sxs-lookup"><span data-stu-id="bf0e9-105">The adapter accepts XML messages that enable BizTalk applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="bf0e9-106">**传输适配器**:使用静态单向发送端口将消息发送到 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="bf0e9-106">**Transmit Adapter**: Uses a static one-way send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="bf0e9-107">**接收适配器**:使用静态单向接收端口以接收来自 TIBCO EMS 的消息。</span><span class="sxs-lookup"><span data-stu-id="bf0e9-107">**Receive Adapter**: Uses a static one-way receive port to receive messages from TIBCO EMS.</span></span>  
  
## <a name="one-way-send-operation"></a><span data-ttu-id="bf0e9-108">单向发送操作</span><span class="sxs-lookup"><span data-stu-id="bf0e9-108">One-Way Send Operation</span></span>  
 <span data-ttu-id="bf0e9-109">下图显示了使用用于 TIBCO EMS 的 BizTalk 适配器的单向发送操作的体系结构。</span><span class="sxs-lookup"><span data-stu-id="bf0e9-109">The following figure shows the architecture of a one-way send operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 <span data-ttu-id="bf0e9-110">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span><span class="sxs-lookup"><span data-stu-id="bf0e9-110">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span></span>  
  
## <a name="one-way-receive-operation"></a><span data-ttu-id="bf0e9-111">单向接收操作</span><span class="sxs-lookup"><span data-stu-id="bf0e9-111">One-Way Receive Operation</span></span>  
 <span data-ttu-id="bf0e9-112">下图显示了体系结构进行的单向接收操作使用用于 TIBCO EMS 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="bf0e9-112">The following figure shows the architecture for a one-way receive operation using BizTalk Adapter for TIBCO EMS.</span></span>  
  
 <span data-ttu-id="bf0e9-113">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span><span class="sxs-lookup"><span data-stu-id="bf0e9-113">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0e9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf0e9-114">See Also</span></span>  
 <span data-ttu-id="bf0e9-115">[适配器功能](../core/adapter-features.md) </span><span class="sxs-lookup"><span data-stu-id="bf0e9-115">[Adapter Features](../core/adapter-features.md) </span></span>  
 [<span data-ttu-id="bf0e9-116">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="bf0e9-116">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)