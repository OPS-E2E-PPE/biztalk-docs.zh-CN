---
title: PrivateInitiator 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27ead20d17452dcbd4982bba7f3082ee430ae6dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282571"
---
# <a name="privateinitiator-sample"></a><span data-ttu-id="04598-102">PrivateInitiator 示例</span><span class="sxs-lookup"><span data-stu-id="04598-102">PrivateInitiator Sample</span></span>
<span data-ttu-id="04598-103">PrivateInitiator.odx 示例包含安装 Microsoft® BizTalk Server 的发起方专用流程的代码。</span><span class="sxs-lookup"><span data-stu-id="04598-103">The PrivateInitiator.odx sample contains the code for the initiator private process installed by Microsoft® BizTalk Server.</span></span> <span data-ttu-id="04598-104">这是通用的专用流程发送和接收 RNIF 服务内容消息从默认的 SQL 适配器基于发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="04598-104">This is a generic private process that sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="04598-105">默认情况下[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK\PrivateInitiator 中。</span><span class="sxs-lookup"><span data-stu-id="04598-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateInitiator.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="04598-106">示例内容</span><span class="sxs-lookup"><span data-stu-id="04598-106">Sample Contents</span></span>  
 <span data-ttu-id="04598-107">发起方专用流程是发起方内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="04598-107">The initiator private process is the business process that is internal to the initiator.</span></span> <span data-ttu-id="04598-108">专用流程提供发起方公用流程和后端业务线程序之间的后端集成。</span><span class="sxs-lookup"><span data-stu-id="04598-108">The private process provides back-end integration between the initiator public process and the back-end line-of-business program.</span></span> <span data-ttu-id="04598-109">发起方专用流程与公用流程，以便启动的消息进行通信。</span><span class="sxs-lookup"><span data-stu-id="04598-109">The initiator private process communicates with the public process to initiate messages.</span></span>  
  
 <span data-ttu-id="04598-110">发起方专用流程是唯一的每个实现。</span><span class="sxs-lookup"><span data-stu-id="04598-110">The initiator private process is unique for each implementation.</span></span> <span data-ttu-id="04598-111">你可以为您的要求自定义 PrivateInitiator.odx 示例。</span><span class="sxs-lookup"><span data-stu-id="04598-111">You can customize the PrivateInitiator.odx sample for your purposes.</span></span> <span data-ttu-id="04598-112">您必须小心，不产生不利影响的发起方公用流程正常运行。</span><span class="sxs-lookup"><span data-stu-id="04598-112">You must be careful that you do not adversely affect the functioning of the initiator public process.</span></span>  
  
 <span data-ttu-id="04598-113">有关详细信息，包括消息流的说明，请参阅[发起方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)。</span><span class="sxs-lookup"><span data-stu-id="04598-113">For more information, including a description of the message flow, see [Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04598-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="04598-114">See Also</span></span>  
 <span data-ttu-id="04598-115">[业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="04598-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="04598-116">专用流程</span><span class="sxs-lookup"><span data-stu-id="04598-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)