---
title: 找不到文件专用于反映将 BizTalk 程序集时发生异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804428d71c33d0c45d75443bbc5118a2dfed9ac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362410"
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="38c03-102">找不到文件专用于反映将 BizTalk 程序集时发生异常</span><span class="sxs-lookup"><span data-stu-id="38c03-102">A file not found exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="38c03-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="38c03-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="38c03-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="38c03-104">Product Name</span></span>   |                                                                                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                           |
| <span data-ttu-id="38c03-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="38c03-105">Product Version</span></span> |                                                                                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                       |
|    <span data-ttu-id="38c03-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="38c03-106">Event ID</span></span>     |                                                                                                                                                                   <span data-ttu-id="38c03-107">0</span><span class="sxs-lookup"><span data-stu-id="38c03-107">0</span></span>                                                                                                                                                                    |
|  <span data-ttu-id="38c03-108">事件源</span><span class="sxs-lookup"><span data-stu-id="38c03-108">Event Source</span></span>   |                                                                                                                                                                   <span data-ttu-id="38c03-109">0</span><span class="sxs-lookup"><span data-stu-id="38c03-109">0</span></span>                                                                                                                                                                    |
|    <span data-ttu-id="38c03-110">组件</span><span class="sxs-lookup"><span data-stu-id="38c03-110">Component</span></span>    |                                                                                                                                                                   <span data-ttu-id="38c03-111">0</span><span class="sxs-lookup"><span data-stu-id="38c03-111">0</span></span>                                                                                                                                                                    |
|  <span data-ttu-id="38c03-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="38c03-112">Symbolic Name</span></span>  |                                                                                                                                                                   <span data-ttu-id="38c03-113">0</span><span class="sxs-lookup"><span data-stu-id="38c03-113">0</span></span>                                                                                                                                                                    |
|  <span data-ttu-id="38c03-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="38c03-114">Message Text</span></span>   | <span data-ttu-id="38c03-115">找不到文件专用于反映将 BizTalk 程序集时出现异常"{0}"。</span><span class="sxs-lookup"><span data-stu-id="38c03-115">A file not found exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="38c03-116">如果一个或多个依赖项不可用，则可能会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="38c03-116">This problem may occur if one or more dependencies are not available.</span></span> <span data-ttu-id="38c03-117">若要更正此问题，请尝试以下项之一：1.</span><span class="sxs-lookup"><span data-stu-id="38c03-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="38c03-118">将程序集的依赖项复制到同一文件夹。</span><span class="sxs-lookup"><span data-stu-id="38c03-118">Copy the dependencies of the assembly to the same folder.</span></span> <span data-ttu-id="38c03-119">2.</span><span class="sxs-lookup"><span data-stu-id="38c03-119">2.</span></span> <span data-ttu-id="38c03-120">安装到全局程序集缓存中缺少的依赖项。</span><span class="sxs-lookup"><span data-stu-id="38c03-120">Install the missing dependencies into the Global Assembly Cache.</span></span> |

## <a name="explanation"></a><span data-ttu-id="38c03-121">解释</span><span class="sxs-lookup"><span data-stu-id="38c03-121">Explanation</span></span>  
 <span data-ttu-id="38c03-122">此错误表明正在发布的引用 BizTalk 程序集不在全局程序集缓存 (GAC) 或相同的目录中的另一个程序集。</span><span class="sxs-lookup"><span data-stu-id="38c03-122">This error indicates the BizTalk Assembly that is being published references another assembly that is not in the Global Assembly Cache (GAC) or in the same directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="38c03-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="38c03-123">User Action</span></span>  
 <span data-ttu-id="38c03-124">除了错误消息中指定的操作，将引用程序集移到全局程序集缓存或将其复制到与 BizTalk 程序集相同的位置</span><span class="sxs-lookup"><span data-stu-id="38c03-124">In addition to the actions specified in the error message, move the reference assembly to the Global Assembly Cache or copy it to the same location as the BizTalk assembly</span></span>  

1. <span data-ttu-id="38c03-125">单击**启动**，依次指向**所有程序**，指向**Visual Studio**，然后单击**Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="38c03-125">Click **Start**, point to **All Programs**, point to **Visual Studio**, and then click **Visual Studio**.</span></span>  

2. <span data-ttu-id="38c03-126">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="38c03-126">Open a command prompt.</span></span>  

3. <span data-ttu-id="38c03-127">浏览到该程序集的位置并输入**gacutil /I /\<**<em>程序集名称</em>**\>.dll**</span><span class="sxs-lookup"><span data-stu-id="38c03-127">Browse to the location of the assembly, and enter **gacutil /I /\<**<em>assembly name</em>**\>.dll**</span></span>
