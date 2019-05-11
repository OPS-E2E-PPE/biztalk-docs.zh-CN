---
title: 在功能组后发现 TA1 段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3d090a-0916-4a0e-82dc-2c9af9f97683
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4526c07171a96904299c60f12ee5c34c01816a42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291669"
---
# <a name="ta1-segment-found-after-a-functional-group"></a><span data-ttu-id="802a9-102">在功能组后发现 TA1 段</span><span class="sxs-lookup"><span data-stu-id="802a9-102">TA1 segment found after a functional group</span></span>
## <a name="details"></a><span data-ttu-id="802a9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="802a9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="802a9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="802a9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="802a9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="802a9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="802a9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="802a9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="802a9-107">事件源</span><span class="sxs-lookup"><span data-stu-id="802a9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="802a9-108">EDI</span><span class="sxs-lookup"><span data-stu-id="802a9-108">EDI</span></span> |
|    <span data-ttu-id="802a9-109">组件</span><span class="sxs-lookup"><span data-stu-id="802a9-109">Component</span></span>    |                                       <span data-ttu-id="802a9-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="802a9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="802a9-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="802a9-111">Symbolic Name</span></span>  |                              <span data-ttu-id="802a9-112">TA1FoundAfterFunctionalGroup</span><span class="sxs-lookup"><span data-stu-id="802a9-112">TA1FoundAfterFunctionalGroup</span></span>                              |
|  <span data-ttu-id="802a9-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="802a9-113">Message Text</span></span>   |     <span data-ttu-id="802a9-114">在功能组后发现 TA1 段。</span><span class="sxs-lookup"><span data-stu-id="802a9-114">TA1 segment found after a functional group.</span></span> <span data-ttu-id="802a9-115">因此，消息被拒绝</span><span class="sxs-lookup"><span data-stu-id="802a9-115">So, the message is being rejected</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="802a9-116">解释</span><span class="sxs-lookup"><span data-stu-id="802a9-116">Explanation</span></span>  
 <span data-ttu-id="802a9-117">此错误/警告/信息事件表明接收管道无法处理传入的确认，因为确认包含一个功能组并且在该功能组之后是一个 TA1 段。</span><span class="sxs-lookup"><span data-stu-id="802a9-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming acknowledgment because the acknowledgment contained a functional group and then a TA1 segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="802a9-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="802a9-118">User Action</span></span>  
 <span data-ttu-id="802a9-119">若要解决此错误，请让 TA1 确认的发送方确保交换在 TA1 段之前不包含功能组，然后重新发送确认。</span><span class="sxs-lookup"><span data-stu-id="802a9-119">To resolve this error, have the sender of the TA1 acknowledgment ensure that the interchange does not contain a functional group before the TA1 segment, and then resend the acknowledgment.</span></span>