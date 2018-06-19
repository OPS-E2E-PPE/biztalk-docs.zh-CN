---
title: 单一登录： 事件 10718 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4bf86f4db59033b1ee4202c739ffeda43a587e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271781"
---
# <a name="single-sign-on-event-10718"></a><span data-ttu-id="88535-102">单一登录： 事件 10718</span><span class="sxs-lookup"><span data-stu-id="88535-102">Single Sign-On: Event 10718</span></span>
## <a name="details"></a><span data-ttu-id="88535-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="88535-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88535-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="88535-104">Product Name</span></span>|<span data-ttu-id="88535-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="88535-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="88535-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="88535-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="88535-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="88535-107">Event ID</span></span>|<span data-ttu-id="88535-108">10718</span><span class="sxs-lookup"><span data-stu-id="88535-108">10718</span></span>|  
|<span data-ttu-id="88535-109">事件源</span><span class="sxs-lookup"><span data-stu-id="88535-109">Event Source</span></span>|<span data-ttu-id="88535-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="88535-110">ENTSSO</span></span>|  
|<span data-ttu-id="88535-111">组件</span><span class="sxs-lookup"><span data-stu-id="88535-111">Component</span></span>|<span data-ttu-id="88535-112">N\A</span><span class="sxs-lookup"><span data-stu-id="88535-112">N\A</span></span>|  
|<span data-ttu-id="88535-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="88535-113">Symbolic Name</span></span>|<span data-ttu-id="88535-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="88535-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span></span>|  
|<span data-ttu-id="88535-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="88535-115">Message Text</span></span>|<span data-ttu-id="88535-116">重播文件或进度 file.%r 中检测到损坏</span><span class="sxs-lookup"><span data-stu-id="88535-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="88535-117">文件名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="88535-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="88535-118">清除适配器名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="88535-118">Clear Adapter Name: %2%r</span></span><br /><br /> <span data-ttu-id="88535-119">解密的适配器名称： %3</span><span class="sxs-lookup"><span data-stu-id="88535-119">Decrypted Adapter Name: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="88535-120">解释</span><span class="sxs-lookup"><span data-stu-id="88535-120">Explanation</span></span>  
 <span data-ttu-id="88535-121">此错误事件指示在重播文件或进度文件中检测到损坏。</span><span class="sxs-lookup"><span data-stu-id="88535-121">This Error event indicates that corruption was detected in the replay or progress file.</span></span>  
  
 <span data-ttu-id="88535-122">重播文件都存储为特定的密码同步适配器，因此可以为该特定的适配器重放。</span><span class="sxs-lookup"><span data-stu-id="88535-122">A replay file is stored for a particular password sync adapter so it can be played back as that particular adapter.</span></span> <span data-ttu-id="88535-123">适配器名称以明文和加密两种形式存储。</span><span class="sxs-lookup"><span data-stu-id="88535-123">The adapter name is stored in both clear and encrypted forms.</span></span> <span data-ttu-id="88535-124">此消息表示解密重播文件进行播放时，解密的适配器名称与该适配器名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="88535-124">This message indicates that when the replay file was decrypted for playback the decrypted adapter name did not match the adapter name.</span></span> <span data-ttu-id="88535-125">这可以建议已一些损坏或可能篡改重播文件。</span><span class="sxs-lookup"><span data-stu-id="88535-125">This can suggest that there has been some corruption or possible tampering with the replay file.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="88535-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="88535-126">User Action</span></span>  
 <span data-ttu-id="88535-127">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="88535-127">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="88535-128">确定重播文件内容被修改的原因，查看是否存在备份。</span><span class="sxs-lookup"><span data-stu-id="88535-128">Determine why the contents of the replay file might have been modified, see if a backup exists.</span></span>  
  
-   <span data-ttu-id="88535-129">检查是否更改了 SSO 主密钥或 SSO 服务帐户，这可能会影响加密行为。</span><span class="sxs-lookup"><span data-stu-id="88535-129">Check if the SSO master secret was changed or the SSO service account was changed, this could affect encryption behavior.</span></span>  
  
-   <span data-ttu-id="88535-130">删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="88535-130">Delete the replay file.</span></span>  
  
 <span data-ttu-id="88535-131">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="88535-131">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="88535-132">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="88535-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="88535-133">密码同步</span><span class="sxs-lookup"><span data-stu-id="88535-133">Password Synchronization</span></span>](../core/password-synchronization2.md)