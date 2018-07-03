---
title: 单一登录： 事件 10515 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1c3d7498bcd6a045936103d682d3643761a182c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980814"
---
# <a name="single-sign-on-event-10515"></a><span data-ttu-id="cd699-102">单一登录： 事件 10515</span><span class="sxs-lookup"><span data-stu-id="cd699-102">Single Sign-On: Event 10515</span></span>
## <a name="details"></a><span data-ttu-id="cd699-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cd699-103">Details</span></span>  
  
|                 |                                                                               |
|-----------------|-------------------------------------------------------------------------------|
|  <span data-ttu-id="cd699-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cd699-104">Product Name</span></span>   |                           <span data-ttu-id="cd699-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cd699-105">Enterprise Single Sign-On</span></span>                           |
| <span data-ttu-id="cd699-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cd699-106">Product Version</span></span> |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]           |
|    <span data-ttu-id="cd699-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cd699-107">Event ID</span></span>     |                                     <span data-ttu-id="cd699-108">10515</span><span class="sxs-lookup"><span data-stu-id="cd699-108">10515</span></span>                                     |
|  <span data-ttu-id="cd699-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cd699-109">Event Source</span></span>   |                                    <span data-ttu-id="cd699-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cd699-110">ENTSSO</span></span>                                     |
|    <span data-ttu-id="cd699-111">组件</span><span class="sxs-lookup"><span data-stu-id="cd699-111">Component</span></span>    |                                      <span data-ttu-id="cd699-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cd699-112">N\A</span></span>                                      |
|  <span data-ttu-id="cd699-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cd699-113">Symbolic Name</span></span>  |                            <span data-ttu-id="cd699-114">SSO_ERROR_POLL_DATABASE</span><span class="sxs-lookup"><span data-stu-id="cd699-114">SSO_ERROR_POLL_DATABASE</span></span>                            |
|  <span data-ttu-id="cd699-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cd699-115">Message Text</span></span>   | <span data-ttu-id="cd699-116">丢失与 SSO 数据库的联系。</span><span class="sxs-lookup"><span data-stu-id="cd699-116">Lost contact with the SSO database.</span></span> <span data-ttu-id="cd699-117">请检查 SSO 数据库是否可用。</span><span class="sxs-lookup"><span data-stu-id="cd699-117">Check that the SSO database is available.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cd699-118">解释</span><span class="sxs-lookup"><span data-stu-id="cd699-118">Explanation</span></span>  
 <span data-ttu-id="cd699-119">此错误事件表示 SSO 服务已丢失与 SSO 数据库的联系。</span><span class="sxs-lookup"><span data-stu-id="cd699-119">This Error event indicates that the SSO Service has lost contact with the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd699-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="cd699-120">User Action</span></span>  
 <span data-ttu-id="cd699-121">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="cd699-121">To resolve this error, do one or more of the following:</span></span>  
  
- <span data-ttu-id="cd699-122">验证 SQL Server (MSSQLSERVER) 服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="cd699-122">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="cd699-123">如果在远程服务器上，则验证到 SQL Server 的网络连接是否正常。</span><span class="sxs-lookup"><span data-stu-id="cd699-123">Verify network connectivity to SQL Server if on a remote server.</span></span>  
  
  <span data-ttu-id="cd699-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="cd699-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
- [<span data-ttu-id="cd699-125">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cd699-125">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
- [<span data-ttu-id="cd699-126">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="cd699-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
- [<span data-ttu-id="cd699-127">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="cd699-127">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
  <span data-ttu-id="cd699-128">另请参阅 SQL Server 联机丛书</span><span class="sxs-lookup"><span data-stu-id="cd699-128">See also SQL Server Books Online</span></span>