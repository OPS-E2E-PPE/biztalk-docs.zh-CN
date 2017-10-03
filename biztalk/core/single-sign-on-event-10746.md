---
title: "单一登录： 事件 10746 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc2bc096211d8a90089b3b5fdd31b4dbb82f2b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10746"></a><span data-ttu-id="0ef46-102">单一登录： 事件 10746</span><span class="sxs-lookup"><span data-stu-id="0ef46-102">Single Sign-On: Event 10746</span></span>
## <a name="details"></a><span data-ttu-id="0ef46-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0ef46-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ef46-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0ef46-104">Product Name</span></span>|<span data-ttu-id="0ef46-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0ef46-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0ef46-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0ef46-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0ef46-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0ef46-107">Event ID</span></span>|<span data-ttu-id="0ef46-108">10746</span><span class="sxs-lookup"><span data-stu-id="0ef46-108">10746</span></span>|  
|<span data-ttu-id="0ef46-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0ef46-109">Event Source</span></span>|<span data-ttu-id="0ef46-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0ef46-110">ENTSSO</span></span>|  
|<span data-ttu-id="0ef46-111">组件</span><span class="sxs-lookup"><span data-stu-id="0ef46-111">Component</span></span>|<span data-ttu-id="0ef46-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0ef46-112">N\A</span></span>|  
|<span data-ttu-id="0ef46-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0ef46-113">Symbolic Name</span></span>|<span data-ttu-id="0ef46-114">SSO_WARN_PASSWORD_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="0ef46-114">SSO_WARN_PASSWORD_EXPIRED</span></span>|  
|<span data-ttu-id="0ef46-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0ef46-115">Message Text</span></span>|<span data-ttu-id="0ef46-116">外部帐户密码已过期。%r</span><span class="sxs-lookup"><span data-stu-id="0ef46-116">The password for the external account has expired.%r</span></span><br /><br /> <span data-ttu-id="0ef46-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0ef46-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0ef46-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0ef46-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="0ef46-119">外部帐户： %3</span><span class="sxs-lookup"><span data-stu-id="0ef46-119">External Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ef46-120">解释</span><span class="sxs-lookup"><span data-stu-id="0ef46-120">Explanation</span></span>  
 <span data-ttu-id="0ef46-121">此警告事件表明外部帐户的密码已过期。</span><span class="sxs-lookup"><span data-stu-id="0ef46-121">This Warning event indicates that the password for the external account has expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ef46-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="0ef46-122">User Action</span></span>  
 <span data-ttu-id="0ef46-123">若要解决此警告，请检查系统和应用程序事件日志中的关联的错误。</span><span class="sxs-lookup"><span data-stu-id="0ef46-123">To resolve this warning, check the system and application event logs for associated errors.</span></span>    

## <a name="more-info"></a><span data-ttu-id="0ef46-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="0ef46-124">More info</span></span>
<span data-ttu-id="0ef46-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="0ef46-125">For more information, see the following resources:</span></span>  
  
-   <span data-ttu-id="0ef46-126">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0ef46-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
  
-   [<span data-ttu-id="0ef46-127">密码同步</span><span class="sxs-lookup"><span data-stu-id="0ef46-127">Password Synchronization</span></span>](../core/password-synchronization2.md)