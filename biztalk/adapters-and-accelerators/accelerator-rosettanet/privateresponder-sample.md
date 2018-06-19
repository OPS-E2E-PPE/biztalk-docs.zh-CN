---
title: PrivateResponder 示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3de3428aa9971ba62b682494cd94c6bb74bcab53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206941"
---
# <a name="privateresponder-sample"></a><span data-ttu-id="a2655-102">PrivateResponder 示例</span><span class="sxs-lookup"><span data-stu-id="a2655-102">PrivateResponder Sample</span></span>
<span data-ttu-id="a2655-103">PrivateInitiator.odx 示例包含 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 安装的响应方专用流程的代码。</span><span class="sxs-lookup"><span data-stu-id="a2655-103">The PrivateResponder.odx sample contains the code for the responder private process installed by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="a2655-104">此通用专用流程从基于默认 SQL 适配器的发送和接收端口发送和接收 RNIF 服务内容消息。</span><span class="sxs-lookup"><span data-stu-id="a2655-104">This generic private process sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="a2655-105">默认情况下，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\ 快捷键PrivateResponder。</span><span class="sxs-lookup"><span data-stu-id="a2655-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="a2655-106">示例内容</span><span class="sxs-lookup"><span data-stu-id="a2655-106">Sample Contents</span></span>  
 <span data-ttu-id="a2655-107">响应方专用流程是响应方内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a2655-107">The responder private process is the business process that is internal to the responder.</span></span> <span data-ttu-id="a2655-108">该专用流程提供响应方公用流程和后端业务线程序之间的后端集成。</span><span class="sxs-lookup"><span data-stu-id="a2655-108">The private process provides back-end integration between the responder public process and the back-end line-of-business program.</span></span> <span data-ttu-id="a2655-109">响应方专用流程与公用流程进行通信以响应消息。</span><span class="sxs-lookup"><span data-stu-id="a2655-109">The responder private process communicates with the public process to respond to messages.</span></span>  
  
 <span data-ttu-id="a2655-110">每个实现的响应方专用流程都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a2655-110">The responder private process is unique for each implementation.</span></span> <span data-ttu-id="a2655-111">可以根据所需自定义 PrivateResponder.odx 示例。</span><span class="sxs-lookup"><span data-stu-id="a2655-111">You can customize the PrivateResponder.odx sample for your purposes.</span></span> <span data-ttu-id="a2655-112">你必须小心，确保不会对响应方公用流程的正常运行产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="a2655-112">You must be careful that you do not adversely affect the functioning of the responder public process.</span></span>  
  
 <span data-ttu-id="a2655-113">有关详细信息，包括消息流的说明，请参阅[响应方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)。</span><span class="sxs-lookup"><span data-stu-id="a2655-113">For more information, including a description of the message flow, see [Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2655-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2655-114">See Also</span></span>  
 <span data-ttu-id="a2655-115">[业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="a2655-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="a2655-116">私有进程</span><span class="sxs-lookup"><span data-stu-id="a2655-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)