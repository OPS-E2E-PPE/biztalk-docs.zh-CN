---
title: 单一登录：Event 10507 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b02d8dfa-7655-471e-84af-e58d08c3cefd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c147e2cbd5beb0e6c07519b35b700aa59b2b00dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398879"
---
# <a name="single-sign-on-event-10507"></a><span data-ttu-id="c20c6-102">单一登录：事件 10507</span><span class="sxs-lookup"><span data-stu-id="c20c6-102">Single Sign-On: Event 10507</span></span>
## <a name="details"></a><span data-ttu-id="c20c6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c20c6-103">Details</span></span>  

|                 |                                                                 |
|-----------------|-----------------------------------------------------------------|
|  <span data-ttu-id="c20c6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c20c6-104">Product Name</span></span>   |                    <span data-ttu-id="c20c6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c20c6-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="c20c6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c20c6-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    <span data-ttu-id="c20c6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c20c6-107">Event ID</span></span>     |                              <span data-ttu-id="c20c6-108">10504</span><span class="sxs-lookup"><span data-stu-id="c20c6-108">10504</span></span>                              |
|  <span data-ttu-id="c20c6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c20c6-109">Event Source</span></span>   |                             <span data-ttu-id="c20c6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c20c6-110">ENTSSO</span></span>                              |
|    <span data-ttu-id="c20c6-111">组件</span><span class="sxs-lookup"><span data-stu-id="c20c6-111">Component</span></span>    |                               <span data-ttu-id="c20c6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c20c6-112">N\A</span></span>                               |
|  <span data-ttu-id="c20c6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c20c6-113">Symbolic Name</span></span>  |                 <span data-ttu-id="c20c6-114">SSO_INFO_SERVICE_INSTALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="c20c6-114">SSO_INFO_SERVICE_INSTALL_FAILED</span></span>                 |
|  <span data-ttu-id="c20c6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c20c6-115">Message Text</span></span>   | <span data-ttu-id="c20c6-116">安装 SSO service.%r 失败</span><span class="sxs-lookup"><span data-stu-id="c20c6-116">Failed to install the SSO service.%r</span></span><br /><br /> <span data-ttu-id="c20c6-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="c20c6-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="c20c6-118">解释</span><span class="sxs-lookup"><span data-stu-id="c20c6-118">Explanation</span></span>  
 <span data-ttu-id="c20c6-119">此事件表示 ENTSSO 服务未能安装。</span><span class="sxs-lookup"><span data-stu-id="c20c6-119">This event indicates that the ENTSSO Service failed to install.</span></span> <span data-ttu-id="c20c6-120">手动安装的企业单一登录过程中才会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="c20c6-120">This event can only occur during a manual installation of Enterprise Single Sign-On.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c20c6-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="c20c6-121">User Action</span></span>  
 <span data-ttu-id="c20c6-122">若要解决此事件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c20c6-122">To resolve this event, do the following:</span></span>  

- <span data-ttu-id="c20c6-123">检查应用程序和系统事件日志中的 ENTSSO 或其他服务的相关错误。</span><span class="sxs-lookup"><span data-stu-id="c20c6-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="c20c6-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="c20c6-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c20c6-125">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="c20c6-125">Installing SSO</span></span>](../core/installing-sso.md)  

- [<span data-ttu-id="c20c6-126">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c20c6-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
