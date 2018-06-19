---
title: 单一登录： 事件 10724 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd9e65b18b66f119e3cc2acf7f078f17466e46b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271829"
---
# <a name="single-sign-on-event-10724"></a><span data-ttu-id="0f0c1-102">单一登录： 事件 10724</span><span class="sxs-lookup"><span data-stu-id="0f0c1-102">Single Sign-On: Event 10724</span></span>
## <a name="details"></a><span data-ttu-id="0f0c1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0f0c1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f0c1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0f0c1-104">Product Name</span></span>|<span data-ttu-id="0f0c1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0f0c1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0f0c1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0f0c1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0f0c1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0f0c1-107">Event ID</span></span>|<span data-ttu-id="0f0c1-108">10724</span><span class="sxs-lookup"><span data-stu-id="0f0c1-108">10724</span></span>|  
|<span data-ttu-id="0f0c1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0f0c1-109">Event Source</span></span>|<span data-ttu-id="0f0c1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0f0c1-110">ENTSSO</span></span>|  
|<span data-ttu-id="0f0c1-111">组件</span><span class="sxs-lookup"><span data-stu-id="0f0c1-111">Component</span></span>|<span data-ttu-id="0f0c1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0f0c1-112">N\A</span></span>|  
|<span data-ttu-id="0f0c1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0f0c1-113">Symbolic Name</span></span>|<span data-ttu-id="0f0c1-114">SSO_ERROR_REPLAY_SECURITY_2</span><span class="sxs-lookup"><span data-stu-id="0f0c1-114">SSO_ERROR_REPLAY_SECURITY_2</span></span>|  
|<span data-ttu-id="0f0c1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0f0c1-115">Message Text</span></span>|<span data-ttu-id="0f0c1-116">已经对重播或进度文件的初始安全值进行了更改。%r</span><span class="sxs-lookup"><span data-stu-id="0f0c1-116">The security on the replay or progress file has been changed from its original value.%r</span></span><br /><br /> <span data-ttu-id="0f0c1-117">文件名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0f0c1-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="0f0c1-118">当前文件安全性: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0f0c1-118">Current File Security: %2%r</span></span><br /><br /> <span data-ttu-id="0f0c1-119">原始文件安全性： %3</span><span class="sxs-lookup"><span data-stu-id="0f0c1-119">Original File Security: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0f0c1-120">解释</span><span class="sxs-lookup"><span data-stu-id="0f0c1-120">Explanation</span></span>  
 <span data-ttu-id="0f0c1-121">此错误事件指示在重播文件或进度文件安全性已被更改。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-121">This Error event indicates that the security on the replay or progress files has been changed.</span></span>  
  
 <span data-ttu-id="0f0c1-122">重播文件存储在重播文件目录中。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="0f0c1-123">默认情况下，SSO 服务帐户用来创建重播文件和重播文件目录。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="0f0c1-124">创建之后，SSO 会验证是否未对重播文件和重播文件目录的安全配置进行更改。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="0f0c1-125">如果重播文件目录是使用其他帐户创建的，则当密码同步尝试在该目录中创建重播文件时，可能会返回此错误。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="0f0c1-126">强烈建议用户不要更改重播文件和重播文件目录的任何安全配置。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f0c1-127">用户操作</span><span class="sxs-lookup"><span data-stu-id="0f0c1-127">User Action</span></span>  
 <span data-ttu-id="0f0c1-128">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0f0c1-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="0f0c1-129">检查用来创建重播文件的帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-129">Check permission for the account used to create the replay files.</span></span> <span data-ttu-id="0f0c1-130">这通常是 SSO 系统帐户。</span><span class="sxs-lookup"><span data-stu-id="0f0c1-130">This is typically the SSO system account.</span></span>  
  
 <span data-ttu-id="0f0c1-131">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="0f0c1-131">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="0f0c1-132">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="0f0c1-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="0f0c1-133">密码同步</span><span class="sxs-lookup"><span data-stu-id="0f0c1-133">Password Synchronization</span></span>](../core/password-synchronization2.md)