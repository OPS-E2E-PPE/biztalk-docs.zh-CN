---
title: 未找到批处理 |Microsoft Docs
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
ms.openlocfilehash: 564cacb8d1389f03404939a0c9c7f557b6fa7393
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298824"
---
# <a name="the-batch-was-not-found"></a><span data-ttu-id="d2a76-102">未找到批处理</span><span class="sxs-lookup"><span data-stu-id="d2a76-102">The batch was not found</span></span>
## <a name="details"></a><span data-ttu-id="d2a76-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2a76-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d2a76-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d2a76-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d2a76-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d2a76-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d2a76-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d2a76-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d2a76-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d2a76-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d2a76-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d2a76-108">EDI</span></span> |
|    <span data-ttu-id="d2a76-109">组件</span><span class="sxs-lookup"><span data-stu-id="d2a76-109">Component</span></span>    |                                       <span data-ttu-id="d2a76-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d2a76-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d2a76-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d2a76-111">Symbolic Name</span></span>  |                                   <span data-ttu-id="d2a76-112">Err_BatchNotFound</span><span class="sxs-lookup"><span data-stu-id="d2a76-112">Err_BatchNotFound</span></span>                                    |
|  <span data-ttu-id="d2a76-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d2a76-113">Message Text</span></span>   |                                <span data-ttu-id="d2a76-114">未找到批处理。</span><span class="sxs-lookup"><span data-stu-id="d2a76-114">The batch was not found.</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="d2a76-115">解释</span><span class="sxs-lookup"><span data-stu-id="d2a76-115">Explanation</span></span>  
 <span data-ttu-id="d2a76-116">此错误/警告/信息事件表明 BizTalk Server 在启动/停止批处理期间或者在批处理业务流程尝试对消息进行批处理时未找到批处理。</span><span class="sxs-lookup"><span data-stu-id="d2a76-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a batch during the start/stop of a batch or while the Batching Orchestration was trying to batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2a76-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d2a76-117">User Action</span></span>  
 <span data-ttu-id="d2a76-118">若要解决此错误，请确保所包含协议的“协议”属性中存在相应的批处理。</span><span class="sxs-lookup"><span data-stu-id="d2a76-118">To resolve this error, ensure that the respective batch is present in the Agreement properties of the containing Agreement.</span></span>