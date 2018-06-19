---
title: 单一登录： 事件 10705 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81456bdd-dfd8-4483-aa76-5ec72350cc70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41db0b3aeba4e3c71da3193af807f881bb4ae586
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271069"
---
# <a name="single-sign-on-event-10705"></a><span data-ttu-id="caad7-102">单一登录： 事件 10705</span><span class="sxs-lookup"><span data-stu-id="caad7-102">Single Sign-On: Event 10705</span></span>
## <a name="details"></a><span data-ttu-id="caad7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="caad7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="caad7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="caad7-104">Product Name</span></span>|<span data-ttu-id="caad7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="caad7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="caad7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="caad7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="caad7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="caad7-107">Event ID</span></span>|<span data-ttu-id="caad7-108">10705</span><span class="sxs-lookup"><span data-stu-id="caad7-108">10705</span></span>|  
|<span data-ttu-id="caad7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="caad7-109">Event Source</span></span>|<span data-ttu-id="caad7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="caad7-110">ENTSSO</span></span>|  
|<span data-ttu-id="caad7-111">组件</span><span class="sxs-lookup"><span data-stu-id="caad7-111">Component</span></span>|<span data-ttu-id="caad7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="caad7-112">N\A</span></span>|  
|<span data-ttu-id="caad7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="caad7-113">Symbolic Name</span></span>|<span data-ttu-id="caad7-114">SSO_WARN_PS_NOT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="caad7-114">SSO_WARN_PS_NOT_ADAPTER</span></span>|  
|<span data-ttu-id="caad7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="caad7-115">Message Text</span></span>|<span data-ttu-id="caad7-116">指定的适配器不是适配器应用程序。</span><span class="sxs-lookup"><span data-stu-id="caad7-116">The specified adapter is not an adapter application.</span></span> <span data-ttu-id="caad7-117">检查应用程序类型。%r</span><span class="sxs-lookup"><span data-stu-id="caad7-117">Check the application type.%r</span></span><br /><br /> <span data-ttu-id="caad7-118">适配器： %1</span><span class="sxs-lookup"><span data-stu-id="caad7-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="caad7-119">解释</span><span class="sxs-lookup"><span data-stu-id="caad7-119">Explanation</span></span>  
 <span data-ttu-id="caad7-120">此警告事件表明，指定的适配器不是适配器应用程序。</span><span class="sxs-lookup"><span data-stu-id="caad7-120">This Warning event indicates that the specified adapter is not an adapter application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="caad7-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="caad7-121">User Action</span></span>  
 <span data-ttu-id="caad7-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="caad7-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="caad7-123">使用 SSO Admin MMC 管理单元，右键单击指定的适配器，然后单击“属性”以确定应用程序类型，或者使用命令行工具 ssops -list and ssops -display 来确定应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="caad7-123">Use the SSO Admin MMC Snap-In, right click the specified adapter, and then click Properties to determine the application type or use the command line tool  ssops -list and ssops -display to determine the application type.</span></span>  
  
-   <span data-ttu-id="caad7-124">使用 SSO Admin MMC 管理单元或 ssops-addapp 设置适配器应用程序。</span><span class="sxs-lookup"><span data-stu-id="caad7-124">Use the SSO Admin MMC Snap-In or ssops -addapp to set the adapter application.</span></span>  
  
 <span data-ttu-id="caad7-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="caad7-125">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="caad7-126">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="caad7-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)