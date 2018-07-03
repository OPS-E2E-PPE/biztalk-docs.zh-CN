---
title: 单一登录： 事件 10725 |Microsoft Docs
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
ms.openlocfilehash: 206173f45d6702290eef7cd8e203c2439ce44cc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016135"
---
# <a name="single-sign-on-event-10725"></a><span data-ttu-id="82b4c-102">单一登录： 事件 10725</span><span class="sxs-lookup"><span data-stu-id="82b4c-102">Single Sign-On: Event 10725</span></span>
## <a name="details"></a><span data-ttu-id="82b4c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="82b4c-103">Details</span></span>  

|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="82b4c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="82b4c-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="82b4c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="82b4c-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="82b4c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="82b4c-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="82b4c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="82b4c-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="82b4c-108">10725</span><span class="sxs-lookup"><span data-stu-id="82b4c-108">10725</span></span>                                                                                                  |
|  <span data-ttu-id="82b4c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="82b4c-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="82b4c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="82b4c-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="82b4c-111">组件</span><span class="sxs-lookup"><span data-stu-id="82b4c-111">Component</span></span>    |                                                                                                   <span data-ttu-id="82b4c-112">N\A</span><span class="sxs-lookup"><span data-stu-id="82b4c-112">N\A</span></span>                                                                                                   |
|  <span data-ttu-id="82b4c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="82b4c-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="82b4c-114">SSO_ERROR_REPLAY_SECURITY_3</span><span class="sxs-lookup"><span data-stu-id="82b4c-114">SSO_ERROR_REPLAY_SECURITY_3</span></span>                                                                                       |
|  <span data-ttu-id="82b4c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="82b4c-115">Message Text</span></span>   | <span data-ttu-id="82b4c-116">重播文件目录的安全性与重播或进度文件的安全性不匹配。%r</span><span class="sxs-lookup"><span data-stu-id="82b4c-116">The security on the replay files directory does not match the security on the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="82b4c-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="82b4c-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="82b4c-118">文件安全性: %2 %r</span><span class="sxs-lookup"><span data-stu-id="82b4c-118">File Security: %2%r</span></span><br /><br /> <span data-ttu-id="82b4c-119">目录安全性： %3</span><span class="sxs-lookup"><span data-stu-id="82b4c-119">Directory Security: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="82b4c-120">解释</span><span class="sxs-lookup"><span data-stu-id="82b4c-120">Explanation</span></span>  
 <span data-ttu-id="82b4c-121">此错误事件表明重播文件目录的安全性与重播或进度文件的安全性不匹配。</span><span class="sxs-lookup"><span data-stu-id="82b4c-121">This Error event indicates that the security on the replay files directory does not match the security on the replay or progress file.</span></span>  

 <span data-ttu-id="82b4c-122">重播文件存储在重播文件目录中。</span><span class="sxs-lookup"><span data-stu-id="82b4c-122">Replay files are stored in the replay files directory.</span></span> <span data-ttu-id="82b4c-123">默认情况下，SSO 服务帐户用来创建重播文件和重播文件目录。</span><span class="sxs-lookup"><span data-stu-id="82b4c-123">By default, the SSO service account is used to create both the replay files and the replay files directory.</span></span> <span data-ttu-id="82b4c-124">创建之后，SSO 会验证是否未对重播文件和重播文件目录的安全配置进行更改。</span><span class="sxs-lookup"><span data-stu-id="82b4c-124">SSO verifies that no changes have been made to the security configuration of the replay files and replay files directory since they were created.</span></span> <span data-ttu-id="82b4c-125">如果重播文件目录是使用其他帐户创建的，则当密码同步尝试在该目录中创建重播文件时，可能会返回此错误。</span><span class="sxs-lookup"><span data-stu-id="82b4c-125">If the replay files directory was created with a different account, this error can be returned when Password Sync attempts to create a replay file in that directory.</span></span> <span data-ttu-id="82b4c-126">强烈建议用户不要更改重播文件和重播文件目录的任何安全配置。</span><span class="sxs-lookup"><span data-stu-id="82b4c-126">It is strongly recommended that users not change any security configuration of the replay files and replay files directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="82b4c-127">用户操作</span><span class="sxs-lookup"><span data-stu-id="82b4c-127">User Action</span></span>  
 <span data-ttu-id="82b4c-128">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="82b4c-128">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="82b4c-129">检查用于创建重播文件目录的帐户。</span><span class="sxs-lookup"><span data-stu-id="82b4c-129">Check the account used to create the replay files directory.</span></span> <span data-ttu-id="82b4c-130">如果目录为空，请再次尝试运行密码同步。</span><span class="sxs-lookup"><span data-stu-id="82b4c-130">If the directory is empty, attempt running password sync again.</span></span> <span data-ttu-id="82b4c-131">可能需要使用与 SSO 服务相同的服务帐户来重新创建目录。</span><span class="sxs-lookup"><span data-stu-id="82b4c-131">It may be necessary to re-create the directory using the same service account as the SSO service.</span></span> <span data-ttu-id="82b4c-132">如果无法使用与 SSO 服务相同的帐户重新创建重播文件目录，则检查该帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="82b4c-132">If you cannot re-create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  

  <span data-ttu-id="82b4c-133">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="82b4c-133">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="82b4c-134">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="82b4c-134">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="82b4c-135">密码同步</span><span class="sxs-lookup"><span data-stu-id="82b4c-135">Password Synchronization</span></span>](../core/password-synchronization2.md)
