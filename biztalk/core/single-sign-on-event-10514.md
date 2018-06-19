---
title: 单一登录： 事件 10514 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b527841-a2e2-44c7-a9cb-6e9a8eea2fba
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40077ead4157b4cc6c91a2c44b4a19569d76ebc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270501"
---
# <a name="single-sign-on-event-10514"></a><span data-ttu-id="87383-102">单一登录： 事件 10514</span><span class="sxs-lookup"><span data-stu-id="87383-102">Single Sign-On: Event 10514</span></span>
## <a name="details"></a><span data-ttu-id="87383-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="87383-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87383-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="87383-104">Product Name</span></span>|<span data-ttu-id="87383-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="87383-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="87383-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="87383-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="87383-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="87383-107">Event ID</span></span>|<span data-ttu-id="87383-108">10514</span><span class="sxs-lookup"><span data-stu-id="87383-108">10514</span></span>|  
|<span data-ttu-id="87383-109">事件源</span><span class="sxs-lookup"><span data-stu-id="87383-109">Event Source</span></span>|<span data-ttu-id="87383-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="87383-110">ENTSSO</span></span>|  
|<span data-ttu-id="87383-111">组件</span><span class="sxs-lookup"><span data-stu-id="87383-111">Component</span></span>|<span data-ttu-id="87383-112">N\A</span><span class="sxs-lookup"><span data-stu-id="87383-112">N\A</span></span>|  
|<span data-ttu-id="87383-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="87383-113">Symbolic Name</span></span>|<span data-ttu-id="87383-114">SSO_ERROR_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="87383-114">SSO_ERROR_DB_ACCESS</span></span>|  
|<span data-ttu-id="87383-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="87383-115">Message Text</span></span>|<span data-ttu-id="87383-116">尝试访问 SSO 数据库时出错。%r</span><span class="sxs-lookup"><span data-stu-id="87383-116">An error occurred while attempting to access the SSO database.%r</span></span><br /><br /> <span data-ttu-id="87383-117">函数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="87383-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="87383-118">文件: %2 %r</span><span class="sxs-lookup"><span data-stu-id="87383-118">File: %2%r</span></span><br /><br /> <span data-ttu-id="87383-119">%3.%r</span><span class="sxs-lookup"><span data-stu-id="87383-119">%3.%r</span></span><br /><br /> <span data-ttu-id="87383-120">SQL 错误代码: %4 %r</span><span class="sxs-lookup"><span data-stu-id="87383-120">SQL Error code: %4%r</span></span><br /><br /> <span data-ttu-id="87383-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="87383-121">Error code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87383-122">解释</span><span class="sxs-lookup"><span data-stu-id="87383-122">Explanation</span></span>  
 <span data-ttu-id="87383-123">此错误事件表示尝试访问 SSO 数据库时接收到来自 SQL Server 的错误。</span><span class="sxs-lookup"><span data-stu-id="87383-123">This Error event indicates that an error was received from SQL Server when attempting to access the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87383-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="87383-124">User Action</span></span>  
 <span data-ttu-id="87383-125">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="87383-125">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="87383-126">验证 SQL Server (MSSQLSERVER) 服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="87383-126">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
-   <span data-ttu-id="87383-127">检查使用的事件和错误消息中心的 SQL Server 错误代码[http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869)。</span><span class="sxs-lookup"><span data-stu-id="87383-127">Check the SQL Server error code using the Events and Errors Message Center at [http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869).</span></span>  
  
 <span data-ttu-id="87383-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="87383-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="87383-129">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="87383-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="87383-130">如何显示的 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="87383-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
 <span data-ttu-id="87383-131">另请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="87383-131">See also SQL Server Books Online.</span></span>