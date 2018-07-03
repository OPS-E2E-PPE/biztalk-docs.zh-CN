---
title: 未找到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37680b2-b38a-40f3-bb27-7b7281299ec3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98499420c773328d647a9c7fa1c80e3ab09ba1b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003454"
---
# <a name="application-not-found"></a><span data-ttu-id="37e19-102">找不到应用程序</span><span class="sxs-lookup"><span data-stu-id="37e19-102">Application not found</span></span>
## <a name="details"></a><span data-ttu-id="37e19-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="37e19-103">Details</span></span>  

|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="37e19-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="37e19-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| <span data-ttu-id="37e19-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="37e19-105">Product Version</span></span> |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    <span data-ttu-id="37e19-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="37e19-106">Event ID</span></span>     |                                                    <span data-ttu-id="37e19-107">0</span><span class="sxs-lookup"><span data-stu-id="37e19-107">0</span></span>                                                    |
|  <span data-ttu-id="37e19-108">事件源</span><span class="sxs-lookup"><span data-stu-id="37e19-108">Event Source</span></span>   |                                                    <span data-ttu-id="37e19-109">0</span><span class="sxs-lookup"><span data-stu-id="37e19-109">0</span></span>                                                    |
|    <span data-ttu-id="37e19-110">组件</span><span class="sxs-lookup"><span data-stu-id="37e19-110">Component</span></span>    |                                                    <span data-ttu-id="37e19-111">0</span><span class="sxs-lookup"><span data-stu-id="37e19-111">0</span></span>                                                    |
|  <span data-ttu-id="37e19-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="37e19-112">Symbolic Name</span></span>  |                                                    <span data-ttu-id="37e19-113">0</span><span class="sxs-lookup"><span data-stu-id="37e19-113">0</span></span>                                                    |
|  <span data-ttu-id="37e19-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="37e19-114">Message Text</span></span>   | <span data-ttu-id="37e19-115">应用程序"{0}"找不到。验证应用程序的默认 BizTalk 配置数据库中存在</span><span class="sxs-lookup"><span data-stu-id="37e19-115">Application "{0}" not found.Verify the application exists in the default BizTalk configuration database</span></span> |

## <a name="explanation"></a><span data-ttu-id="37e19-116">解释</span><span class="sxs-lookup"><span data-stu-id="37e19-116">Explanation</span></span>  
 <span data-ttu-id="37e19-117">此错误表示 BizTalk 使用的是 BizTalk 数据库中没有的应用程序。</span><span class="sxs-lookup"><span data-stu-id="37e19-117">This error indicates BizTalk is using an application that does not exist in the BizTalk databases.</span></span>  

## <a name="user-action"></a><span data-ttu-id="37e19-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="37e19-118">User Action</span></span>  
 <span data-ttu-id="37e19-119">使用以下过程配置有效的应用程序。</span><span class="sxs-lookup"><span data-stu-id="37e19-119">Use the following procedure to configure a valid application.</span></span>  

#### <a name="to-configure-a-valid-application"></a><span data-ttu-id="37e19-120">配置有效应用程序的步骤</span><span class="sxs-lookup"><span data-stu-id="37e19-120">To configure a valid application</span></span>  

1. <span data-ttu-id="37e19-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="37e19-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="37e19-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="37e19-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="37e19-123">确保应用程序在此处存在。</span><span class="sxs-lookup"><span data-stu-id="37e19-123">Ensure that the application exists there.</span></span> <span data-ttu-id="37e19-124">如果不存在，请选择其他有效应用程序。</span><span class="sxs-lookup"><span data-stu-id="37e19-124">If not, select a different valid application.</span></span>
