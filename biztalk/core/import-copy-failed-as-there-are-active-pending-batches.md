---
title: 导入复制失败，因为有活动挂起的批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a74bfdccbd12db00cd0f325aedee2e42cc76729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970534"
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a><span data-ttu-id="c5732-102">导入复制失败，因为有活动挂起的批处理</span><span class="sxs-lookup"><span data-stu-id="c5732-102">Import-Copy failed as there are active-pending batches</span></span>
## <a name="details"></a><span data-ttu-id="c5732-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c5732-103">Details</span></span>  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c5732-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c5732-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="c5732-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c5732-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="c5732-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c5732-106">Event ID</span></span>     |                                                       -                                                        |
|  <span data-ttu-id="c5732-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c5732-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c5732-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c5732-108"> EDI</span></span>             |
|    <span data-ttu-id="c5732-109">组件</span><span class="sxs-lookup"><span data-stu-id="c5732-109">Component</span></span>    |                                                   <span data-ttu-id="c5732-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c5732-110">EDI Engine</span></span>                                                   |
|  <span data-ttu-id="c5732-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c5732-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="c5732-112">Err_ActiveBatchFound</span><span class="sxs-lookup"><span data-stu-id="c5732-112">Err_ActiveBatchFound</span></span>                                              |
|  <span data-ttu-id="c5732-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c5732-113">Message Text</span></span>   | <span data-ttu-id="c5732-114">导入/复制失败，因为有活动/挂起的批处理。</span><span class="sxs-lookup"><span data-stu-id="c5732-114">Import/Copy failed as there are active/pending batches.</span></span> <span data-ttu-id="c5732-115">停止活动/挂起的批处理，然后尝试导入/复制。</span><span class="sxs-lookup"><span data-stu-id="c5732-115">Stop active/pending batches and try importing/copying.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c5732-116">解释</span><span class="sxs-lookup"><span data-stu-id="c5732-116">Explanation</span></span>  
 <span data-ttu-id="c5732-117">此错误/警告/信息事件表明 BizTalk Server 无法导入绑定文件或无法复制设置，因为受影响的协议具有一个或多个活动或挂起的批处理。</span><span class="sxs-lookup"><span data-stu-id="c5732-117">This Error/Warning/Information event indicates BizTalk Server was unable to Import a binding file or copy the settings as the affected Agreement(s) have one or more active or pending batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5732-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="c5732-118">User Action</span></span>  
 <span data-ttu-id="c5732-119">若要解决此错误，请确保受影响的协议中的所有批处理在“协议”属性中显示为已停止。</span><span class="sxs-lookup"><span data-stu-id="c5732-119">To resolve this error, ensure that all the batches in affected agreements are showing as stopped in the Agreement properties.</span></span>