---
title: 命名空间中找不到类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70011a83e5264344a5ef4f30c4525529aa403dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393775"
---
# <a name="type-cannot-be-found-in-namespace"></a><span data-ttu-id="7488c-102">命名空间中找不到类型</span><span class="sxs-lookup"><span data-stu-id="7488c-102">Type cannot be found in namespace</span></span>
## <a name="details"></a><span data-ttu-id="7488c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7488c-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="7488c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7488c-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="7488c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7488c-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="7488c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7488c-106">Event ID</span></span>     |                                         <span data-ttu-id="7488c-107">0</span><span class="sxs-lookup"><span data-stu-id="7488c-107">0</span></span>                                          |
|  <span data-ttu-id="7488c-108">事件源</span><span class="sxs-lookup"><span data-stu-id="7488c-108">Event Source</span></span>   |                                         <span data-ttu-id="7488c-109">0</span><span class="sxs-lookup"><span data-stu-id="7488c-109">0</span></span>                                          |
|    <span data-ttu-id="7488c-110">组件</span><span class="sxs-lookup"><span data-stu-id="7488c-110">Component</span></span>    |                                         <span data-ttu-id="7488c-111">0</span><span class="sxs-lookup"><span data-stu-id="7488c-111">0</span></span>                                          |
|  <span data-ttu-id="7488c-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="7488c-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="7488c-113">0</span><span class="sxs-lookup"><span data-stu-id="7488c-113">0</span></span>                                          |
|  <span data-ttu-id="7488c-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="7488c-114">Message Text</span></span>   |                <span data-ttu-id="7488c-115">错误：类型"{0}"不能在命名空间中找到"{1}"</span><span class="sxs-lookup"><span data-stu-id="7488c-115">Error: Type "{0}" cannot be found in namespace "{1}"</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="7488c-116">解释</span><span class="sxs-lookup"><span data-stu-id="7488c-116">Explanation</span></span>  
 <span data-ttu-id="7488c-117">此错误表示创建的项目所引用类型不能在指定的命名空间中找到。</span><span class="sxs-lookup"><span data-stu-id="7488c-117">This error indicates artifacts that are created are referencing types which cannot be found in the namespace specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7488c-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="7488c-118">User Action</span></span>  
 <span data-ttu-id="7488c-119">添加包含未找到，则类型的引用，并再次运行该向导 （如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="7488c-119">Add a reference that contain the type that is not found, and run the wizard again (if you own the WCF service that you are trying to consume).</span></span> <span data-ttu-id="7488c-120">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="7488c-120">Otherwise, contact the service provider.</span></span>