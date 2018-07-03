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
ms.openlocfilehash: 8d07b1e5788ae696e94a3bbe326f2cfe79d1b76f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979926"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="9b3a1-102">反射 BizTalk 程序集时发生安全异常</span><span class="sxs-lookup"><span data-stu-id="9b3a1-102">A security exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="9b3a1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9b3a1-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9b3a1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9b3a1-104">Product Name</span></span>   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| <span data-ttu-id="9b3a1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9b3a1-105">Product Version</span></span> |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    <span data-ttu-id="9b3a1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9b3a1-106">Event ID</span></span>     |                                                                                                                                                                         <span data-ttu-id="9b3a1-107">0</span><span class="sxs-lookup"><span data-stu-id="9b3a1-107">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="9b3a1-108">事件源</span><span class="sxs-lookup"><span data-stu-id="9b3a1-108">Event Source</span></span>   |                                                                                                                                                                         <span data-ttu-id="9b3a1-109">0</span><span class="sxs-lookup"><span data-stu-id="9b3a1-109">0</span></span>                                                                                                                                                                          |
|    <span data-ttu-id="9b3a1-110">组件</span><span class="sxs-lookup"><span data-stu-id="9b3a1-110">Component</span></span>    |                                                                                                                                                                         <span data-ttu-id="9b3a1-111">0</span><span class="sxs-lookup"><span data-stu-id="9b3a1-111">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="9b3a1-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="9b3a1-112">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="9b3a1-113">0</span><span class="sxs-lookup"><span data-stu-id="9b3a1-113">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="9b3a1-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="9b3a1-114">Message Text</span></span>   | <span data-ttu-id="9b3a1-115">反射 BizTalk 程序集时发生安全异常"{0}"。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-115">A security exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="9b3a1-116">如果程序集位于共享网络文件夹中，则可能出现此问题。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-116">This problem may occur if the assembly is located in a shared network folder.</span></span> <span data-ttu-id="9b3a1-117">若要更正此问题，请尝试以下项之一： 1。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="9b3a1-118">将程序集及其依存关系复制到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-118">Copy the assembly and its dependencies to the local machine.</span></span> <span data-ttu-id="9b3a1-119">2.</span><span class="sxs-lookup"><span data-stu-id="9b3a1-119">2.</span></span> <span data-ttu-id="9b3a1-120">调整 .NET 配置运行时安全策略以允许访问。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-120">Adjust the .NET Configuration Runtime Security policy to permit access.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9b3a1-121">解释</span><span class="sxs-lookup"><span data-stu-id="9b3a1-121">Explanation</span></span>  
 <span data-ttu-id="9b3a1-122">尝试在不具有正确 .NET 策略的网络共享上发布 BizTalk 程序集时，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-122">This error will occur when trying to publish a BizTalk assembly that is on a network share without the right .NET policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b3a1-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="9b3a1-123">User Action</span></span>  
 <span data-ttu-id="9b3a1-124">除了执行错误消息中列出的特定步骤之外，还应在本地复制程序集。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-124">In addition to taking the specific steps outlined in the error message, copy the assembly locally.</span></span> <span data-ttu-id="9b3a1-125">或编辑策略以向本地 Intranet 授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-125">Or edit the policy to grant full trust to the local intranet.</span></span>  
  
 <span data-ttu-id="9b3a1-126">**使用代码访问安全策略工具 (Caspol.exe)**</span><span class="sxs-lookup"><span data-stu-id="9b3a1-126">**Using the Code Access Security Policy Tool (Caspol.exe)**</span></span>  
  
 <span data-ttu-id="9b3a1-127">您可以使用普通用户权限在用户级别为本地计算机上的文件夹授予信任。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-127">You can grant trust to a folder on your local computer at the User level with normal user permissions.</span></span> <span data-ttu-id="9b3a1-128">要向网络位置授予信任，您必须具有管理员权限，并且可以在计算机级别更改安全策略。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-128">To grant trust to a network location, you must have administrator privileges and change the security policy at the Machine level.</span></span> <span data-ttu-id="9b3a1-129">计算机策略级别独立于用户策略级别，即使用户策略向 Intranet 区域授予完全信任，计算机策略级别也不会向 Intranet 区域授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-129">The Machine policy level acts independently of the User policy level, and the machine policy level does not grant full trust to the Intranet zone even if the User policy does.</span></span> <span data-ttu-id="9b3a1-130">策略级别必须一致。</span><span class="sxs-lookup"><span data-stu-id="9b3a1-130">The policy levels must agree.</span></span>  
  
 <span data-ttu-id="9b3a1-131">**若要向本地文件夹授予完全信任**</span><span class="sxs-lookup"><span data-stu-id="9b3a1-131">**To grant full trust to a local folder**</span></span>  
  
-   <span data-ttu-id="9b3a1-132">在 Visual Studio 命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="9b3a1-132">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 <span data-ttu-id="9b3a1-133">**若要向网络文件夹授予完全信任**</span><span class="sxs-lookup"><span data-stu-id="9b3a1-133">**To grant full trust to a network folder**</span></span>  
  
-   <span data-ttu-id="9b3a1-134">在 Visual Studio 命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="9b3a1-134">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```