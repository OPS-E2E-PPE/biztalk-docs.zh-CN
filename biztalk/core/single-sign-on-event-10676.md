---
title: 单一登录： 事件 10676 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec0e86fb-921d-4505-b458-51b565123ea7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63228e82546e100c81bf01c301d7d9507f147671
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991926"
---
# <a name="single-sign-on-event-10676"></a><span data-ttu-id="189e4-102">单一登录： 事件 10676</span><span class="sxs-lookup"><span data-stu-id="189e4-102">Single Sign-On: Event 10676</span></span>
## <a name="details"></a><span data-ttu-id="189e4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="189e4-103">Details</span></span>  

|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="189e4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="189e4-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="189e4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="189e4-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="189e4-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="189e4-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="189e4-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="189e4-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="189e4-108">10676</span><span class="sxs-lookup"><span data-stu-id="189e4-108">10676</span></span>                                                                                                       |
|  <span data-ttu-id="189e4-109">事件源</span><span class="sxs-lookup"><span data-stu-id="189e4-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="189e4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="189e4-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="189e4-111">组件</span><span class="sxs-lookup"><span data-stu-id="189e4-111">Component</span></span>    |                                                                                                        <span data-ttu-id="189e4-112">N\A</span><span class="sxs-lookup"><span data-stu-id="189e4-112">N\A</span></span>                                                                                                        |
|  <span data-ttu-id="189e4-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="189e4-113">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="189e4-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="189e4-114">SSO_ERROR_REQUIRE_OLD_PASSWORD</span></span>                                                                                           |
|  <span data-ttu-id="189e4-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="189e4-115">Message Text</span></span>   | <span data-ttu-id="189e4-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="189e4-116">External password change.</span></span> <span data-ttu-id="189e4-117">更改外部帐户的密码时，适配器必须提供旧密码。%r</span><span class="sxs-lookup"><span data-stu-id="189e4-117">When changing the password for an external account the adapter must supply the old password.%r</span></span><br /><br /> <span data-ttu-id="189e4-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="189e4-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="189e4-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="189e4-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="189e4-120">外部帐户： %3</span><span class="sxs-lookup"><span data-stu-id="189e4-120">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="189e4-121">解释</span><span class="sxs-lookup"><span data-stu-id="189e4-121">Explanation</span></span>  
 <span data-ttu-id="189e4-122">此错误事件表示密码同步适配器已配置为要求从外部系统，旧密码，但未提供旧密码。</span><span class="sxs-lookup"><span data-stu-id="189e4-122">This Error event indicates that the password sync adapter was configured to expect an old password from the external system, but an old password was not provided.</span></span> <span data-ttu-id="189e4-123">可能是外部系统（外部密码同步适配器）未如预期般配置或工作，或者是密码同步适配器配置不正确。</span><span class="sxs-lookup"><span data-stu-id="189e4-123">Either the external system (the external password sync adapter) is not configured or working as expected or the password sync adapter is incorrectly configured.</span></span> <span data-ttu-id="189e4-124">此错误还可能返回错误代码符号名称 ENTSSO_E_REQUIRE_OLD_PASSWORD。</span><span class="sxs-lookup"><span data-stu-id="189e4-124">This error may also return error code symbolic name ENTSSO_E_REQUIRE_OLD_PASSWORD.</span></span>  

## <a name="user-action"></a><span data-ttu-id="189e4-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="189e4-125">User Action</span></span>  
 <span data-ttu-id="189e4-126">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="189e4-126">To resolve this error, do the following:</span></span>  

-   <span data-ttu-id="189e4-127">使用 SSO 管理工具来设置用户可配置属性**验证旧密码**密码同步适配器选项属性选项卡上。也可以在使用命令行工具 (ssops.exe) 创建适配器时，通过 `verifyOldPassword` 标记名称设置此属性；还可以在使用密码同步适配器向导创建新密码同步适配器时，设置此属性。</span><span class="sxs-lookup"><span data-stu-id="189e4-127">Use the SSO administration tools to set the user configurable property **Verify Old Password** on the Password Sync Adapter Options properties tab. This property can also be set when creating adapters via the command line tools (ssops.exe) with the flag name `verifyOldPassword` and also when creating a new password sync adapter using the Password Sync Adapter wizard.</span></span>  

## <a name="more-info"></a><span data-ttu-id="189e4-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="189e4-128">More info</span></span>

- [<span data-ttu-id="189e4-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="189e4-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="189e4-130">**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="189e4-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
