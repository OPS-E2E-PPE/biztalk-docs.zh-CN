---
title: 从失败的数据库读取批说明 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3eed2b26b01840104ba1219dd6acde7e2b0ae2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398289"
---
# <a name="reading-batch-descriptions-from-database-failed"></a><span data-ttu-id="64430-102">从数据库读取批说明失败</span><span class="sxs-lookup"><span data-stu-id="64430-102">Reading Batch Descriptions from database failed</span></span>
## <a name="details"></a><span data-ttu-id="64430-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="64430-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="64430-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="64430-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="64430-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="64430-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="64430-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="64430-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="64430-107">事件源</span><span class="sxs-lookup"><span data-stu-id="64430-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="64430-108">EDI</span><span class="sxs-lookup"><span data-stu-id="64430-108">EDI</span></span> |
|    <span data-ttu-id="64430-109">组件</span><span class="sxs-lookup"><span data-stu-id="64430-109">Component</span></span>    |                                       <span data-ttu-id="64430-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="64430-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="64430-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="64430-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="64430-112">LoadBatchFiltersFailed</span><span class="sxs-lookup"><span data-stu-id="64430-112">LoadBatchFiltersFailed</span></span>                                 |
|  <span data-ttu-id="64430-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="64430-113">Message Text</span></span>   |     <span data-ttu-id="64430-114">从数据库中读取 BatchDescriptions 失败。</span><span class="sxs-lookup"><span data-stu-id="64430-114">Reading BatchDescriptions from database failed.</span></span> <span data-ttu-id="64430-115">错误： {0}。</span><span class="sxs-lookup"><span data-stu-id="64430-115">Error: {0}.</span></span> <span data-ttu-id="64430-116">堆栈跟踪： {1}。</span><span class="sxs-lookup"><span data-stu-id="64430-116">Stack Trace: {1}.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="64430-117">解释</span><span class="sxs-lookup"><span data-stu-id="64430-117">Explanation</span></span>  
 <span data-ttu-id="64430-118">此错误/警告/信息事件表明 BizTalk Server 无法加载指定要比较的传入消息的上下文属性的已配置批的筛选器。</span><span class="sxs-lookup"><span data-stu-id="64430-118">This Error/Warning/Information event indicates BizTalk Server was unable to load the filters specified for the configured batches to compare context properties of incoming messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64430-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="64430-119">User Action</span></span>  
 <span data-ttu-id="64430-120">若要解决此错误，请确保管理数据库已启动，并且可以连接。</span><span class="sxs-lookup"><span data-stu-id="64430-120">To resolve this error, ensure that the Management database is up and can be connected.</span></span>