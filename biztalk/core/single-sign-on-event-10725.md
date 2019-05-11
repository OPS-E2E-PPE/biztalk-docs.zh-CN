---
title: 单一登录：Event 10725 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89218d73-bda0-4e98-a578-cd244af79041
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b47a3a9ac9c9537515dc2baf3affe6e4a729bb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267558"
---
# <a name="single-sign-on-event-10725"></a><span data-ttu-id="f0913-102">单一登录：事件 10725</span><span class="sxs-lookup"><span data-stu-id="f0913-102">Single Sign-On: Event 10725</span></span>
## <a name="details"></a><span data-ttu-id="f0913-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f0913-103">Details</span></span>  

|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f0913-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f0913-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="f0913-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f0913-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="f0913-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f0913-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="f0913-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f0913-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="f0913-108">10725</span><span class="sxs-lookup"><span data-stu-id="f0913-108">10725</span></span>                                                                                                  |
|  <span data-ttu-id="f0913-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f0913-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="f0913-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f0913-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="f0913-111">组件</span><span class="sxs-lookup"><span data-stu-id="f0913-111">Component</span></span>    |                                                                                                   <span data-ttu-id="f0913-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f0913-112">N\A</span></span>                                                                                                   |
|  <span data-ttu-id="f0913-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f0913-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="f0913-114">SSO_ERROR_REPLAY_SECURITY_3</span><span class="sxs-lookup"><span data-stu-id="f0913-114">SSO_ERROR_REPLAY_SECURITY_3</span></span>                                                                                       |
|  <span data-ttu-id="f0913-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f0913-115">Message Text</span></span>   | <span data-ttu-id="f0913-116">重播文件目录的安全性与重播或进度 file.%r 的安全性不匹配</span><span class="sxs-lookup"><span data-stu-id="f0913-116">The security on the replay files directory does not match the security on the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="f0913-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f0913-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="f0913-118">文件安全性: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f0913-118">File Security: %2%r</span></span><br /><br /> <span data-ttu-id="f0913-119">目录安全性： %3</span><span class="sxs-lookup"><span data-stu-id="f0913-119">Directory Security: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="f0913-120">解释</span><span class="sxs-lookup"><span data-stu-id="f0913-120">Explanation</span></span>  
 <span data-ttu-id="f0913-121">此错误事件表明重播文件目录的安全性与重播或进度文件的安全性不匹配。</span><span class="sxs-lookup"><span data-stu-id="f0913-121">This Error event indicates that the security on the replay files directory does not match the security on the replay or progress file.</span></span>  

 <span data-ttu-id="f0913-122">重播文件存储在重播文件目录。</span><span class="sxs-lookup"><span data-stu-id="f0913-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="f0913-123">默认情况下，SSO 服务帐户用于创建重播文件和重播文件目录。</span><span class="sxs-lookup"><span data-stu-id="f0913-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="f0913-124">没有进行了更改的安全配置的重播文件和重播文件目录创建以来，SSO 会验证。</span><span class="sxs-lookup"><span data-stu-id="f0913-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="f0913-125">如果在不同帐户创建重播文件目录时，密码同步尝试在该目录中创建重播文件时，可以返回此错误。</span><span class="sxs-lookup"><span data-stu-id="f0913-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="f0913-126">强烈建议用户不要更改重播文件和重播文件目录的任何安全配置。</span><span class="sxs-lookup"><span data-stu-id="f0913-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f0913-127">用户操作</span><span class="sxs-lookup"><span data-stu-id="f0913-127">User Action</span></span>  
 <span data-ttu-id="f0913-128">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f0913-128">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="f0913-129">检查用来创建重播文件目录的帐户。</span><span class="sxs-lookup"><span data-stu-id="f0913-129">Check the account used to create the replay files directory.</span></span> <span data-ttu-id="f0913-130">如果该目录为空，则尝试再次运行密码同步。</span><span class="sxs-lookup"><span data-stu-id="f0913-130">If the directory is empty, attempt running password sync again.</span></span> <span data-ttu-id="f0913-131">可能需要重新创建使用与 SSO 服务相同的服务帐户的目录。</span><span class="sxs-lookup"><span data-stu-id="f0913-131">It may be necessary to re-create the directory using the same service account as the SSO service.</span></span> <span data-ttu-id="f0913-132">如果无法重新创建重播文件目录使用与 SSO 服务相同的帐户，检查该帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="f0913-132">If you cannot re-create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  

  <span data-ttu-id="f0913-133">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="f0913-133">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="f0913-134">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="f0913-134">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f0913-135">密码同步</span><span class="sxs-lookup"><span data-stu-id="f0913-135">Password Synchronization</span></span>](../core/password-synchronization2.md)
