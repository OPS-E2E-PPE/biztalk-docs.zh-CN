---
title: 单一登录： 事件 10748 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4b18ea-6565-4c0b-89f8-30a8c67601ba
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d83f0bfec0137e0788b55ca6aa5857f3dcfcc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276501"
---
# <a name="single-sign-on-event-10748"></a><span data-ttu-id="8d014-102">单一登录： 事件 10748</span><span class="sxs-lookup"><span data-stu-id="8d014-102">Single Sign-On: Event 10748</span></span>
## <a name="details"></a><span data-ttu-id="8d014-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8d014-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d014-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8d014-104">Product Name</span></span>|<span data-ttu-id="8d014-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8d014-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8d014-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8d014-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8d014-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8d014-107">Event ID</span></span>|<span data-ttu-id="8d014-108">10748</span><span class="sxs-lookup"><span data-stu-id="8d014-108">10748</span></span>|  
|<span data-ttu-id="8d014-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8d014-109">Event Source</span></span>|<span data-ttu-id="8d014-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8d014-110">ENTSSO</span></span>|  
|<span data-ttu-id="8d014-111">组件</span><span class="sxs-lookup"><span data-stu-id="8d014-111">Component</span></span>|<span data-ttu-id="8d014-112">N\A</span><span class="sxs-lookup"><span data-stu-id="8d014-112">N\A</span></span>|  
|<span data-ttu-id="8d014-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8d014-113">Symbolic Name</span></span>|<span data-ttu-id="8d014-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span><span class="sxs-lookup"><span data-stu-id="8d014-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span></span>|  
|<span data-ttu-id="8d014-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8d014-115">Message Text</span></span>|<span data-ttu-id="8d014-116">无法联系目标适配器。</span><span class="sxs-lookup"><span data-stu-id="8d014-116">Could not contact the destination adapter.</span></span><br /><br /> <span data-ttu-id="8d014-117">目标适配器可能无法运行或初始化。%r</span><span class="sxs-lookup"><span data-stu-id="8d014-117">It may not be running or initialized.%r</span></span><br /><br /> <span data-ttu-id="8d014-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8d014-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8d014-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8d014-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="8d014-120">SSO 服务器名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="8d014-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="8d014-121">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="8d014-121">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d014-122">解释</span><span class="sxs-lookup"><span data-stu-id="8d014-122">Explanation</span></span>  
 <span data-ttu-id="8d014-123">此警告事件表明密码同步无法联系指定的密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="8d014-123">This Warning event indicates that Password Synchronization could not contact the specified password sync adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d014-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="8d014-124">User Action</span></span>  
 <span data-ttu-id="8d014-125">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="8d014-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="8d014-126">检查外部适配器。</span><span class="sxs-lookup"><span data-stu-id="8d014-126">Check the external adapter.</span></span>  
  
-   <span data-ttu-id="8d014-127">使用 MMC 管理单元或命令行工具启用适配器。</span><span class="sxs-lookup"><span data-stu-id="8d014-127">Use the MMC Snap-In or command line tools to enable the adapter.</span></span>  
  
-   <span data-ttu-id="8d014-128">检查相关错误的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="8d014-128">Check the system and application event logs for associated errors.</span></span>  
  
 <span data-ttu-id="8d014-129">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="8d014-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="8d014-130">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="8d014-130">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)