---
title: 单一登录：Event 10540 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd18184dbf06934600231a6bbb75abdc1709f5ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243407"
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="19cdf-102">单一登录：事件 10540</span><span class="sxs-lookup"><span data-stu-id="19cdf-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="19cdf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="19cdf-103">Details</span></span>  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="19cdf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="19cdf-104">Product Name</span></span>   |                            <span data-ttu-id="19cdf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="19cdf-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="19cdf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="19cdf-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="19cdf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="19cdf-107">Event ID</span></span>     |                                      <span data-ttu-id="19cdf-108">10540</span><span class="sxs-lookup"><span data-stu-id="19cdf-108">10540</span></span>                                       |
|  <span data-ttu-id="19cdf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="19cdf-109">Event Source</span></span>   |                                      <span data-ttu-id="19cdf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="19cdf-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="19cdf-111">组件</span><span class="sxs-lookup"><span data-stu-id="19cdf-111">Component</span></span>    |                                        <span data-ttu-id="19cdf-112">CO</span><span class="sxs-lookup"><span data-stu-id="19cdf-112">CO</span></span>                                        |
|  <span data-ttu-id="19cdf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="19cdf-113">Symbolic Name</span></span>  |                         <span data-ttu-id="19cdf-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="19cdf-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>                         |
|  <span data-ttu-id="19cdf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="19cdf-115">Message Text</span></span>   | <span data-ttu-id="19cdf-116">Application.%r 未启用票证</span><span class="sxs-lookup"><span data-stu-id="19cdf-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="19cdf-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="19cdf-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="19cdf-118">解释</span><span class="sxs-lookup"><span data-stu-id="19cdf-118">Explanation</span></span>  
 <span data-ttu-id="19cdf-119">此警告事件表示票证功能尚未启用此应用程序。</span><span class="sxs-lookup"><span data-stu-id="19cdf-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="19cdf-120">使用 SSO 票证是每个 SSO 应用程序的可选功能。</span><span class="sxs-lookup"><span data-stu-id="19cdf-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="19cdf-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="19cdf-121">User Action</span></span>  
 <span data-ttu-id="19cdf-122">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="19cdf-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="19cdf-123">请联系你的应用程序管理员以启用对此 SSO 应用程序的票证。</span><span class="sxs-lookup"><span data-stu-id="19cdf-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="19cdf-124">这可以使用 SSO 管理工具 （GUI 或命令行）。</span><span class="sxs-lookup"><span data-stu-id="19cdf-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="19cdf-125">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="19cdf-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="19cdf-126">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="19cdf-126">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="19cdf-127">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="19cdf-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="19cdf-128">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="19cdf-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
