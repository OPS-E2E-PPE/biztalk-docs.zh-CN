---
title: 单一登录： 事件 10856 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10c06a86-e402-4adc-abbe-5ded923d626a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6be0f098929e0419378de9eaebdf0ca00f5eb421
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276341"
---
# <a name="single-sign-on-event-10856"></a><span data-ttu-id="bdc0d-102">单一登录： 事件 10856</span><span class="sxs-lookup"><span data-stu-id="bdc0d-102">Single Sign-On: Event 10856</span></span>
## <a name="details"></a><span data-ttu-id="bdc0d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bdc0d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bdc0d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bdc0d-104">Product Name</span></span>|<span data-ttu-id="bdc0d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bdc0d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="bdc0d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bdc0d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="bdc0d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bdc0d-107">Event ID</span></span>|<span data-ttu-id="bdc0d-108">10856</span><span class="sxs-lookup"><span data-stu-id="bdc0d-108">10856</span></span>|  
|<span data-ttu-id="bdc0d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bdc0d-109">Event Source</span></span>|<span data-ttu-id="bdc0d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bdc0d-110">ENTSSO</span></span>|  
|<span data-ttu-id="bdc0d-111">组件</span><span class="sxs-lookup"><span data-stu-id="bdc0d-111">Component</span></span>|<span data-ttu-id="bdc0d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="bdc0d-112">N/A</span></span>|  
|<span data-ttu-id="bdc0d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bdc0d-113">Symbolic Name</span></span>|<span data-ttu-id="bdc0d-114">ENTSSO_E_MAPPING_CREATE_RESTRICTED</span><span class="sxs-lookup"><span data-stu-id="bdc0d-114">ENTSSO_E_MAPPING_CREATE_RESTRICTED</span></span>|  
|<span data-ttu-id="bdc0d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bdc0d-115">Message Text</span></span>|<span data-ttu-id="bdc0d-116">应用程序用户不能为此应用程序创建映射。</span><span class="sxs-lookup"><span data-stu-id="bdc0d-116">Application Users cannot create mappings for this application.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bdc0d-117">解释</span><span class="sxs-lookup"><span data-stu-id="bdc0d-117">Explanation</span></span>  
 <span data-ttu-id="bdc0d-118">此应用程序已配置为不允许应用程序用户组的成员创建映射。</span><span class="sxs-lookup"><span data-stu-id="bdc0d-118">This application was configured in such a way that members of the Application Users group are not permitted to create mappings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bdc0d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="bdc0d-119">User Action</span></span>  
 <span data-ttu-id="bdc0d-120">您应请求具有足够权限的用户来创建这些映射。</span><span class="sxs-lookup"><span data-stu-id="bdc0d-120">You should ask a person with sufficient privileges to create these mappings.</span></span>