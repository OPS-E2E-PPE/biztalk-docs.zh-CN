---
title: 单一登录：Event 10549 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac97f659dfc1f3b152df36c136fc45c3ef4238d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243376"
---
# <a name="single-sign-on-event-10549"></a><span data-ttu-id="048d8-102">单一登录：事件 10549</span><span class="sxs-lookup"><span data-stu-id="048d8-102">Single Sign-On: Event 10549</span></span>
## <a name="details"></a><span data-ttu-id="048d8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="048d8-103">Details</span></span>  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="048d8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="048d8-104">Product Name</span></span>   |                                                                                <span data-ttu-id="048d8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="048d8-105">Enterprise Single Sign-On</span></span>                                                                                 |
| <span data-ttu-id="048d8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="048d8-106">Product Version</span></span> |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    <span data-ttu-id="048d8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="048d8-107">Event ID</span></span>     |                                                                                          <span data-ttu-id="048d8-108">10549</span><span class="sxs-lookup"><span data-stu-id="048d8-108">10549</span></span>                                                                                           |
|  <span data-ttu-id="048d8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="048d8-109">Event Source</span></span>   |                                                                                          <span data-ttu-id="048d8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="048d8-110">ENTSSO</span></span>                                                                                          |
|    <span data-ttu-id="048d8-111">组件</span><span class="sxs-lookup"><span data-stu-id="048d8-111">Component</span></span>    |                                                                                            <span data-ttu-id="048d8-112">CO</span><span class="sxs-lookup"><span data-stu-id="048d8-112">CO</span></span>                                                                                            |
|  <span data-ttu-id="048d8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="048d8-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="048d8-114">SSO_ERROR_CREATE_DATABASE_FAILED</span><span class="sxs-lookup"><span data-stu-id="048d8-114">SSO_ERROR_CREATE_DATABASE_FAILED</span></span>                                                                             |
|  <span data-ttu-id="048d8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="048d8-115">Message Text</span></span>   | <span data-ttu-id="048d8-116">创建和初始化 SSO 数据库 failed.%r</span><span class="sxs-lookup"><span data-stu-id="048d8-116">Creation and initialization of the SSO database failed.%r</span></span><br /><br /> <span data-ttu-id="048d8-117">SQL Server 名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="048d8-117">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="048d8-118">SSO 数据库名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="048d8-118">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="048d8-119">客户端用户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="048d8-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="048d8-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="048d8-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="048d8-121">解释</span><span class="sxs-lookup"><span data-stu-id="048d8-121">Explanation</span></span>  
 <span data-ttu-id="048d8-122">此错误表示创建和初始化 SSO 数据库失败。</span><span class="sxs-lookup"><span data-stu-id="048d8-122">This Error indicates that creation and initialization of the SSO database failed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="048d8-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="048d8-123">User Action</span></span>  
 <span data-ttu-id="048d8-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="048d8-124">To resolve this error do the following:</span></span>  

- <span data-ttu-id="048d8-125">检查系统和应用程序事件日志中的关联消息。</span><span class="sxs-lookup"><span data-stu-id="048d8-125">Check the system and application event logs for associated messages.</span></span>  

- <span data-ttu-id="048d8-126">再次运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="048d8-126">Run Setup again.</span></span>  

  <span data-ttu-id="048d8-127">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="048d8-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="048d8-128">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="048d8-128">Installing SSO</span></span>](../core/installing-sso.md)
