---
title: 无效的标识符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f87e1e42-457f-4d04-a1d2-6b796f3fa7b7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b349991d0e0d6949754c804fcd1ebf16ea7ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012344"
---
# <a name="invalid-identifier"></a><span data-ttu-id="8c0bb-102">无效的标识符</span><span class="sxs-lookup"><span data-stu-id="8c0bb-102">Invalid identifier</span></span>
## <a name="details"></a><span data-ttu-id="8c0bb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8c0bb-103">Details</span></span>  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8c0bb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8c0bb-104">Product Name</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| <span data-ttu-id="8c0bb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8c0bb-105">Product Version</span></span> |                                                        [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                         |
|    <span data-ttu-id="8c0bb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8c0bb-106">Event ID</span></span>     |                                                                                     <span data-ttu-id="8c0bb-107">0</span><span class="sxs-lookup"><span data-stu-id="8c0bb-107">0</span></span>                                                                                     |
|  <span data-ttu-id="8c0bb-108">事件源</span><span class="sxs-lookup"><span data-stu-id="8c0bb-108">Event Source</span></span>   |                                                                                     <span data-ttu-id="8c0bb-109">0</span><span class="sxs-lookup"><span data-stu-id="8c0bb-109">0</span></span>                                                                                     |
|    <span data-ttu-id="8c0bb-110">组件</span><span class="sxs-lookup"><span data-stu-id="8c0bb-110">Component</span></span>    |                                                                                     <span data-ttu-id="8c0bb-111">0</span><span class="sxs-lookup"><span data-stu-id="8c0bb-111">0</span></span>                                                                                     |
|  <span data-ttu-id="8c0bb-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="8c0bb-112">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="8c0bb-113">0</span><span class="sxs-lookup"><span data-stu-id="8c0bb-113">0</span></span>                                                                                     |
|  <span data-ttu-id="8c0bb-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="8c0bb-114">Message Text</span></span>   | <span data-ttu-id="8c0bb-115">"{0}"不是有效标识符。</span><span class="sxs-lookup"><span data-stu-id="8c0bb-115">"{0}" is not a valid identifier.</span></span> <span data-ttu-id="8c0bb-116">正在还原原始名称。</span><span class="sxs-lookup"><span data-stu-id="8c0bb-116">Restoring original name.</span></span> <span data-ttu-id="8c0bb-117">（是有效的标识符以字母开头后, 跟零个或多个字母或数字和不能包含空格。）</span><span class="sxs-lookup"><span data-stu-id="8c0bb-117">(A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8c0bb-118">解释</span><span class="sxs-lookup"><span data-stu-id="8c0bb-118">Explanation</span></span>  
 <span data-ttu-id="8c0bb-119">此错误表明发布一个架构不是有效的.net 标识符时定义的 web 方法。</span><span class="sxs-lookup"><span data-stu-id="8c0bb-119">This error indicates the web methods defined when publishing a schema is not a valid .net identifier.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8c0bb-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="8c0bb-120">User Action</span></span>  
 <span data-ttu-id="8c0bb-121">将 web 方法重命名为有效的.net 标识符。</span><span class="sxs-lookup"><span data-stu-id="8c0bb-121">Rename the web methods to a valid .net identifier.</span></span> <span data-ttu-id="8c0bb-122">有效的标识符由一个字母后跟零个或多个字母或数字组成，但不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="8c0bb-122">A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.</span></span>