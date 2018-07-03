---
title: 单一登录： 事件 10540 |Microsoft Docs
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
ms.openlocfilehash: b1bcd7cc64a79634aa7868791d7e74e92cd1c4a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990942"
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="091a5-102">单一登录： 事件 10540</span><span class="sxs-lookup"><span data-stu-id="091a5-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="091a5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="091a5-103">Details</span></span>  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="091a5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="091a5-104">Product Name</span></span>   |                            <span data-ttu-id="091a5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="091a5-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="091a5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="091a5-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="091a5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="091a5-107">Event ID</span></span>     |                                      <span data-ttu-id="091a5-108">10540</span><span class="sxs-lookup"><span data-stu-id="091a5-108">10540</span></span>                                       |
|  <span data-ttu-id="091a5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="091a5-109">Event Source</span></span>   |                                      <span data-ttu-id="091a5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="091a5-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="091a5-111">组件</span><span class="sxs-lookup"><span data-stu-id="091a5-111">Component</span></span>    |                                        <span data-ttu-id="091a5-112">CO</span><span class="sxs-lookup"><span data-stu-id="091a5-112">CO</span></span>                                        |
|  <span data-ttu-id="091a5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="091a5-113">Symbolic Name</span></span>  |                         <span data-ttu-id="091a5-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="091a5-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>                         |
|  <span data-ttu-id="091a5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="091a5-115">Message Text</span></span>   | <span data-ttu-id="091a5-116">此应用程序未启用票证。%r</span><span class="sxs-lookup"><span data-stu-id="091a5-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="091a5-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="091a5-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="091a5-118">解释</span><span class="sxs-lookup"><span data-stu-id="091a5-118">Explanation</span></span>  
 <span data-ttu-id="091a5-119">此警告事件表示，此应用程序未启用票证功能。</span><span class="sxs-lookup"><span data-stu-id="091a5-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="091a5-120">使用 SSO 票证是每个 SSO 应用程序的可选功能。</span><span class="sxs-lookup"><span data-stu-id="091a5-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="091a5-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="091a5-121">User Action</span></span>  
 <span data-ttu-id="091a5-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="091a5-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="091a5-123">与应用程序管理员联系，为此 SSO 应用程序启用票证。</span><span class="sxs-lookup"><span data-stu-id="091a5-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="091a5-124">可使用 SSO 管理工具（GUI 或命令行）完成此操作。</span><span class="sxs-lookup"><span data-stu-id="091a5-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="091a5-125">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="091a5-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="091a5-126">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="091a5-126">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="091a5-127">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="091a5-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="091a5-128">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="091a5-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
