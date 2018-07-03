---
title: 控制编号重复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 331ad173-29b3-427c-8104-60d80c580a5a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcfd1a10b836ec593b6aa94a87d8145d6e2ebaaf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967886"
---
# <a name="duplicate-control-number"></a><span data-ttu-id="45f8a-102">控制编号重复</span><span class="sxs-lookup"><span data-stu-id="45f8a-102">Duplicate Control Number</span></span>
## <a name="details"></a><span data-ttu-id="45f8a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="45f8a-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="45f8a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="45f8a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="45f8a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="45f8a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="45f8a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45f8a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="45f8a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="45f8a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="45f8a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="45f8a-108"> EDI</span></span> |
|    <span data-ttu-id="45f8a-109">组件</span><span class="sxs-lookup"><span data-stu-id="45f8a-109">Component</span></span>    |                                       <span data-ttu-id="45f8a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="45f8a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="45f8a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="45f8a-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="45f8a-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="45f8a-112">Message Text</span></span>   |                                <span data-ttu-id="45f8a-113">控制编号重复</span><span class="sxs-lookup"><span data-stu-id="45f8a-113">Duplicate Control Number</span></span>                                |

## <a name="explanation"></a><span data-ttu-id="45f8a-114">解释</span><span class="sxs-lookup"><span data-stu-id="45f8a-114">Explanation</span></span>  
 <span data-ttu-id="45f8a-115">此错误/警告/信息事件表明 EDI 接收管道可以不处理传入的交换由于具有相同的交换、 组或事务集控制编号与以前接收的交换。</span><span class="sxs-lookup"><span data-stu-id="45f8a-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming interchange because it had the same interchange, group, or transaction set control number as a previously received interchange.</span></span> <span data-ttu-id="45f8a-116">这将导致失败，只要启用了相应的重复控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="45f8a-116">This will result in a failure as long as the appropriate duplicate control number checks are enabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="45f8a-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="45f8a-117">User Action</span></span>  
 <span data-ttu-id="45f8a-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="45f8a-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="45f8a-119">请确保发送给 BizTalk Server 的交换具有与之前交换不同的交换、组或事务集控制编号（如果启用相应的重复控制编号检查）。</span><span class="sxs-lookup"><span data-stu-id="45f8a-119">Ensure that the interchange sent to BizTalk Server does not have the same interchange, group, or transaction set control number as a previous interchange, if the corresponding duplicate control number check is enabled.</span></span>  

- <span data-ttu-id="45f8a-120">禁用重复控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="45f8a-120">Disable the duplicate control number check.</span></span> <span data-ttu-id="45f8a-121">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，右键单击相应的一方，然后为作为交换发送方的参与方打开“EDIFACT 交换处理属性”或“X12 交换处理属性”对话框。</span><span class="sxs-lookup"><span data-stu-id="45f8a-121">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the appropriate party, and open either the EDIFACT Interchange Processing Properties or the X12 Interchange Processing Properties dialog box for the party as an interchange sender.</span></span> <span data-ttu-id="45f8a-122">若要禁用 EDIFACT 交换的检查，请清除“检查重复的 UNB5 (交换控制编号)”、“检查交换中重复的 UNG5 (组控制编号)”或“检查组中重复的 UNH1 (事务集参考编号)”属性。</span><span class="sxs-lookup"><span data-stu-id="45f8a-122">To disable a check for an EDIFACT interchange, clear the Check for duplicate UNB5 (Interchange control number), Check for duplicate UNG5 (Group control number) in interchange, or Check for duplicate UNH1 (Transaction set reference number) in group property.</span></span> <span data-ttu-id="45f8a-123">若要禁用 X12 交换的检查，请清除“检查重复的 ISA13 (交换控制编号)”、“检查交换中重复的 GS6 (组控制编号)”或“检查组中重复的 ST2 (事务集控制编号)”属性。</span><span class="sxs-lookup"><span data-stu-id="45f8a-123">To disable a check for an X12 interchange, clear the Check for duplicate ISA13 (Interchange control number), Check for duplicate GS6 (Group control number) in interchange, or Check for duplicate ST2 (Transaction set control number) in group property.</span></span>
