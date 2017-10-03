---
title: "找不到业务标识对应于批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9baf11-e9c6-482d-a47d-aa99852939bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f1027186e5b001d21e08bbabcfc100400a02d5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a><span data-ttu-id="23c51-102">找不到对应于批处理的业务标识</span><span class="sxs-lookup"><span data-stu-id="23c51-102">Could not find Business Identities corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="23c51-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="23c51-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23c51-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="23c51-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="23c51-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="23c51-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="23c51-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="23c51-106">Event ID</span></span>|-|  
|<span data-ttu-id="23c51-107">事件源</span><span class="sxs-lookup"><span data-stu-id="23c51-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="23c51-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="23c51-108"> EDI</span></span>|  
|<span data-ttu-id="23c51-109">组件</span><span class="sxs-lookup"><span data-stu-id="23c51-109">Component</span></span>|<span data-ttu-id="23c51-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="23c51-110">EDI Engine</span></span>|  
|<span data-ttu-id="23c51-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="23c51-111">Symbolic Name</span></span>|<span data-ttu-id="23c51-112">IdentitiesNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="23c51-112">IdentitiesNotFoundForBatch</span></span>|  
|<span data-ttu-id="23c51-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="23c51-113">Message Text</span></span>|<span data-ttu-id="23c51-114">找不到与批处理 {0} 相对应的业务标识。</span><span class="sxs-lookup"><span data-stu-id="23c51-114">Could not find Business Identities corresponding to batch {0}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="23c51-115">解释</span><span class="sxs-lookup"><span data-stu-id="23c51-115">Explanation</span></span>  
 <span data-ttu-id="23c51-116">此错误/警告/信息事件表明 BizTalk Server 由于数据不足而无法处理某个批处理消息。</span><span class="sxs-lookup"><span data-stu-id="23c51-116">This Error/Warning/Information event indicates BizTalk Server was not able to process a batch message because of insufficient data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23c51-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="23c51-117">User Action</span></span>  
 <span data-ttu-id="23c51-118">若要解决此错误，请确保具有给定 Id 的批处理中包含的协议的协议属性存在，并且协议指定了正确的业务标识。</span><span class="sxs-lookup"><span data-stu-id="23c51-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and proper business identities are specified for the agreement.</span></span>