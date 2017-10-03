---
title: "单一登录： 事件 11029 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f24cee6fcbe7db5ce0b4f31d458a5a29118c3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11029"></a><span data-ttu-id="b9618-102">单一登录： 事件 11029</span><span class="sxs-lookup"><span data-stu-id="b9618-102">Single Sign-On: Event 11029</span></span>
## <a name="details"></a><span data-ttu-id="b9618-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b9618-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9618-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b9618-104">Product Name</span></span>|<span data-ttu-id="b9618-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b9618-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b9618-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b9618-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b9618-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b9618-107">Event ID</span></span>|<span data-ttu-id="b9618-108">11029</span><span class="sxs-lookup"><span data-stu-id="b9618-108">11029</span></span>|  
|<span data-ttu-id="b9618-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b9618-109">Event Source</span></span>|<span data-ttu-id="b9618-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b9618-110">ENTSSO</span></span>|  
|<span data-ttu-id="b9618-111">组件</span><span class="sxs-lookup"><span data-stu-id="b9618-111">Component</span></span>|<span data-ttu-id="b9618-112">N/A</span><span class="sxs-lookup"><span data-stu-id="b9618-112">N/A</span></span>|  
|<span data-ttu-id="b9618-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b9618-113">Symbolic Name</span></span>|<span data-ttu-id="b9618-114">SSO_INFO_CASE_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="b9618-114">SSO_INFO_CASE_SENSITIVE</span></span>|  
|<span data-ttu-id="b9618-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b9618-115">Message Text</span></span>|<span data-ttu-id="b9618-116">SSO 数据库区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b9618-116">The SSO database is case sensitive.</span></span> <span data-ttu-id="b9618-117">SSO 服务器将在区分大小写的模式下运行。</span><span class="sxs-lookup"><span data-stu-id="b9618-117">The SSO server will run in case sensitive mode.</span></span> <span data-ttu-id="b9618-118">有关详细信息，请参阅文档。%r</span><span class="sxs-lookup"><span data-stu-id="b9618-118">See documentation for details.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b9618-119">解释</span><span class="sxs-lookup"><span data-stu-id="b9618-119">Explanation</span></span>  
 <span data-ttu-id="b9618-120">默认情况下，SSO 服务器不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b9618-120">By default the SSO server is not case-sensitive.</span></span> <span data-ttu-id="b9618-121">但是，SQL Server SSO 数据库已配置为区分大小写，因此 SSO Server 也将在区分大小写的模式下运行。</span><span class="sxs-lookup"><span data-stu-id="b9618-121">However, the SQL Server SSO database has been configured to be case-sensitive, so the SSO Server will also run in case sensitive mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9618-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="b9618-122">User Action</span></span>  
 <span data-ttu-id="b9618-123">指定应用程序名和外部帐户名时，请注意这一点，因为现在它们是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="b9618-123">Be aware of this when specifying application names and external account names as they are now case-sensitive.</span></span> <span data-ttu-id="b9618-124">有关详细信息，请参阅[SSO 服务器](../core/sso-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b9618-124">For more information, see [SSO Server](../core/sso-server.md).</span></span>