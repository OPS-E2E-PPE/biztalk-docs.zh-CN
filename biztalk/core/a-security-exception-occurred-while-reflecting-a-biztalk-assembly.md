---
title: 反射 BizTalk 程序集时发生安全异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3161593fb871e93852480f717216391daac67e7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362422"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="eeef9-102">反射 BizTalk 程序集时发生安全异常</span><span class="sxs-lookup"><span data-stu-id="eeef9-102">A security exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="eeef9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="eeef9-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="eeef9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="eeef9-104">Product Name</span></span>   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| <span data-ttu-id="eeef9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="eeef9-105">Product Version</span></span> |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    <span data-ttu-id="eeef9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eeef9-106">Event ID</span></span>     |                                                                                                                                                                         <span data-ttu-id="eeef9-107">0</span><span class="sxs-lookup"><span data-stu-id="eeef9-107">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="eeef9-108">事件源</span><span class="sxs-lookup"><span data-stu-id="eeef9-108">Event Source</span></span>   |                                                                                                                                                                         <span data-ttu-id="eeef9-109">0</span><span class="sxs-lookup"><span data-stu-id="eeef9-109">0</span></span>                                                                                                                                                                          |
|    <span data-ttu-id="eeef9-110">组件</span><span class="sxs-lookup"><span data-stu-id="eeef9-110">Component</span></span>    |                                                                                                                                                                         <span data-ttu-id="eeef9-111">0</span><span class="sxs-lookup"><span data-stu-id="eeef9-111">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="eeef9-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="eeef9-112">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="eeef9-113">0</span><span class="sxs-lookup"><span data-stu-id="eeef9-113">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="eeef9-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="eeef9-114">Message Text</span></span>   | <span data-ttu-id="eeef9-115">反射 BizTalk 程序集时发生安全异常"{0}"。</span><span class="sxs-lookup"><span data-stu-id="eeef9-115">A security exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="eeef9-116">如果该程序集位于共享的网络文件夹中，可能会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="eeef9-116">This problem may occur if the assembly is located in a shared network folder.</span></span> <span data-ttu-id="eeef9-117">若要更正此问题，请尝试以下项之一：1.</span><span class="sxs-lookup"><span data-stu-id="eeef9-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="eeef9-118">将程序集和其依赖项复制到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="eeef9-118">Copy the assembly and its dependencies to the local machine.</span></span> <span data-ttu-id="eeef9-119">2.</span><span class="sxs-lookup"><span data-stu-id="eeef9-119">2.</span></span> <span data-ttu-id="eeef9-120">调整.NET 配置运行时安全策略以允许访问。</span><span class="sxs-lookup"><span data-stu-id="eeef9-120">Adjust the .NET Configuration Runtime Security policy to permit access.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="eeef9-121">解释</span><span class="sxs-lookup"><span data-stu-id="eeef9-121">Explanation</span></span>  
 <span data-ttu-id="eeef9-122">尝试发布不具有正确.NET 策略的情况下在网络共享上的 BizTalk 程序集时，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="eeef9-122">This error will occur when trying to publish a BizTalk assembly that is on a network share without the right .NET policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eeef9-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="eeef9-123">User Action</span></span>  
 <span data-ttu-id="eeef9-124">除了错误消息中所述的特定步骤，将复制本地程序集。</span><span class="sxs-lookup"><span data-stu-id="eeef9-124">In addition to taking the specific steps outlined in the error message, copy the assembly locally.</span></span> <span data-ttu-id="eeef9-125">或编辑策略以向本地 intranet 授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="eeef9-125">Or edit the policy to grant full trust to the local intranet.</span></span>  
  
 <span data-ttu-id="eeef9-126">**使用代码访问安全策略工具 (Caspol.exe)**</span><span class="sxs-lookup"><span data-stu-id="eeef9-126">**Using the Code Access Security Policy Tool (Caspol.exe)**</span></span>  
  
 <span data-ttu-id="eeef9-127">在用户级别的普通用户权限与在本地计算机上，可以授予对文件夹的信任。</span><span class="sxs-lookup"><span data-stu-id="eeef9-127">You can grant trust to a folder on your local computer at the User level with normal user permissions.</span></span> <span data-ttu-id="eeef9-128">若要向网络位置授予信任，必须具有管理员权限并更改在计算机级别的安全策略。</span><span class="sxs-lookup"><span data-stu-id="eeef9-128">To grant trust to a network location, you must have administrator privileges and change the security policy at the Machine level.</span></span> <span data-ttu-id="eeef9-129">计算机策略级别可独立于用户策略级别，即使用户策略，计算机策略级别不会授予完全信任权限的 Intranet 区域。</span><span class="sxs-lookup"><span data-stu-id="eeef9-129">The Machine policy level acts independently of the User policy level, and the machine policy level does not grant full trust to the Intranet zone even if the User policy does.</span></span> <span data-ttu-id="eeef9-130">策略级别必须一致。</span><span class="sxs-lookup"><span data-stu-id="eeef9-130">The policy levels must agree.</span></span>  
  
 <span data-ttu-id="eeef9-131">**若要向本地文件夹授予完全信任**</span><span class="sxs-lookup"><span data-stu-id="eeef9-131">**To grant full trust to a local folder**</span></span>  
  
-   <span data-ttu-id="eeef9-132">在 Visual Studio 命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="eeef9-132">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 <span data-ttu-id="eeef9-133">**若要向网络文件夹授予完全信任**</span><span class="sxs-lookup"><span data-stu-id="eeef9-133">**To grant full trust to a network folder**</span></span>  
  
-   <span data-ttu-id="eeef9-134">在 Visual Studio 命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="eeef9-134">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```