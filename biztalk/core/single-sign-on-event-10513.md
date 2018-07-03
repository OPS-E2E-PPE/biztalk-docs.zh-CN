---
title: 单一登录： 事件 10513 |Microsoft Docs
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
ms.openlocfilehash: c61b1b861cb14ec0d16dce27fd26360df7fcdc98
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981622"
---
# <a name="single-sign-on-event-10513"></a><span data-ttu-id="7dafa-102">单一登录： 事件 10513</span><span class="sxs-lookup"><span data-stu-id="7dafa-102">Single Sign-On: Event 10513</span></span>
## <a name="details"></a><span data-ttu-id="7dafa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7dafa-103">Details</span></span>  

|                 |                                                                                      |
|-----------------|--------------------------------------------------------------------------------------|
|  <span data-ttu-id="7dafa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7dafa-104">Product Name</span></span>   |                              <span data-ttu-id="7dafa-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7dafa-105">Enterprise Single Sign-On</span></span>                               |
| <span data-ttu-id="7dafa-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7dafa-106">Product Version</span></span> |              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    <span data-ttu-id="7dafa-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7dafa-107">Event ID</span></span>     |                                        <span data-ttu-id="7dafa-108">10513</span><span class="sxs-lookup"><span data-stu-id="7dafa-108">10513</span></span>                                         |
|  <span data-ttu-id="7dafa-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7dafa-109">Event Source</span></span>   |                                        <span data-ttu-id="7dafa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7dafa-110">ENTSSO</span></span>                                        |
|    <span data-ttu-id="7dafa-111">组件</span><span class="sxs-lookup"><span data-stu-id="7dafa-111">Component</span></span>    |                                         <span data-ttu-id="7dafa-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7dafa-112">N\A</span></span>                                          |
|  <span data-ttu-id="7dafa-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7dafa-113">Symbolic Name</span></span>  |                              <span data-ttu-id="7dafa-114">SSO_ERROR_DB_FIRST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="7dafa-114">SSO_ERROR_DB_FIRST_ACCESS</span></span>                               |
|  <span data-ttu-id="7dafa-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7dafa-115">Message Text</span></span>   | <span data-ttu-id="7dafa-116">无法与 SSO 数据库取得联系: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7dafa-116">Failed to contact the SSO database: %1%r</span></span><br /><br /> <span data-ttu-id="7dafa-117">%2%r</span><span class="sxs-lookup"><span data-stu-id="7dafa-117">%2%r</span></span><br /><br /> <span data-ttu-id="7dafa-118">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="7dafa-118">Error code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="7dafa-119">解释</span><span class="sxs-lookup"><span data-stu-id="7dafa-119">Explanation</span></span>  
 <span data-ttu-id="7dafa-120">此错误事件表明，SSO 服务在启动时无法连接到 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="7dafa-120">This Error event indicates that the SSO Service cannot connect to the SSO database when it starts.</span></span> <span data-ttu-id="7dafa-121">事件消息包含数据源名称 (DSN) 字符串（表明指定的 SQL Server 和数据库名称），以及从 SQL 连接库返回的错误消息。</span><span class="sxs-lookup"><span data-stu-id="7dafa-121">The event message contains the Data Source Name (DSN) string indicating the specified SQL Server and database names as well as the error message that was returned from the SQL connection libraries.</span></span>  

 <span data-ttu-id="7dafa-122">当 SSO 服务启动时，它将尝试使用在注册表中指定的 SQL Server 和 SSO 数据库名称连接到 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="7dafa-122">When the SSO Service starts, it will attempt to connect to the SSO database using the SQL Server and SSO database names specified in the registry.</span></span> <span data-ttu-id="7dafa-123">SSO 服务将尝试进行 12 次连接，每次尝试失败后再等待 5 秒钟重试，总共 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="7dafa-123">The SSO Service will attempt to connect 12 times, waiting 5 seconds between each failed attempt, for a total of 1 minute.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7dafa-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="7dafa-124">User Action</span></span>  
 <span data-ttu-id="7dafa-125">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="7dafa-125">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="7dafa-126">验证 SQL Server (MSSQLSERVER) 服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="7dafa-126">Verify the SQL Server (MSSQLSERVER) service is running.</span></span>  

- <span data-ttu-id="7dafa-127">验证错误消息中显示的数据源名称 (DSN) 字符串是否正确，以及是否包含正确的 SQL Server 和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="7dafa-127">Verify the Data Source Name (DSN) string indicated in the error message is correct and contains the correct SQL Server and database names.</span></span>  

  <span data-ttu-id="7dafa-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="7dafa-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="7dafa-129">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7dafa-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  

- [<span data-ttu-id="7dafa-130">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="7dafa-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  

- [<span data-ttu-id="7dafa-131">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="7dafa-131">Configuring SSO</span></span>](../core/configuring-sso.md)  

- <span data-ttu-id="7dafa-132">SQL Server 联机丛书</span><span class="sxs-lookup"><span data-stu-id="7dafa-132">SQL Server Books Online</span></span>
