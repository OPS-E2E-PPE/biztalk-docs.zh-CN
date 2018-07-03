---
title: 单一登录： 事件 10718 |Microsoft Docs
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
ms.openlocfilehash: 958753d50d15662cd138ea5460c121eefcac8a98
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004982"
---
# <a name="single-sign-on-event-10718"></a><span data-ttu-id="78b14-102">单一登录： 事件 10718</span><span class="sxs-lookup"><span data-stu-id="78b14-102">Single Sign-On: Event 10718</span></span>
## <a name="details"></a><span data-ttu-id="78b14-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="78b14-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="78b14-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="78b14-104">Product Name</span></span>   |                                                                     <span data-ttu-id="78b14-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="78b14-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="78b14-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="78b14-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="78b14-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="78b14-107">Event ID</span></span>     |                                                                               <span data-ttu-id="78b14-108">10718</span><span class="sxs-lookup"><span data-stu-id="78b14-108">10718</span></span>                                                                               |
|  <span data-ttu-id="78b14-109">事件源</span><span class="sxs-lookup"><span data-stu-id="78b14-109">Event Source</span></span>   |                                                                              <span data-ttu-id="78b14-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="78b14-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="78b14-111">组件</span><span class="sxs-lookup"><span data-stu-id="78b14-111">Component</span></span>    |                                                                                <span data-ttu-id="78b14-112">N\A</span><span class="sxs-lookup"><span data-stu-id="78b14-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="78b14-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="78b14-113">Symbolic Name</span></span>  |                                                                <span data-ttu-id="78b14-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="78b14-114">SSO_ERROR_REPLAY_INCORRECT_ADAPTER</span></span>                                                                 |
|  <span data-ttu-id="78b14-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="78b14-115">Message Text</span></span>   | <span data-ttu-id="78b14-116">在重播或进度 file.%r 中检测到损坏。</span><span class="sxs-lookup"><span data-stu-id="78b14-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="78b14-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="78b14-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="78b14-118">清除适配器名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="78b14-118">Clear Adapter Name: %2%r</span></span><br /><br /> <span data-ttu-id="78b14-119">解密适配器名称： %3</span><span class="sxs-lookup"><span data-stu-id="78b14-119">Decrypted Adapter Name: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="78b14-120">解释</span><span class="sxs-lookup"><span data-stu-id="78b14-120">Explanation</span></span>  
 <span data-ttu-id="78b14-121">此错误事件表明重播或进度文件中检测到损坏。</span><span class="sxs-lookup"><span data-stu-id="78b14-121">This Error event indicates that corruption was detected in the replay or progress file.</span></span>  

 <span data-ttu-id="78b14-122">重播文件存储特定的密码同步适配器，因此可以为该特定适配器重放。</span><span class="sxs-lookup"><span data-stu-id="78b14-122">A replay file is stored for a particular password sync adapter so it can be played back as that particular adapter.</span></span> <span data-ttu-id="78b14-123">适配器名称以明文和加密两种形式存储。</span><span class="sxs-lookup"><span data-stu-id="78b14-123">The adapter name is stored in both clear and encrypted forms.</span></span> <span data-ttu-id="78b14-124">此消息表示解密重播文件进行播放时，解密的适配器名称与该适配器名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="78b14-124">This message indicates that when the replay file was decrypted for playback the decrypted adapter name did not match the adapter name.</span></span> <span data-ttu-id="78b14-125">这可以建议发生了一些损坏或与重播文件可能被篡改。</span><span class="sxs-lookup"><span data-stu-id="78b14-125">This can suggest that there has been some corruption or possible tampering with the replay file.</span></span>  

## <a name="user-action"></a><span data-ttu-id="78b14-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="78b14-126">User Action</span></span>  
 <span data-ttu-id="78b14-127">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="78b14-127">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="78b14-128">确定重播文件内容被修改的原因，查看是否存在备份。</span><span class="sxs-lookup"><span data-stu-id="78b14-128">Determine why the contents of the replay file might have been modified, see if a backup exists.</span></span>  

- <span data-ttu-id="78b14-129">检查是否更改了 SSO 主密钥或 SSO 服务帐户，这可能会影响加密行为。</span><span class="sxs-lookup"><span data-stu-id="78b14-129">Check if the SSO master secret was changed or the SSO service account was changed, this could affect encryption behavior.</span></span>  

- <span data-ttu-id="78b14-130">删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="78b14-130">Delete the replay file.</span></span>  

  <span data-ttu-id="78b14-131">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="78b14-131">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="78b14-132">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="78b14-132">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="78b14-133">密码同步</span><span class="sxs-lookup"><span data-stu-id="78b14-133">Password Synchronization</span></span>](../core/password-synchronization2.md)
