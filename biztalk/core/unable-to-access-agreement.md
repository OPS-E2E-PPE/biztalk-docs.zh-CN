---
title: 无法访问协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72890ee9-54c9-48ed-8c6e-8b329d79c68b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9c8d8126a7b38d95adfce1e813dd2a86ccde24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024531"
---
# <a name="unable-to-access-agreement"></a><span data-ttu-id="14fba-102">无法访问协议</span><span class="sxs-lookup"><span data-stu-id="14fba-102">Unable to access agreement</span></span>
## <a name="details"></a><span data-ttu-id="14fba-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="14fba-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="14fba-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="14fba-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="14fba-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="14fba-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="14fba-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="14fba-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="14fba-107">事件源</span><span class="sxs-lookup"><span data-stu-id="14fba-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14fba-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="14fba-108"> EDI</span></span> |
|    <span data-ttu-id="14fba-109">组件</span><span class="sxs-lookup"><span data-stu-id="14fba-109">Component</span></span>    |                                       <span data-ttu-id="14fba-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="14fba-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="14fba-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="14fba-111">Symbolic Name</span></span>  |                              <span data-ttu-id="14fba-112">UnableToLocateAS2PartyError</span><span class="sxs-lookup"><span data-stu-id="14fba-112">UnableToLocateAS2PartyError</span></span>                               |
|  <span data-ttu-id="14fba-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="14fba-113">Message Text</span></span>   |            <span data-ttu-id="14fba-114">无法访问协议。</span><span class="sxs-lookup"><span data-stu-id="14fba-114">Unable to access agreement.</span></span> <span data-ttu-id="14fba-115">AS2From: {0} AS2To: {1}。</span><span class="sxs-lookup"><span data-stu-id="14fba-115">AS2From: {0} AS2To: {1}.</span></span> <span data-ttu-id="14fba-116">错误：{2}</span><span class="sxs-lookup"><span data-stu-id="14fba-116">Error: {2}</span></span>             |

## <a name="explanation"></a><span data-ttu-id="14fba-117">解释</span><span class="sxs-lookup"><span data-stu-id="14fba-117">Explanation</span></span>  
 <span data-ttu-id="14fba-118">此错误表明 BizTalk Server 找不到给定限定符和值的参与方。</span><span class="sxs-lookup"><span data-stu-id="14fba-118">This error indicates BizTalk Server could not find a party for the given qualifier and value.</span></span>  

## <a name="user-action"></a><span data-ttu-id="14fba-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="14fba-119">User Action</span></span>  
 <span data-ttu-id="14fba-120">若要解决此错误，请为给定的限定符创建参与方别名：</span><span class="sxs-lookup"><span data-stu-id="14fba-120">To resolve this error, create a party alias for the given qualifier:</span></span>  

1. <span data-ttu-id="14fba-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="14fba-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="14fba-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="14fba-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  

3. <span data-ttu-id="14fba-123">右键单击正确的参与方。</span><span class="sxs-lookup"><span data-stu-id="14fba-123">Right-click the correct party.</span></span>  

4. <span data-ttu-id="14fba-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="14fba-124">Click **Properties**.</span></span>  

5. <span data-ttu-id="14fba-125">在 [*参与方名称*]**参与方属性**对话框框中，输入**EDIINT-AS2 From 值**中**名称**列。</span><span class="sxs-lookup"><span data-stu-id="14fba-125">In the [*party name*] **Party Properties** dialog box, enter **EDIINT-AS2 From Value** in the **Name** column.</span></span>  

6. <span data-ttu-id="14fba-126">输入中的参与方名称**值**列。</span><span class="sxs-lookup"><span data-stu-id="14fba-126">Enter the party name in the **Value** column.</span></span>  

7. <span data-ttu-id="14fba-127">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="14fba-127">Click **OK**.</span></span>
