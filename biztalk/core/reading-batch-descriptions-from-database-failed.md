---
title: "从失败的数据库的读取批说明 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9049c9f3964b231d7c1370784bccd78fd0836
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reading-batch-descriptions-from-database-failed"></a><span data-ttu-id="675c6-102">从数据库读取批说明失败</span><span class="sxs-lookup"><span data-stu-id="675c6-102">Reading Batch Descriptions from database failed</span></span>
## <a name="details"></a><span data-ttu-id="675c6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="675c6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="675c6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="675c6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="675c6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="675c6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="675c6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="675c6-106">Event ID</span></span>|-|  
|<span data-ttu-id="675c6-107">事件源</span><span class="sxs-lookup"><span data-stu-id="675c6-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="675c6-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="675c6-108"> EDI</span></span>|  
|<span data-ttu-id="675c6-109">组件</span><span class="sxs-lookup"><span data-stu-id="675c6-109">Component</span></span>|<span data-ttu-id="675c6-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="675c6-110">EDI Engine</span></span>|  
|<span data-ttu-id="675c6-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="675c6-111">Symbolic Name</span></span>|<span data-ttu-id="675c6-112">LoadBatchFiltersFailed</span><span class="sxs-lookup"><span data-stu-id="675c6-112">LoadBatchFiltersFailed</span></span>|  
|<span data-ttu-id="675c6-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="675c6-113">Message Text</span></span>|<span data-ttu-id="675c6-114">从数据库中读取 BatchDescriptions 失败。</span><span class="sxs-lookup"><span data-stu-id="675c6-114">Reading BatchDescriptions from database failed.</span></span> <span data-ttu-id="675c6-115">错误: {0}。</span><span class="sxs-lookup"><span data-stu-id="675c6-115">Error: {0}.</span></span> <span data-ttu-id="675c6-116">堆栈跟踪： {1}。</span><span class="sxs-lookup"><span data-stu-id="675c6-116">Stack Trace: {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="675c6-117">解释</span><span class="sxs-lookup"><span data-stu-id="675c6-117">Explanation</span></span>  
 <span data-ttu-id="675c6-118">此错误/警告/信息事件表明 BizTalk Server 无法加载为配置为比较传入消息的上下文属性的批处理指定的筛选器。</span><span class="sxs-lookup"><span data-stu-id="675c6-118">This Error/Warning/Information event indicates BizTalk Server was unable to load the filters specified for the configured batches to compare context properties of incoming messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="675c6-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="675c6-119">User Action</span></span>  
 <span data-ttu-id="675c6-120">若要解决此错误，请确保管理数据库正在运行，并且可以连接。</span><span class="sxs-lookup"><span data-stu-id="675c6-120">To resolve this error, ensure that the Management database is up and can be connected.</span></span>