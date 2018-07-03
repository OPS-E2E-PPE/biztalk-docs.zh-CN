---
title: 单一登录： 事件 10820 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b566c4dfe4437017b743228c9bae2631c79a00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011654"
---
# <a name="single-sign-on-event-10820"></a><span data-ttu-id="282bf-102">单一登录： 事件 10820</span><span class="sxs-lookup"><span data-stu-id="282bf-102">Single Sign-On: Event 10820</span></span>
## <a name="details"></a><span data-ttu-id="282bf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="282bf-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="282bf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="282bf-104">Product Name</span></span>   |                                  <span data-ttu-id="282bf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="282bf-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="282bf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="282bf-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="282bf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="282bf-107">Event ID</span></span>     |                                            <span data-ttu-id="282bf-108">10820</span><span class="sxs-lookup"><span data-stu-id="282bf-108">10820</span></span>                                             |
|  <span data-ttu-id="282bf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="282bf-109">Event Source</span></span>   |                                            <span data-ttu-id="282bf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="282bf-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="282bf-111">组件</span><span class="sxs-lookup"><span data-stu-id="282bf-111">Component</span></span>    |                                             <span data-ttu-id="282bf-112">N/A</span><span class="sxs-lookup"><span data-stu-id="282bf-112">N/A</span></span>                                              |
|  <span data-ttu-id="282bf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="282bf-113">Symbolic Name</span></span>  |                                <span data-ttu-id="282bf-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="282bf-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span></span>                                 |
|  <span data-ttu-id="282bf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="282bf-115">Message Text</span></span>   | <span data-ttu-id="282bf-116">为外部帐户更改密码时，适配器必须提供旧密码。</span><span class="sxs-lookup"><span data-stu-id="282bf-116">When changing the password for an external account the adapter must supply the old password.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="282bf-117">解释</span><span class="sxs-lookup"><span data-stu-id="282bf-117">Explanation</span></span>  
 <span data-ttu-id="282bf-118">此应用程序配置为需要密码同步适配器提供旧密码。</span><span class="sxs-lookup"><span data-stu-id="282bf-118">This application is configured in such a way that the password sync adapter is required to supply the old password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="282bf-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="282bf-119">User Action</span></span>  
 <span data-ttu-id="282bf-120">检查密码同步适配器的配置。</span><span class="sxs-lookup"><span data-stu-id="282bf-120">Check the configuration of your password sync adapter.</span></span>