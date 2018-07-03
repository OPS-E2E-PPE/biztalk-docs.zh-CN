---
title: 与 BatchId 关联的协议未启用或已过期。 批处理不能继续 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d92cb07-7646-42b3-90a8-18acbcd145cd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace947d1c05774882b1e8f78f7b093f0795ba919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018284"
---
# <a name="the-agreement-associated-with-batchid-is-not-enabled-or-has-expired-batching-cannot-continue"></a><span data-ttu-id="29ac5-103">与 BatchId 关联的协议未启用或已过期。</span><span class="sxs-lookup"><span data-stu-id="29ac5-103">The agreement associated with BatchId is not enabled or has expired.</span></span> <span data-ttu-id="29ac5-104">批处理无法继续</span><span class="sxs-lookup"><span data-stu-id="29ac5-104">Batching cannot continue</span></span>
## <a name="details"></a><span data-ttu-id="29ac5-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="29ac5-105">Details</span></span>  
  
|                 |                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="29ac5-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="29ac5-106">Product Name</span></span>   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="29ac5-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="29ac5-107">Product Version</span></span> |                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="29ac5-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="29ac5-108">Event ID</span></span>     |                                                 -                                                  |
|  <span data-ttu-id="29ac5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="29ac5-109">Event Source</span></span>   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="29ac5-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="29ac5-110"> EDI</span></span>       |
|    <span data-ttu-id="29ac5-111">组件</span><span class="sxs-lookup"><span data-stu-id="29ac5-111">Component</span></span>    |                                             <span data-ttu-id="29ac5-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="29ac5-112">EDI Engine</span></span>                                             |
|  <span data-ttu-id="29ac5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="29ac5-113">Symbolic Name</span></span>  |                                    <span data-ttu-id="29ac5-114">ErrorBatchAgreementDisabled</span><span class="sxs-lookup"><span data-stu-id="29ac5-114">ErrorBatchAgreementDisabled</span></span>                                     |
|  <span data-ttu-id="29ac5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="29ac5-115">Message Text</span></span>   | <span data-ttu-id="29ac5-116">与 BatchId 关联的协议{0}未启用或已过期。</span><span class="sxs-lookup"><span data-stu-id="29ac5-116">The agreement associated with BatchId {0} is not enabled or has expired.</span></span> <span data-ttu-id="29ac5-117">批处理不能继续。</span><span class="sxs-lookup"><span data-stu-id="29ac5-117">Batching cannot continue.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="29ac5-118">解释</span><span class="sxs-lookup"><span data-stu-id="29ac5-118">Explanation</span></span>  
 <span data-ttu-id="29ac5-119">此错误/警告/信息事件表明 BizTalk Server 无法启动批处理或无法处理批处理消息，因为协议已过期。</span><span class="sxs-lookup"><span data-stu-id="29ac5-119">This Error/Warning/Information event indicates BizTalk Server was not able to start a batch or process a batch message because of Agreement getting expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29ac5-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="29ac5-120">User Action</span></span>  
 <span data-ttu-id="29ac5-121">若要解决此错误，请确保所包含协议的“协议”属性中存在具有给定 Id 的批处理并且确保其开始和结束日期落在协议的开始和结束日期之内。</span><span class="sxs-lookup"><span data-stu-id="29ac5-121">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and its start and end date fall within the start and end dates of the Agreement.</span></span> <span data-ttu-id="29ac5-122">还要确保启用该协议。</span><span class="sxs-lookup"><span data-stu-id="29ac5-122">Also make sure that the agreement is enabled.</span></span>