---
title: 无法获取数据库或服务器名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e2d346c2771328ac67df3e2aa7454288779cb9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990262"
---
# <a name="could-not-get-the-database-or-the-server-names"></a><span data-ttu-id="7a25a-102">无法获取数据库或服务器名称</span><span class="sxs-lookup"><span data-stu-id="7a25a-102">Could not get the database or the server names</span></span>
## <a name="details"></a><span data-ttu-id="7a25a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7a25a-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a25a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7a25a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7a25a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7a25a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7a25a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7a25a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7a25a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7a25a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7a25a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7a25a-108"> EDI</span></span> |
|    <span data-ttu-id="7a25a-109">组件</span><span class="sxs-lookup"><span data-stu-id="7a25a-109">Component</span></span>    |                                       <span data-ttu-id="7a25a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7a25a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7a25a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7a25a-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="7a25a-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="7a25a-112">Message Text</span></span>   |                     <span data-ttu-id="7a25a-113">无法获取数据库或服务器名称</span><span class="sxs-lookup"><span data-stu-id="7a25a-113">Could not get the database or the server names</span></span>                     |

## <a name="explanation"></a><span data-ttu-id="7a25a-114">解释</span><span class="sxs-lookup"><span data-stu-id="7a25a-114">Explanation</span></span>  
 <span data-ttu-id="7a25a-115">此错误表明 BizTalk 无法从注册表中读取 BizTalkMgmtDb 名称和服务器名称。</span><span class="sxs-lookup"><span data-stu-id="7a25a-115">This error indicates BizTalk could not read the BizTalkMgmtDb name and Server name from registry.</span></span> <span data-ttu-id="7a25a-116">此错误的一个可能原因是未配置 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="7a25a-116">One possible reason for this error is the BizTalk Group is not configured.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7a25a-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7a25a-117">User Action</span></span>  
 <span data-ttu-id="7a25a-118">若要解决此错误，请配置 BizTalk 组：</span><span class="sxs-lookup"><span data-stu-id="7a25a-118">To resolve this error, configure the BizTalk Group:</span></span>  

1. <span data-ttu-id="7a25a-119">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7a25a-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="7a25a-120">在控制台根目录中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7a25a-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

3. <span data-ttu-id="7a25a-121">右键单击**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="7a25a-121">Right-click **BizTalk Group**.</span></span>  

4. <span data-ttu-id="7a25a-122">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="7a25a-122">Click **Properties**.</span></span>  

5. <span data-ttu-id="7a25a-123">在左窗格中，单击**常规**。</span><span class="sxs-lookup"><span data-stu-id="7a25a-123">In the left pane, click **General**.</span></span>  

6. <span data-ttu-id="7a25a-124">验证是否**服务器**名称和**数据库**名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="7a25a-124">Verify the **Server** name and **Database** name are correct.</span></span>
