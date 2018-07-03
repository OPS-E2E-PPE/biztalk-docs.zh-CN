---
title: 注册表错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5bf2cd-f807-4083-8687-4416a2ee2908
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62522299866748d92abf91d36a01444c3175b070
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975110"
---
# <a name="registry-errors"></a><span data-ttu-id="14d72-102">注册表错误</span><span class="sxs-lookup"><span data-stu-id="14d72-102">Registry Errors</span></span>
<span data-ttu-id="14d72-103">诊断和解决 WCF 注册表错误的信息。</span><span class="sxs-lookup"><span data-stu-id="14d72-103">Information for diagnosing and resolving WCF Registry errors.</span></span>  

## <a name="failed-to-access-the-registry"></a><span data-ttu-id="14d72-104">未能访问注册表</span><span class="sxs-lookup"><span data-stu-id="14d72-104">Failed to access the registry</span></span>
  
|                 |                                   <span data-ttu-id="14d72-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="14d72-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="14d72-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="14d72-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="14d72-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="14d72-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="14d72-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="14d72-108">Event ID</span></span>     |                                         <span data-ttu-id="14d72-109">0</span><span class="sxs-lookup"><span data-stu-id="14d72-109">0</span></span>                                          |
|  <span data-ttu-id="14d72-110">事件源</span><span class="sxs-lookup"><span data-stu-id="14d72-110">Event Source</span></span>   |                                         <span data-ttu-id="14d72-111">0</span><span class="sxs-lookup"><span data-stu-id="14d72-111">0</span></span>                                          |
|    <span data-ttu-id="14d72-112">组件</span><span class="sxs-lookup"><span data-stu-id="14d72-112">Component</span></span>    |                                         <span data-ttu-id="14d72-113">0</span><span class="sxs-lookup"><span data-stu-id="14d72-113">0</span></span>                                          |
|  <span data-ttu-id="14d72-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="14d72-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="14d72-115">0</span><span class="sxs-lookup"><span data-stu-id="14d72-115">0</span></span>                                          |
|  <span data-ttu-id="14d72-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="14d72-116">Message Text</span></span>   |                             <span data-ttu-id="14d72-117">无法打开 HKLM\\{0}。</span><span class="sxs-lookup"><span data-stu-id="14d72-117">Failed to open HKLM\\{0}.</span></span>                              |
  
### <a name="explanation"></a><span data-ttu-id="14d72-118">解释</span><span class="sxs-lookup"><span data-stu-id="14d72-118">Explanation</span></span>  
 <span data-ttu-id="14d72-119">此错误表明访问注册表失败。</span><span class="sxs-lookup"><span data-stu-id="14d72-119">This error indicates a failure to access the registry.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="14d72-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="14d72-120">User Action</span></span>  
 <span data-ttu-id="14d72-121">确保您具有注册表的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="14d72-121">Ensure you have read access to the registry.</span></span> <span data-ttu-id="14d72-122">要访问注册表，请确保您具有管理员权限，或者与计算机管理员联系。</span><span class="sxs-lookup"><span data-stu-id="14d72-122">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span>
 
## <a name="failed-to-obtain-biztalk-install-path"></a><span data-ttu-id="14d72-123">未能获取 BizTalk 安装路径</span><span class="sxs-lookup"><span data-stu-id="14d72-123">Failed to obtain BizTalk install path</span></span>
  
|                 |                                   <span data-ttu-id="14d72-124">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="14d72-124">Error Details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="14d72-125">产品名称</span><span class="sxs-lookup"><span data-stu-id="14d72-125">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="14d72-126">产品版本</span><span class="sxs-lookup"><span data-stu-id="14d72-126">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="14d72-127">事件 ID</span><span class="sxs-lookup"><span data-stu-id="14d72-127">Event ID</span></span>     |                                         <span data-ttu-id="14d72-128">0</span><span class="sxs-lookup"><span data-stu-id="14d72-128">0</span></span>                                          |
|  <span data-ttu-id="14d72-129">事件源</span><span class="sxs-lookup"><span data-stu-id="14d72-129">Event Source</span></span>   |                                         <span data-ttu-id="14d72-130">0</span><span class="sxs-lookup"><span data-stu-id="14d72-130">0</span></span>                                          |
|    <span data-ttu-id="14d72-131">组件</span><span class="sxs-lookup"><span data-stu-id="14d72-131">Component</span></span>    |                                         <span data-ttu-id="14d72-132">0</span><span class="sxs-lookup"><span data-stu-id="14d72-132">0</span></span>                                          |
|  <span data-ttu-id="14d72-133">符号名称</span><span class="sxs-lookup"><span data-stu-id="14d72-133">Symbolic Name</span></span>  |                                         <span data-ttu-id="14d72-134">0</span><span class="sxs-lookup"><span data-stu-id="14d72-134">0</span></span>                                          |
|  <span data-ttu-id="14d72-135">消息正文</span><span class="sxs-lookup"><span data-stu-id="14d72-135">Message Text</span></span>   |             <span data-ttu-id="14d72-136">未能从 HKLM 获取 BizTalk 安装路径\\{0}\\{1}</span><span class="sxs-lookup"><span data-stu-id="14d72-136">Failed to obtain BizTalk install path from HKLM\\{0}\\{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="14d72-137">解释</span><span class="sxs-lookup"><span data-stu-id="14d72-137">Explanation</span></span>  
 <span data-ttu-id="14d72-138">此错误表明访问注册表失败，并且该密钥具有不正确的值。</span><span class="sxs-lookup"><span data-stu-id="14d72-138">This error indicates a failure to access the registry, and that the key has an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14d72-139">用户操作</span><span class="sxs-lookup"><span data-stu-id="14d72-139">User Action</span></span>  
 <span data-ttu-id="14d72-140">确保您具有注册表的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="14d72-140">Ensure you have read access to the registry.</span></span> <span data-ttu-id="14d72-141">确保密钥具有正确的值。</span><span class="sxs-lookup"><span data-stu-id="14d72-141">Ensure the key has the correct value.</span></span> <span data-ttu-id="14d72-142">要访问注册表，请确保您具有管理员权限，或者与计算机管理员联系。</span><span class="sxs-lookup"><span data-stu-id="14d72-142">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span> 