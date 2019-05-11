---
title: PrivateResponder 示例 |Microsoft Docs
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
ms.openlocfilehash: a02d4b2d902f2dad24a20c150e474e671f582a66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282519"
---
# <a name="privateresponder-sample"></a><span data-ttu-id="4f95f-102">PrivateResponder 示例</span><span class="sxs-lookup"><span data-stu-id="4f95f-102">PrivateResponder Sample</span></span>
<span data-ttu-id="4f95f-103">PrivateResponder.odx 示例包含用于安装 Microsoft® 的响应方专用流程的代码[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4f95f-103">The PrivateResponder.odx sample contains the code for the responder private process installed by Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="4f95f-104">此通用专用流程将发送和接收 RNIF 服务内容消息从默认的 SQL 适配器基于发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="4f95f-104">This generic private process sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="4f95f-105">默认情况下[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*>: \Program Files\\Microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\PrivateResponder。</span><span class="sxs-lookup"><span data-stu-id="4f95f-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\Microsoft  BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="4f95f-106">示例内容</span><span class="sxs-lookup"><span data-stu-id="4f95f-106">Sample Contents</span></span>  
 <span data-ttu-id="4f95f-107">响应方专用流程是响应方内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="4f95f-107">The responder private process is the business process that is internal to the responder.</span></span> <span data-ttu-id="4f95f-108">专用流程提供响应方公用流程和后端业务线程序之间的后端集成。</span><span class="sxs-lookup"><span data-stu-id="4f95f-108">The private process provides back-end integration between the responder public process and the back-end line-of-business program.</span></span> <span data-ttu-id="4f95f-109">响应方专用流程与公用流程，以便响应消息进行通信。</span><span class="sxs-lookup"><span data-stu-id="4f95f-109">The responder private process communicates with the public process to respond to messages.</span></span>  
  
 <span data-ttu-id="4f95f-110">响应方专用流程是唯一的每个实现。</span><span class="sxs-lookup"><span data-stu-id="4f95f-110">The responder private process is unique for each implementation.</span></span> <span data-ttu-id="4f95f-111">你可以为您的要求自定义 PrivateResponder.odx 示例。</span><span class="sxs-lookup"><span data-stu-id="4f95f-111">You can customize the PrivateResponder.odx sample for your purposes.</span></span> <span data-ttu-id="4f95f-112">您必须小心，不产生不利影响响应方公用流程的正常运行。</span><span class="sxs-lookup"><span data-stu-id="4f95f-112">You must be careful that you do not adversely affect the functioning of the responder public process.</span></span>  
  
 <span data-ttu-id="4f95f-113">有关详细信息，包括消息流的说明，请参阅[响应方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)。</span><span class="sxs-lookup"><span data-stu-id="4f95f-113">For more information, including a description of the message flow, see [Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f95f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f95f-114">See Also</span></span>  
 <span data-ttu-id="4f95f-115">[业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="4f95f-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="4f95f-116">专用流程</span><span class="sxs-lookup"><span data-stu-id="4f95f-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)