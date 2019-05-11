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
ms.openlocfilehash: afca0825ee04334385925d08e3edb0d0ed055c19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398002"
---
# <a name="registry-errors"></a><span data-ttu-id="e2f3e-102">注册表错误</span><span class="sxs-lookup"><span data-stu-id="e2f3e-102">Registry Errors</span></span>
<span data-ttu-id="e2f3e-103">诊断和解决 WCF 注册表错误的信息。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-103">Information for diagnosing and resolving WCF Registry errors.</span></span>  

## <a name="failed-to-access-the-registry"></a><span data-ttu-id="e2f3e-104">未能访问注册表</span><span class="sxs-lookup"><span data-stu-id="e2f3e-104">Failed to access the registry</span></span>
  
|                 |                                   <span data-ttu-id="e2f3e-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="e2f3e-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e2f3e-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="e2f3e-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e2f3e-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="e2f3e-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e2f3e-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e2f3e-108">Event ID</span></span>     |                                         <span data-ttu-id="e2f3e-109">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-109">0</span></span>                                          |
|  <span data-ttu-id="e2f3e-110">事件源</span><span class="sxs-lookup"><span data-stu-id="e2f3e-110">Event Source</span></span>   |                                         <span data-ttu-id="e2f3e-111">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-111">0</span></span>                                          |
|    <span data-ttu-id="e2f3e-112">组件</span><span class="sxs-lookup"><span data-stu-id="e2f3e-112">Component</span></span>    |                                         <span data-ttu-id="e2f3e-113">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-113">0</span></span>                                          |
|  <span data-ttu-id="e2f3e-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="e2f3e-114">Symbolic Name</span></span>  |                                         <span data-ttu-id="e2f3e-115">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-115">0</span></span>                                          |
|  <span data-ttu-id="e2f3e-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="e2f3e-116">Message Text</span></span>   |                             <span data-ttu-id="e2f3e-117">无法打开 HKLM\\{0}。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-117">Failed to open HKLM\\{0}.</span></span>                              |
  
### <a name="explanation"></a><span data-ttu-id="e2f3e-118">解释</span><span class="sxs-lookup"><span data-stu-id="e2f3e-118">Explanation</span></span>  
 <span data-ttu-id="e2f3e-119">此错误表明访问注册表失败。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-119">This error indicates a failure to access the registry.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="e2f3e-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="e2f3e-120">User Action</span></span>  
 <span data-ttu-id="e2f3e-121">确保对注册表有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-121">Ensure you have read access to the registry.</span></span> <span data-ttu-id="e2f3e-122">若要访问注册表，请确保你具有管理员权限或计算机的管理员联系。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-122">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span>
 
## <a name="failed-to-obtain-biztalk-install-path"></a><span data-ttu-id="e2f3e-123">未能获取 BizTalk 安装路径</span><span class="sxs-lookup"><span data-stu-id="e2f3e-123">Failed to obtain BizTalk install path</span></span>
  
|                 |                                   <span data-ttu-id="e2f3e-124">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="e2f3e-124">Error Details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e2f3e-125">产品名称</span><span class="sxs-lookup"><span data-stu-id="e2f3e-125">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e2f3e-126">产品版本</span><span class="sxs-lookup"><span data-stu-id="e2f3e-126">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e2f3e-127">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e2f3e-127">Event ID</span></span>     |                                         <span data-ttu-id="e2f3e-128">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-128">0</span></span>                                          |
|  <span data-ttu-id="e2f3e-129">事件源</span><span class="sxs-lookup"><span data-stu-id="e2f3e-129">Event Source</span></span>   |                                         <span data-ttu-id="e2f3e-130">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-130">0</span></span>                                          |
|    <span data-ttu-id="e2f3e-131">组件</span><span class="sxs-lookup"><span data-stu-id="e2f3e-131">Component</span></span>    |                                         <span data-ttu-id="e2f3e-132">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-132">0</span></span>                                          |
|  <span data-ttu-id="e2f3e-133">符号名称</span><span class="sxs-lookup"><span data-stu-id="e2f3e-133">Symbolic Name</span></span>  |                                         <span data-ttu-id="e2f3e-134">0</span><span class="sxs-lookup"><span data-stu-id="e2f3e-134">0</span></span>                                          |
|  <span data-ttu-id="e2f3e-135">消息正文</span><span class="sxs-lookup"><span data-stu-id="e2f3e-135">Message Text</span></span>   |             <span data-ttu-id="e2f3e-136">未能从 HKLM 获取 BizTalk 安装路径\\{0}\\{1}</span><span class="sxs-lookup"><span data-stu-id="e2f3e-136">Failed to obtain BizTalk install path from HKLM\\{0}\\{1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="e2f3e-137">解释</span><span class="sxs-lookup"><span data-stu-id="e2f3e-137">Explanation</span></span>  
 <span data-ttu-id="e2f3e-138">此错误表示无法访问注册表，并且该密钥具有不正确的值。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-138">This error indicates a failure to access the registry, and that the key has an incorrect value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e2f3e-139">用户操作</span><span class="sxs-lookup"><span data-stu-id="e2f3e-139">User Action</span></span>  
 <span data-ttu-id="e2f3e-140">确保对注册表有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-140">Ensure you have read access to the registry.</span></span> <span data-ttu-id="e2f3e-141">确保密钥具有正确的值。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-141">Ensure the key has the correct value.</span></span> <span data-ttu-id="e2f3e-142">若要访问注册表，请确保你具有管理员权限或计算机的管理员联系。</span><span class="sxs-lookup"><span data-stu-id="e2f3e-142">To access the registry, ensure you have Administrator privileges or contact the administrator of the machine.</span></span> 