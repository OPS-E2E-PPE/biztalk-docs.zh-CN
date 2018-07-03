---
title: 单一登录： 事件 10514 |Microsoft Docs
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
ms.openlocfilehash: 06fff4fbbb9b5c4d32968312b0f585ffbf2f5bb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995302"
---
# <a name="single-sign-on-event-10514"></a><span data-ttu-id="f40aa-102">单一登录： 事件 10514</span><span class="sxs-lookup"><span data-stu-id="f40aa-102">Single Sign-On: Event 10514</span></span>
## <a name="details"></a><span data-ttu-id="f40aa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f40aa-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f40aa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f40aa-104">Product Name</span></span>   |                                                                                    <span data-ttu-id="f40aa-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f40aa-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="f40aa-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f40aa-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    <span data-ttu-id="f40aa-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f40aa-107">Event ID</span></span>     |                                                                                              <span data-ttu-id="f40aa-108">10514</span><span class="sxs-lookup"><span data-stu-id="f40aa-108">10514</span></span>                                                                                               |
|  <span data-ttu-id="f40aa-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f40aa-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="f40aa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f40aa-110">ENTSSO</span></span>                                                                                              |
|    <span data-ttu-id="f40aa-111">组件</span><span class="sxs-lookup"><span data-stu-id="f40aa-111">Component</span></span>    |                                                                                               <span data-ttu-id="f40aa-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f40aa-112">N\A</span></span>                                                                                                |
|  <span data-ttu-id="f40aa-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f40aa-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="f40aa-114">SSO_ERROR_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f40aa-114">SSO_ERROR_DB_ACCESS</span></span>                                                                                        |
|  <span data-ttu-id="f40aa-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f40aa-115">Message Text</span></span>   | <span data-ttu-id="f40aa-116">尝试访问 SSO 数据库时出错。%r</span><span class="sxs-lookup"><span data-stu-id="f40aa-116">An error occurred while attempting to access the SSO database.%r</span></span><br /><br /> <span data-ttu-id="f40aa-117">函数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f40aa-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="f40aa-118">文件: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f40aa-118">File: %2%r</span></span><br /><br /> <span data-ttu-id="f40aa-119">%3.%r</span><span class="sxs-lookup"><span data-stu-id="f40aa-119">%3.%r</span></span><br /><br /> <span data-ttu-id="f40aa-120">SQL 错误代码: %4 %r</span><span class="sxs-lookup"><span data-stu-id="f40aa-120">SQL Error code: %4%r</span></span><br /><br /> <span data-ttu-id="f40aa-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="f40aa-121">Error code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f40aa-122">解释</span><span class="sxs-lookup"><span data-stu-id="f40aa-122">Explanation</span></span>  
 <span data-ttu-id="f40aa-123">此错误事件表示尝试访问 SSO 数据库时接收到来自 SQL Server 的错误。</span><span class="sxs-lookup"><span data-stu-id="f40aa-123">This Error event indicates that an error was received from SQL Server when attempting to access the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f40aa-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="f40aa-124">User Action</span></span>  
 <span data-ttu-id="f40aa-125">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="f40aa-125">To resolve this error, do one or more of the following:</span></span>  
  
- <span data-ttu-id="f40aa-126">验证 SQL Server (MSSQLSERVER) 服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="f40aa-126">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="f40aa-127">检查使用的事件和错误消息中心的 SQL Server 错误代码[ http://go.microsoft.com/fwlink/?LinkID=20869 ](http://go.microsoft.com/fwlink/?LinkID=20869)。</span><span class="sxs-lookup"><span data-stu-id="f40aa-127">Check the SQL Server error code using the Events and Errors Message Center at [http://go.microsoft.com/fwlink/?LinkID=20869](http://go.microsoft.com/fwlink/?LinkID=20869).</span></span>  
  
  <span data-ttu-id="f40aa-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="f40aa-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
- [<span data-ttu-id="f40aa-129">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f40aa-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
- [<span data-ttu-id="f40aa-130">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="f40aa-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
  <span data-ttu-id="f40aa-131">另请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="f40aa-131">See also SQL Server Books Online.</span></span>