---
title: "无效的控件结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9bb104-7ea1-429a-8540-49f4d598fd46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa21ceae70798242a153978adeaf5b75478b3b49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-control-structure"></a><span data-ttu-id="1221b-102">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="1221b-102">Invalid Control Structure</span></span>
## <a name="details"></a><span data-ttu-id="1221b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1221b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1221b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1221b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1221b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1221b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1221b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1221b-106">Event ID</span></span>|-|  
|<span data-ttu-id="1221b-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1221b-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1221b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1221b-108"> EDI</span></span>|  
|<span data-ttu-id="1221b-109">组件</span><span class="sxs-lookup"><span data-stu-id="1221b-109">Component</span></span>|<span data-ttu-id="1221b-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1221b-110">EDI Engine</span></span>|  
|<span data-ttu-id="1221b-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1221b-111">Symbolic Name</span></span>|<span data-ttu-id="1221b-112">X12Ta1InvalidControlStructureDescription</span><span class="sxs-lookup"><span data-stu-id="1221b-112">X12Ta1InvalidControlStructureDescription</span></span>|  
|<span data-ttu-id="1221b-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1221b-113">Message Text</span></span>|<span data-ttu-id="1221b-114">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="1221b-114">Invalid Control Structure</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1221b-115">解释</span><span class="sxs-lookup"><span data-stu-id="1221b-115">Explanation</span></span>  
 <span data-ttu-id="1221b-116">此错误/警告/信息事件表明 BizTalk Server 无法针对 TA1Schema 验证 TA1 确认的结构。</span><span class="sxs-lookup"><span data-stu-id="1221b-116">This Error/Warning/Information event indicates that BizTalk Server could not validate the structure of the TA1 acknowledgment against the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1221b-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="1221b-117">User Action</span></span>  
 <span data-ttu-id="1221b-118">若要解决此错误，请确定 TA1 确认不符合 TA1Schema 的原因并解决此问题。</span><span class="sxs-lookup"><span data-stu-id="1221b-118">To resolve this error, determine why the TA1 acknowledgment does not conform to the TA1Schema, and resolve the issue.</span></span>