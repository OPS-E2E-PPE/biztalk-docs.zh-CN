---
title: 单一登录：Event 10538 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d1a1b8b09d9bc4725c55060aebe705f256e691
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250381"
---
# <a name="single-sign-on-event-10538"></a><span data-ttu-id="afd03-102">单一登录：事件 10538</span><span class="sxs-lookup"><span data-stu-id="afd03-102">Single Sign-On: Event 10538</span></span>
## <a name="details"></a><span data-ttu-id="afd03-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="afd03-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="afd03-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="afd03-104">Product Name</span></span>   |                         <span data-ttu-id="afd03-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="afd03-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="afd03-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="afd03-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="afd03-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="afd03-107">Event ID</span></span>     |                                   <span data-ttu-id="afd03-108">10538</span><span class="sxs-lookup"><span data-stu-id="afd03-108">10538</span></span>                                   |
|  <span data-ttu-id="afd03-109">事件源</span><span class="sxs-lookup"><span data-stu-id="afd03-109">Event Source</span></span>   |                                  <span data-ttu-id="afd03-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="afd03-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="afd03-111">组件</span><span class="sxs-lookup"><span data-stu-id="afd03-111">Component</span></span>    |                                    <span data-ttu-id="afd03-112">CO</span><span class="sxs-lookup"><span data-stu-id="afd03-112">CO</span></span>                                     |
|  <span data-ttu-id="afd03-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="afd03-113">Symbolic Name</span></span>  |                           <span data-ttu-id="afd03-114">SSO_WARN_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="afd03-114">SSO_WARN_APP_DISABLED</span></span>                           |
|  <span data-ttu-id="afd03-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="afd03-115">Message Text</span></span>   | <span data-ttu-id="afd03-116">应用程序当前被 disabled.%r</span><span class="sxs-lookup"><span data-stu-id="afd03-116">The application is currently disabled.%r</span></span><br /><br /> <span data-ttu-id="afd03-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="afd03-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="afd03-118">解释</span><span class="sxs-lookup"><span data-stu-id="afd03-118">Explanation</span></span>  
 <span data-ttu-id="afd03-119">此警告事件表明 SSO 关联应用程序已禁用了由应用程序管理员。</span><span class="sxs-lookup"><span data-stu-id="afd03-119">This Warning event indicates that the SSO affiliate application has been disabled by an Application Administrator.</span></span>  

## <a name="user-action"></a><span data-ttu-id="afd03-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="afd03-120">User Action</span></span>  
 <span data-ttu-id="afd03-121">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="afd03-121">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="afd03-122">请联系你的应用程序管理员联系以启用 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="afd03-122">Contact your Application Administrator to enable the SSO affiliate application.</span></span> <span data-ttu-id="afd03-123">这可以使用 SSO 管理工具 （GUI 或命令行）。</span><span class="sxs-lookup"><span data-stu-id="afd03-123">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="afd03-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="afd03-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="afd03-125">如何启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="afd03-125">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="afd03-126">如何禁用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="afd03-126">How to Disable an Affiliate Application</span></span>](../core/how-to-disable-an-affiliate-application.md)
