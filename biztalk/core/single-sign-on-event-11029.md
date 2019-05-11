---
title: 单一登录：事件 11029 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4498b2a326138095bca4476c6a992e4259e81227
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379935"
---
# <a name="single-sign-on-event-11029"></a><span data-ttu-id="faa5b-102">单一登录：事件 11029</span><span class="sxs-lookup"><span data-stu-id="faa5b-102">Single Sign-On: Event 11029</span></span>
## <a name="details"></a><span data-ttu-id="faa5b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="faa5b-103">Details</span></span>  
  
|                 |                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="faa5b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="faa5b-104">Product Name</span></span>   |                                              <span data-ttu-id="faa5b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="faa5b-105">Enterprise Single Sign-On</span></span>                                               |
| <span data-ttu-id="faa5b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="faa5b-106">Product Version</span></span> |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                              |
|    <span data-ttu-id="faa5b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="faa5b-107">Event ID</span></span>     |                                                        <span data-ttu-id="faa5b-108">11029</span><span class="sxs-lookup"><span data-stu-id="faa5b-108">11029</span></span>                                                         |
|  <span data-ttu-id="faa5b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="faa5b-109">Event Source</span></span>   |                                                        <span data-ttu-id="faa5b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="faa5b-110">ENTSSO</span></span>                                                        |
|    <span data-ttu-id="faa5b-111">组件</span><span class="sxs-lookup"><span data-stu-id="faa5b-111">Component</span></span>    |                                                         <span data-ttu-id="faa5b-112">不可用</span><span class="sxs-lookup"><span data-stu-id="faa5b-112">N/A</span></span>                                                          |
|  <span data-ttu-id="faa5b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="faa5b-113">Symbolic Name</span></span>  |                                               <span data-ttu-id="faa5b-114">SSO_INFO_CASE_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="faa5b-114">SSO_INFO_CASE_SENSITIVE</span></span>                                                |
|  <span data-ttu-id="faa5b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="faa5b-115">Message Text</span></span>   | <span data-ttu-id="faa5b-116">SSO 数据库是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="faa5b-116">The SSO database is case sensitive.</span></span> <span data-ttu-id="faa5b-117">SSO 服务器将在区分大小写模式下运行。</span><span class="sxs-lookup"><span data-stu-id="faa5b-117">The SSO server will run in case sensitive mode.</span></span> <span data-ttu-id="faa5b-118">请参阅 details.%r 文档</span><span class="sxs-lookup"><span data-stu-id="faa5b-118">See documentation for details.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="faa5b-119">解释</span><span class="sxs-lookup"><span data-stu-id="faa5b-119">Explanation</span></span>  
 <span data-ttu-id="faa5b-120">默认情况下，SSO 服务器不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="faa5b-120">By default the SSO server is not case-sensitive.</span></span> <span data-ttu-id="faa5b-121">但是，SQL Server SSO 数据库已配置为区分大小写，因此 SSO Server 也将在区分大小写的模式下运行。</span><span class="sxs-lookup"><span data-stu-id="faa5b-121">However, the SQL Server SSO database has been configured to be case-sensitive, so the SSO Server will also run in case sensitive mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="faa5b-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="faa5b-122">User Action</span></span>  
 <span data-ttu-id="faa5b-123">请注意此时指定应用程序的名称和外部帐户名，因为现在它们是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="faa5b-123">Be aware of this when specifying application names and external account names as they are now case-sensitive.</span></span> <span data-ttu-id="faa5b-124">有关详细信息，请参阅[SSO 服务器](../core/sso-server.md)。</span><span class="sxs-lookup"><span data-stu-id="faa5b-124">For more information, see [SSO Server](../core/sso-server.md).</span></span>