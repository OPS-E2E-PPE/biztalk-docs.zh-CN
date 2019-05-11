---
title: 单一登录：Event 10513 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ec0cb1df806771e3676bcd580be2965498b618a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243397"
---
# <a name="single-sign-on-event-10513"></a><span data-ttu-id="84283-102">单一登录：事件 10513</span><span class="sxs-lookup"><span data-stu-id="84283-102">Single Sign-On: Event 10513</span></span>
## <a name="details"></a><span data-ttu-id="84283-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="84283-103">Details</span></span>  

|                 |                                                                                      |
|-----------------|--------------------------------------------------------------------------------------|
|  <span data-ttu-id="84283-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="84283-104">Product Name</span></span>   |                              <span data-ttu-id="84283-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="84283-105">Enterprise Single Sign-On</span></span>                               |
| <span data-ttu-id="84283-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="84283-106">Product Version</span></span> |              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    <span data-ttu-id="84283-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="84283-107">Event ID</span></span>     |                                        <span data-ttu-id="84283-108">10513</span><span class="sxs-lookup"><span data-stu-id="84283-108">10513</span></span>                                         |
|  <span data-ttu-id="84283-109">事件源</span><span class="sxs-lookup"><span data-stu-id="84283-109">Event Source</span></span>   |                                        <span data-ttu-id="84283-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="84283-110">ENTSSO</span></span>                                        |
|    <span data-ttu-id="84283-111">组件</span><span class="sxs-lookup"><span data-stu-id="84283-111">Component</span></span>    |                                         <span data-ttu-id="84283-112">N\A</span><span class="sxs-lookup"><span data-stu-id="84283-112">N\A</span></span>                                          |
|  <span data-ttu-id="84283-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="84283-113">Symbolic Name</span></span>  |                              <span data-ttu-id="84283-114">SSO_ERROR_DB_FIRST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="84283-114">SSO_ERROR_DB_FIRST_ACCESS</span></span>                               |
|  <span data-ttu-id="84283-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="84283-115">Message Text</span></span>   | <span data-ttu-id="84283-116">无法与 SSO 数据库取得联系: %1 %r</span><span class="sxs-lookup"><span data-stu-id="84283-116">Failed to contact the SSO database: %1%r</span></span><br /><br /> <span data-ttu-id="84283-117">%2%r</span><span class="sxs-lookup"><span data-stu-id="84283-117">%2%r</span></span><br /><br /> <span data-ttu-id="84283-118">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="84283-118">Error code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="84283-119">解释</span><span class="sxs-lookup"><span data-stu-id="84283-119">Explanation</span></span>  
 <span data-ttu-id="84283-120">此错误事件表示 SSO 服务无法连接到 SSO 数据库启动时。</span><span class="sxs-lookup"><span data-stu-id="84283-120">This Error event indicates that the SSO Service cannot connect to the SSO database when it starts.</span></span> <span data-ttu-id="84283-121">事件消息包含数据源名称 (DSN) 字符串，该值指示指定的 SQL Server 和数据库名称，以及从 SQL 连接库返回的错误消息。</span><span class="sxs-lookup"><span data-stu-id="84283-121">The event message contains the Data Source Name (DSN) string indicating the specified SQL Server and database names as well as the error message that was returned from the SQL connection libraries.</span></span>  

 <span data-ttu-id="84283-122">SSO 服务启动时，它将尝试连接到 SSO 数据库使用在注册表中指定的 SQL Server 和 SSO 数据库名称。</span><span class="sxs-lookup"><span data-stu-id="84283-122">When the SSO Service starts, it will attempt to connect to the SSO database using the SQL Server and SSO database names specified in the registry.</span></span> <span data-ttu-id="84283-123">SSO 服务将尝试连接 12 倍，等待 5 秒每次失败尝试，总共 1 分钟之间。</span><span class="sxs-lookup"><span data-stu-id="84283-123">The SSO Service will attempt to connect 12 times, waiting 5 seconds between each failed attempt, for a total of 1 minute.</span></span>  

## <a name="user-action"></a><span data-ttu-id="84283-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="84283-124">User Action</span></span>  
 <span data-ttu-id="84283-125">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="84283-125">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="84283-126">验证 SQL Server (MSSQLSERVER) 服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="84283-126">Verify the SQL Server (MSSQLSERVER) service is running.</span></span>  

- <span data-ttu-id="84283-127">验证错误消息中指示的数据源名称 (DSN) 字符串正确以及包含正确的 SQL Server 和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="84283-127">Verify the Data Source Name (DSN) string indicated in the error message is correct and contains the correct SQL Server and database names.</span></span>  

  <span data-ttu-id="84283-128">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="84283-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="84283-129">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="84283-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  

- [<span data-ttu-id="84283-130">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="84283-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  

- [<span data-ttu-id="84283-131">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="84283-131">Configuring SSO</span></span>](../core/configuring-sso.md)  

- <span data-ttu-id="84283-132">SQL Server 联机丛书</span><span class="sxs-lookup"><span data-stu-id="84283-132">SQL Server Books Online</span></span>
