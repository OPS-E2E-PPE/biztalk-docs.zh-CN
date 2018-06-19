---
title: 找不到批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73c3e65a806f02faeb81baa6a5263019079b0c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279477"
---
# <a name="the-batch-was-not-found"></a><span data-ttu-id="e66aa-102">找不到批处理</span><span class="sxs-lookup"><span data-stu-id="e66aa-102">The batch was not found</span></span>
## <a name="details"></a><span data-ttu-id="e66aa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e66aa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e66aa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e66aa-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e66aa-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e66aa-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e66aa-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e66aa-106">Event ID</span></span>|-|  
|<span data-ttu-id="e66aa-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e66aa-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e66aa-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e66aa-108"> EDI</span></span>|  
|<span data-ttu-id="e66aa-109">组件</span><span class="sxs-lookup"><span data-stu-id="e66aa-109">Component</span></span>|<span data-ttu-id="e66aa-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e66aa-110">EDI Engine</span></span>|  
|<span data-ttu-id="e66aa-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e66aa-111">Symbolic Name</span></span>|<span data-ttu-id="e66aa-112">Err_BatchNotFound</span><span class="sxs-lookup"><span data-stu-id="e66aa-112">Err_BatchNotFound</span></span>|  
|<span data-ttu-id="e66aa-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e66aa-113">Message Text</span></span>|<span data-ttu-id="e66aa-114">未找到批处理。</span><span class="sxs-lookup"><span data-stu-id="e66aa-114">The batch was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e66aa-115">解释</span><span class="sxs-lookup"><span data-stu-id="e66aa-115">Explanation</span></span>  
 <span data-ttu-id="e66aa-116">此错误/警告/信息事件表明 BizTalk Server 在启动/停止批处理期间或者在批处理业务流程尝试对消息进行批处理时未找到批处理。</span><span class="sxs-lookup"><span data-stu-id="e66aa-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a batch during the start/stop of a batch or while the Batching Orchestration was trying to batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e66aa-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e66aa-117">User Action</span></span>  
 <span data-ttu-id="e66aa-118">若要解决此错误，请确保所包含协议的“协议”属性中存在相应的批处理。</span><span class="sxs-lookup"><span data-stu-id="e66aa-118">To resolve this error, ensure that the respective batch is present in the Agreement properties of the containing Agreement.</span></span>