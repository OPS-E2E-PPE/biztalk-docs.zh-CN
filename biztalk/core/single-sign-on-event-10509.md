---
title: 单一登录： 事件 10509 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906823f-db3f-45fc-bf61-cbe6a9566bd7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4d61cbb7af195aa88c36b64149366334c835b80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270349"
---
# <a name="single-sign-on-event-10509"></a><span data-ttu-id="490a1-102">单一登录： 事件 10509</span><span class="sxs-lookup"><span data-stu-id="490a1-102">Single Sign-On: Event 10509</span></span>
## <a name="details"></a><span data-ttu-id="490a1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="490a1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="490a1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="490a1-104">Product Name</span></span>|<span data-ttu-id="490a1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="490a1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="490a1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="490a1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="490a1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="490a1-107">Event ID</span></span>|<span data-ttu-id="490a1-108">10509</span><span class="sxs-lookup"><span data-stu-id="490a1-108">10509</span></span>|  
|<span data-ttu-id="490a1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="490a1-109">Event Source</span></span>|<span data-ttu-id="490a1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="490a1-110">ENTSSO</span></span>|  
|<span data-ttu-id="490a1-111">组件</span><span class="sxs-lookup"><span data-stu-id="490a1-111">Component</span></span>|<span data-ttu-id="490a1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="490a1-112">N\A</span></span>|  
|<span data-ttu-id="490a1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="490a1-113">Symbolic Name</span></span>|<span data-ttu-id="490a1-114">SSO_INFO_SERVICE_REMOVE_FAILED</span><span class="sxs-lookup"><span data-stu-id="490a1-114">SSO_INFO_SERVICE_REMOVE_FAILED</span></span>|  
|<span data-ttu-id="490a1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="490a1-115">Message Text</span></span>|<span data-ttu-id="490a1-116">无法删除 SSO 服务。%r</span><span class="sxs-lookup"><span data-stu-id="490a1-116">Failed to remove the SSO service.%r</span></span><br /><br /> <span data-ttu-id="490a1-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="490a1-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="490a1-118">解释</span><span class="sxs-lookup"><span data-stu-id="490a1-118">Explanation</span></span>  
 <span data-ttu-id="490a1-119">此事件表示无法卸载 ENTSSO 服务。</span><span class="sxs-lookup"><span data-stu-id="490a1-119">This event indicates that the ENTSSO Service failed to uninstall.</span></span> <span data-ttu-id="490a1-120">只有在手动卸载企业单一登录时，才会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="490a1-120">This event can only occur during a manual uninstallation of Enterprise Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="490a1-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="490a1-121">User Action</span></span>  
 <span data-ttu-id="490a1-122">若要解决此事件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="490a1-122">To resolve this event, do the following:</span></span>  
  
-   <span data-ttu-id="490a1-123">检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。</span><span class="sxs-lookup"><span data-stu-id="490a1-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="490a1-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="490a1-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="490a1-125">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="490a1-125">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="490a1-126">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="490a1-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)