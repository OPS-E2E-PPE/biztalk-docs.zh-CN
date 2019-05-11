---
title: 无效的方案 |Microsoft Docs
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
ms.openlocfilehash: b29ee2fb5361aed12c7f90a094e3abeb7296e495
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381271"
---
# <a name="invalid-scheme"></a><span data-ttu-id="86f8d-102">方案无效</span><span class="sxs-lookup"><span data-stu-id="86f8d-102">Invalid scheme</span></span>
## <a name="details"></a><span data-ttu-id="86f8d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="86f8d-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="86f8d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="86f8d-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="86f8d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="86f8d-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="86f8d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="86f8d-106">Event ID</span></span>     |                                         <span data-ttu-id="86f8d-107">0</span><span class="sxs-lookup"><span data-stu-id="86f8d-107">0</span></span>                                          |
|  <span data-ttu-id="86f8d-108">事件源</span><span class="sxs-lookup"><span data-stu-id="86f8d-108">Event Source</span></span>   |                                         <span data-ttu-id="86f8d-109">0</span><span class="sxs-lookup"><span data-stu-id="86f8d-109">0</span></span>                                          |
|    <span data-ttu-id="86f8d-110">组件</span><span class="sxs-lookup"><span data-stu-id="86f8d-110">Component</span></span>    |                                         <span data-ttu-id="86f8d-111">0</span><span class="sxs-lookup"><span data-stu-id="86f8d-111">0</span></span>                                          |
|  <span data-ttu-id="86f8d-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="86f8d-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="86f8d-113">0</span><span class="sxs-lookup"><span data-stu-id="86f8d-113">0</span></span>                                          |
|  <span data-ttu-id="86f8d-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="86f8d-114">Message Text</span></span>   |                  <span data-ttu-id="86f8d-115">方案无效;应为方案"{0}"或"{1}"</span><span class="sxs-lookup"><span data-stu-id="86f8d-115">Invalid scheme; expecting scheme "{0}" or "{1}"</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="86f8d-116">解释</span><span class="sxs-lookup"><span data-stu-id="86f8d-116">Explanation</span></span>  
 <span data-ttu-id="86f8d-117">发生以下情况之一： URI （统一资源标识符） 字段中指定的地址必须以 http:// 或 https:// 开头。</span><span class="sxs-lookup"><span data-stu-id="86f8d-117">One of the following situations has occurred: the address that is specified in the URI (uniform resource identifier) field must start with either http:// or https://.</span></span> <span data-ttu-id="86f8d-118">或方案不匹配的传输绑定元素实现中指定的内容。</span><span class="sxs-lookup"><span data-stu-id="86f8d-118">Or the scheme does not match what is specified in the implementation of the transport binding element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86f8d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="86f8d-119">User Action</span></span>  
 <span data-ttu-id="86f8d-120">输入有效的代理地址以 http:// 或 https:// 开头的 URI</span><span class="sxs-lookup"><span data-stu-id="86f8d-120">Enter a valid proxy address URI that starts with http:// or https://</span></span>