---
title: 单一登录： 事件 10750 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0fdaf2-d429-40b9-adc3-eb134687fb1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32b8c29159edc0cf6fa7281b5a717af509e3a63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276325"
---
# <a name="single-sign-on-event-10750"></a><span data-ttu-id="08dfd-102">单一登录： 事件 10750</span><span class="sxs-lookup"><span data-stu-id="08dfd-102">Single Sign-On: Event 10750</span></span>
## <a name="details"></a><span data-ttu-id="08dfd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="08dfd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08dfd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="08dfd-104">Product Name</span></span>|<span data-ttu-id="08dfd-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="08dfd-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="08dfd-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="08dfd-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="08dfd-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="08dfd-107">Event ID</span></span>|<span data-ttu-id="08dfd-108">10750</span><span class="sxs-lookup"><span data-stu-id="08dfd-108">10750</span></span>|  
|<span data-ttu-id="08dfd-109">事件源</span><span class="sxs-lookup"><span data-stu-id="08dfd-109">Event Source</span></span>|<span data-ttu-id="08dfd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="08dfd-110">ENTSSO</span></span>|  
|<span data-ttu-id="08dfd-111">组件</span><span class="sxs-lookup"><span data-stu-id="08dfd-111">Component</span></span>|<span data-ttu-id="08dfd-112">N\A</span><span class="sxs-lookup"><span data-stu-id="08dfd-112">N\A</span></span>|  
|<span data-ttu-id="08dfd-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="08dfd-113">Symbolic Name</span></span>|<span data-ttu-id="08dfd-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span><span class="sxs-lookup"><span data-stu-id="08dfd-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span></span>|  
|<span data-ttu-id="08dfd-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="08dfd-115">Message Text</span></span>|<span data-ttu-id="08dfd-116">PasswordChangeNotify： 正确的用户名称类型。</span><span class="sxs-lookup"><span data-stu-id="08dfd-116">PasswordChangeNotify: Incorrect User Name Type.</span></span> <span data-ttu-id="08dfd-117">唯一接受的值是 USER_NAME_TYPE_NT4。</span><span class="sxs-lookup"><span data-stu-id="08dfd-117">The only accepted value is USER_NAME_TYPE_NT4.</span></span><br /><br /> <span data-ttu-id="08dfd-118">在 Active Directory.%r 中未正确配置目标</span><span class="sxs-lookup"><span data-stu-id="08dfd-118">The target is incorrectly configured in Active Directory.%r</span></span><br /><br /> <span data-ttu-id="08dfd-119">用户名称类型: %1 %r</span><span class="sxs-lookup"><span data-stu-id="08dfd-119">User Name Type: %1%r</span></span><br /><br /> <span data-ttu-id="08dfd-120">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="08dfd-120">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="08dfd-121">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="08dfd-121">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08dfd-122">解释</span><span class="sxs-lookup"><span data-stu-id="08dfd-122">Explanation</span></span>  
 <span data-ttu-id="08dfd-123">此错误事件表示密码同步接收到了来自密码更改通知服务 (PCNS) 的密码更改，但密码更改的格式错误。</span><span class="sxs-lookup"><span data-stu-id="08dfd-123">This Error event indicates that Password Sync received a password change from the Password Change Notification Service (PCNS), but the password change was in the wrong format.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08dfd-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="08dfd-124">User Action</span></span>  
 <span data-ttu-id="08dfd-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="08dfd-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="08dfd-126">检查 PCNS 配置。</span><span class="sxs-lookup"><span data-stu-id="08dfd-126">Check the PCNS configuration.</span></span> <span data-ttu-id="08dfd-127">PCNS 只能在域控制器上运行。</span><span class="sxs-lookup"><span data-stu-id="08dfd-127">PCNS can run only on a domain controller.</span></span>  
  
-   <span data-ttu-id="08dfd-128">在 Active Directory 中将用户名称类型配置为 USER_NAME_TYPE_NT4。</span><span class="sxs-lookup"><span data-stu-id="08dfd-128">Configure User Name Type to USER_NAME_TYPE_NT4 in Active Directory.</span></span>  
  
 <span data-ttu-id="08dfd-129">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="08dfd-129">For more information, see the following resources:</span></span>  
  
-   <span data-ttu-id="08dfd-130">请参阅 Active Directory 文档，了解有关如何指定用户名称类型的信息。</span><span class="sxs-lookup"><span data-stu-id="08dfd-130">Refer to Active Directory documentation for information on how to specify User Name Type.</span></span>  
  
-   [<span data-ttu-id="08dfd-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="08dfd-131">Password Synchronization</span></span>](../core/password-synchronization2.md)