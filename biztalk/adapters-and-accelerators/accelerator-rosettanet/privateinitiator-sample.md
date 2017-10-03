---
title: "PrivateInitiator 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d33b164033cdd3b966ed1f0e77dd551cd56076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="privateinitiator-sample"></a><span data-ttu-id="c07f1-102">PrivateInitiator 示例</span><span class="sxs-lookup"><span data-stu-id="c07f1-102">PrivateInitiator Sample</span></span>
<span data-ttu-id="c07f1-103">PrivateInitiator.odx 示例包含 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 安装的发起方专用流程的代码。</span><span class="sxs-lookup"><span data-stu-id="c07f1-103">The PrivateInitiator.odx sample contains the code for the initiator private process installed by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="c07f1-104">此通用专用流程从基于默认的 SQL 适配器的发送和接收端口发送和接收 RNIF 服务内容消息。</span><span class="sxs-lookup"><span data-stu-id="c07f1-104">This is a generic private process that sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="c07f1-105">默认情况下，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\ 快捷键PrivateInitiator。</span><span class="sxs-lookup"><span data-stu-id="c07f1-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateInitiator.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="c07f1-106">示例内容</span><span class="sxs-lookup"><span data-stu-id="c07f1-106">Sample Contents</span></span>  
 <span data-ttu-id="c07f1-107">发起方专用流程是发起方内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c07f1-107">The initiator private process is the business process that is internal to the initiator.</span></span> <span data-ttu-id="c07f1-108">该专用流程提供发起方公用流程和后端业务线程序之间的后端集成。</span><span class="sxs-lookup"><span data-stu-id="c07f1-108">The private process provides back-end integration between the initiator public process and the back-end line-of-business program.</span></span> <span data-ttu-id="c07f1-109">发起方专用流程与公用流程进行通信以发起消息。</span><span class="sxs-lookup"><span data-stu-id="c07f1-109">The initiator private process communicates with the public process to initiate messages.</span></span>  
  
 <span data-ttu-id="c07f1-110">每个实现的发起方专用流程都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c07f1-110">The initiator private process is unique for each implementation.</span></span> <span data-ttu-id="c07f1-111">可以根据所需自定义 PrivateInitiator.odx 示例。</span><span class="sxs-lookup"><span data-stu-id="c07f1-111">You can customize the PrivateInitiator.odx sample for your purposes.</span></span> <span data-ttu-id="c07f1-112">你必须小心，确保不会对发起方公用流程的正常运行产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="c07f1-112">You must be careful that you do not adversely affect the functioning of the initiator public process.</span></span>  
  
 <span data-ttu-id="c07f1-113">有关详细信息，包括消息流的说明，请参阅[发起方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)。</span><span class="sxs-lookup"><span data-stu-id="c07f1-113">For more information, including a description of the message flow, see [Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c07f1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c07f1-114">See Also</span></span>  
 <span data-ttu-id="c07f1-115">[业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="c07f1-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="c07f1-116">私有进程</span><span class="sxs-lookup"><span data-stu-id="c07f1-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)