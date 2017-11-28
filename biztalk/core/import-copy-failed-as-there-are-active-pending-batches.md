---
title: "导入复制失败，因为有多个活动挂起批 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3055f3e95ef3d0fb8bf5a36dae5957e318f6e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a><span data-ttu-id="c06ca-102">导入复制失败，因为有多个活动挂起批</span><span class="sxs-lookup"><span data-stu-id="c06ca-102">Import-Copy failed as there are active-pending batches</span></span>
## <a name="details"></a><span data-ttu-id="c06ca-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c06ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c06ca-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c06ca-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c06ca-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c06ca-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c06ca-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c06ca-106">Event ID</span></span>|-|  
|<span data-ttu-id="c06ca-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c06ca-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c06ca-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c06ca-108"> EDI</span></span>|  
|<span data-ttu-id="c06ca-109">组件</span><span class="sxs-lookup"><span data-stu-id="c06ca-109">Component</span></span>|<span data-ttu-id="c06ca-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c06ca-110">EDI Engine</span></span>|  
|<span data-ttu-id="c06ca-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c06ca-111">Symbolic Name</span></span>|<span data-ttu-id="c06ca-112">Err_ActiveBatchFound</span><span class="sxs-lookup"><span data-stu-id="c06ca-112">Err_ActiveBatchFound</span></span>|  
|<span data-ttu-id="c06ca-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c06ca-113">Message Text</span></span>|<span data-ttu-id="c06ca-114">导入/复制失败，因为有活动/挂起的批处理。</span><span class="sxs-lookup"><span data-stu-id="c06ca-114">Import/Copy failed as there are active/pending batches.</span></span> <span data-ttu-id="c06ca-115">停止活动/挂起的批处理，然后尝试导入/复制。</span><span class="sxs-lookup"><span data-stu-id="c06ca-115">Stop active/pending batches and try importing/copying.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c06ca-116">解释</span><span class="sxs-lookup"><span data-stu-id="c06ca-116">Explanation</span></span>  
 <span data-ttu-id="c06ca-117">此错误/警告/信息事件表明 BizTalk Server 无法导入绑定文件或无法复制设置，因为受影响的协议具有一个或多个活动或挂起的批处理。</span><span class="sxs-lookup"><span data-stu-id="c06ca-117">This Error/Warning/Information event indicates BizTalk Server was unable to Import a binding file or copy the settings as the affected Agreement(s) have one or more active or pending batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c06ca-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="c06ca-118">User Action</span></span>  
 <span data-ttu-id="c06ca-119">若要解决此错误，请确保受影响的协议中的所有批处理在“协议”属性中显示为已停止。</span><span class="sxs-lookup"><span data-stu-id="c06ca-119">To resolve this error, ensure that all the batches in affected agreements are showing as stopped in the Agreement properties.</span></span>