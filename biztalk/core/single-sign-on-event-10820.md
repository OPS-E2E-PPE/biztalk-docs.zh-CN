---
title: "单一登录： 事件 10820 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a3ae1be84ca0b936fe38463e51e6385071f7a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10820"></a><span data-ttu-id="51a3d-102">单一登录： 事件 10820</span><span class="sxs-lookup"><span data-stu-id="51a3d-102">Single Sign-On: Event 10820</span></span>
## <a name="details"></a><span data-ttu-id="51a3d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="51a3d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51a3d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="51a3d-104">Product Name</span></span>|<span data-ttu-id="51a3d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="51a3d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="51a3d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="51a3d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="51a3d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="51a3d-107">Event ID</span></span>|<span data-ttu-id="51a3d-108">10820</span><span class="sxs-lookup"><span data-stu-id="51a3d-108">10820</span></span>|  
|<span data-ttu-id="51a3d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="51a3d-109">Event Source</span></span>|<span data-ttu-id="51a3d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="51a3d-110">ENTSSO</span></span>|  
|<span data-ttu-id="51a3d-111">组件</span><span class="sxs-lookup"><span data-stu-id="51a3d-111">Component</span></span>|<span data-ttu-id="51a3d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="51a3d-112">N/A</span></span>|  
|<span data-ttu-id="51a3d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="51a3d-113">Symbolic Name</span></span>|<span data-ttu-id="51a3d-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="51a3d-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span></span>|  
|<span data-ttu-id="51a3d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="51a3d-115">Message Text</span></span>|<span data-ttu-id="51a3d-116">为外部帐户更改密码时，适配器必须提供旧密码。</span><span class="sxs-lookup"><span data-stu-id="51a3d-116">When changing the password for an external account the adapter must supply the old password.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="51a3d-117">解释</span><span class="sxs-lookup"><span data-stu-id="51a3d-117">Explanation</span></span>  
 <span data-ttu-id="51a3d-118">此应用程序配置为需要密码同步适配器提供旧密码。</span><span class="sxs-lookup"><span data-stu-id="51a3d-118">This application is configured in such a way that the password sync adapter is required to supply the old password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="51a3d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="51a3d-119">User Action</span></span>  
 <span data-ttu-id="51a3d-120">检查密码同步适配器的配置。</span><span class="sxs-lookup"><span data-stu-id="51a3d-120">Check the configuration of your password sync adapter.</span></span>