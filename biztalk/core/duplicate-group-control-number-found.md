---
title: 重复组控制编号找到 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1badc033-42fd-4992-ad36-b53047ba7817
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9165414d1a9a743c77c28b087730745d3dcc4c0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239541"
---
# <a name="duplicate-group-control-number-found"></a><span data-ttu-id="ea216-102">找到重复的组控制编号</span><span class="sxs-lookup"><span data-stu-id="ea216-102">Duplicate group control number found</span></span>
## <a name="details"></a><span data-ttu-id="ea216-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ea216-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea216-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ea216-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ea216-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ea216-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ea216-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ea216-106">Event ID</span></span>|-|  
|<span data-ttu-id="ea216-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ea216-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ea216-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ea216-108"> EDI</span></span>|  
|<span data-ttu-id="ea216-109">组件</span><span class="sxs-lookup"><span data-stu-id="ea216-109">Component</span></span>|<span data-ttu-id="ea216-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ea216-110">EDI Engine</span></span>|  
|<span data-ttu-id="ea216-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ea216-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="ea216-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="ea216-112">Message Text</span></span>|<span data-ttu-id="ea216-113">找到重复的组控制编号</span><span class="sxs-lookup"><span data-stu-id="ea216-113">Duplicate group control number found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ea216-114">解释</span><span class="sxs-lookup"><span data-stu-id="ea216-114">Explanation</span></span>  
 <span data-ttu-id="ea216-115">此错误/警告/信息事件指示 EDI 接收管道无法不传入交换由于具有相同的交换中，组的过程或事务集控制编号为以前收到的交换。</span><span class="sxs-lookup"><span data-stu-id="ea216-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming interchange because it had the same interchange, group, or transaction set control number as a previously received interchange.</span></span> <span data-ttu-id="ea216-116">只要启用了适当的重复控制编号检查，这将导致失败。</span><span class="sxs-lookup"><span data-stu-id="ea216-116">This will result in a failure as long as the appropriate duplicate control number checks are enabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ea216-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ea216-117">User Action</span></span>  
 <span data-ttu-id="ea216-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ea216-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="ea216-119">确保发送给 BizTalk Server 的交换具有与之前交换不同的组控制编号（如果启用相应的重复控制编号检查）。</span><span class="sxs-lookup"><span data-stu-id="ea216-119">Ensure that the interchange sent to BizTalk Server does not have the same group control number as a previous interchange, if the corresponding duplicate control number check is enabled.</span></span>  
  
-   <span data-ttu-id="ea216-120">禁用重复组控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="ea216-120">Disable the duplicate group control number check.</span></span> <span data-ttu-id="ea216-121">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，右键单击相应的一方，然后为作为交换发送方的参与方打开“EDIFACT 交换处理属性”或“X12 交换处理属性”对话框。</span><span class="sxs-lookup"><span data-stu-id="ea216-121">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the appropriate party, and open either the EDIFACT Interchange Processing Properties or the X12 Interchange Processing Properties dialog box for the party as an interchange sender.</span></span> <span data-ttu-id="ea216-122">若要禁用 EDIFACT 交换检查，请清除“检查交换中重复的 UNG5 (组控制编号)”属性。</span><span class="sxs-lookup"><span data-stu-id="ea216-122">To disable a check for an EDIFACT interchange, clear the Check for duplicate UNG5 (Group control number) in interchange property.</span></span> <span data-ttu-id="ea216-123">若要禁用 X12 交换检查，请清除“检查交换中重复的 GS6 (组控制编号)”属性。</span><span class="sxs-lookup"><span data-stu-id="ea216-123">To disable a check for an X12 interchange, clear the Check for duplicate GS6 (Group control number) in interchange property.</span></span>