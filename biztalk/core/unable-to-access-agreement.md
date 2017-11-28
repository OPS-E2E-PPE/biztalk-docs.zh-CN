---
title: "无法访问协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72890ee9-54c9-48ed-8c6e-8b329d79c68b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a28b2b3587781d66e8788ca88931c7c5522bac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-agreement"></a><span data-ttu-id="28210-102">无法访问协议</span><span class="sxs-lookup"><span data-stu-id="28210-102">Unable to access agreement</span></span>
## <a name="details"></a><span data-ttu-id="28210-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="28210-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28210-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="28210-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="28210-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="28210-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="28210-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="28210-106">Event ID</span></span>|-|  
|<span data-ttu-id="28210-107">事件源</span><span class="sxs-lookup"><span data-stu-id="28210-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="28210-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="28210-108"> EDI</span></span>|  
|<span data-ttu-id="28210-109">组件</span><span class="sxs-lookup"><span data-stu-id="28210-109">Component</span></span>|<span data-ttu-id="28210-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="28210-110">EDI Engine</span></span>|  
|<span data-ttu-id="28210-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="28210-111">Symbolic Name</span></span>|<span data-ttu-id="28210-112">UnableToLocateAS2PartyError</span><span class="sxs-lookup"><span data-stu-id="28210-112">UnableToLocateAS2PartyError</span></span>|  
|<span data-ttu-id="28210-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="28210-113">Message Text</span></span>|<span data-ttu-id="28210-114">无法访问协议。</span><span class="sxs-lookup"><span data-stu-id="28210-114">Unable to access agreement.</span></span> <span data-ttu-id="28210-115">AS2From: {0} AS2To: {1}。</span><span class="sxs-lookup"><span data-stu-id="28210-115">AS2From: {0} AS2To: {1}.</span></span> <span data-ttu-id="28210-116">错误： {2}</span><span class="sxs-lookup"><span data-stu-id="28210-116">Error: {2}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28210-117">解释</span><span class="sxs-lookup"><span data-stu-id="28210-117">Explanation</span></span>  
 <span data-ttu-id="28210-118">此错误表明 BizTalk Server 找不到给定限定符和值的参与方。</span><span class="sxs-lookup"><span data-stu-id="28210-118">This error indicates BizTalk Server could not find a party for the given qualifier and value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28210-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="28210-119">User Action</span></span>  
 <span data-ttu-id="28210-120">若要解决此错误，请为给定的限定符创建参与方别名：</span><span class="sxs-lookup"><span data-stu-id="28210-120">To resolve this error, create a party alias for the given qualifier:</span></span>  
  
1.  <span data-ttu-id="28210-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="28210-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="28210-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="28210-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  
  
3.  <span data-ttu-id="28210-123">右键单击正确方。</span><span class="sxs-lookup"><span data-stu-id="28210-123">Right-click the correct party.</span></span>  
  
4.  <span data-ttu-id="28210-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="28210-124">Click **Properties**.</span></span>  
  
5.  <span data-ttu-id="28210-125">在 [*方名称*]**参与方属性**对话框框中，输入**EDIINT AS2 从值**中**名称**列。</span><span class="sxs-lookup"><span data-stu-id="28210-125">In the [*party name*] **Party Properties** dialog box, enter **EDIINT-AS2 From Value** in the **Name** column.</span></span>  
  
6.  <span data-ttu-id="28210-126">输入中的方名称**值**列。</span><span class="sxs-lookup"><span data-stu-id="28210-126">Enter the party name in the **Value** column.</span></span>  
  
7.  <span data-ttu-id="28210-127">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="28210-127">Click **OK**.</span></span>