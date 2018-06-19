---
title: 方案无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5736a3738a9598f4c4b419d7e291c3c3e32207f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257733"
---
# <a name="invalid-scheme"></a><span data-ttu-id="49c10-102">方案无效</span><span class="sxs-lookup"><span data-stu-id="49c10-102">Invalid scheme</span></span>
## <a name="details"></a><span data-ttu-id="49c10-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="49c10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49c10-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="49c10-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="49c10-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="49c10-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="49c10-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="49c10-106">Event ID</span></span>|<span data-ttu-id="49c10-107">0</span><span class="sxs-lookup"><span data-stu-id="49c10-107">0</span></span>|  
|<span data-ttu-id="49c10-108">事件源</span><span class="sxs-lookup"><span data-stu-id="49c10-108">Event Source</span></span>|<span data-ttu-id="49c10-109">0</span><span class="sxs-lookup"><span data-stu-id="49c10-109">0</span></span>|  
|<span data-ttu-id="49c10-110">组件</span><span class="sxs-lookup"><span data-stu-id="49c10-110">Component</span></span>|<span data-ttu-id="49c10-111">0</span><span class="sxs-lookup"><span data-stu-id="49c10-111">0</span></span>|  
|<span data-ttu-id="49c10-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="49c10-112">Symbolic Name</span></span>|<span data-ttu-id="49c10-113">0</span><span class="sxs-lookup"><span data-stu-id="49c10-113">0</span></span>|  
|<span data-ttu-id="49c10-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="49c10-114">Message Text</span></span>|<span data-ttu-id="49c10-115">方案无效;预期的方案"{0}"或"{1}"</span><span class="sxs-lookup"><span data-stu-id="49c10-115">Invalid scheme; expecting scheme "{0}" or "{1}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="49c10-116">解释</span><span class="sxs-lookup"><span data-stu-id="49c10-116">Explanation</span></span>  
 <span data-ttu-id="49c10-117">发生以下情况之一： URI （统一资源标识符） 字段中指定的地址必须以 http:// 或 https:// 开头。</span><span class="sxs-lookup"><span data-stu-id="49c10-117">One of the following situations has occurred: the address that is specified in the URI (uniform resource identifier) field must start with either http:// or https://.</span></span> <span data-ttu-id="49c10-118">或者，该方案与传输绑定元素的实现中指定的方案不匹配。</span><span class="sxs-lookup"><span data-stu-id="49c10-118">Or the scheme does not match what is specified in the implementation of the transport binding element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49c10-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="49c10-119">User Action</span></span>  
 <span data-ttu-id="49c10-120">输入以 http:// 或 https:// 开头的有效代理地址 URI</span><span class="sxs-lookup"><span data-stu-id="49c10-120">Enter a valid proxy address URI that starts with http:// or https://</span></span>