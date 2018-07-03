---
title: 单一登录： 事件 10603 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5416ae8a2dcfdf5a3da6d8c1d00eb5a556fc3599
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970062"
---
# <a name="single-sign-on-event-10603"></a><span data-ttu-id="a2acb-102">单一登录： 事件 10603</span><span class="sxs-lookup"><span data-stu-id="a2acb-102">Single Sign-On: Event 10603</span></span>
## <a name="details"></a><span data-ttu-id="a2acb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a2acb-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a2acb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a2acb-104">Product Name</span></span>   |                                                             <span data-ttu-id="a2acb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a2acb-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="a2acb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a2acb-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="a2acb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2acb-107">Event ID</span></span>     |                                                                       <span data-ttu-id="a2acb-108">10603</span><span class="sxs-lookup"><span data-stu-id="a2acb-108">10603</span></span>                                                                        |
|  <span data-ttu-id="a2acb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a2acb-109">Event Source</span></span>   |                                                                       <span data-ttu-id="a2acb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a2acb-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="a2acb-111">组件</span><span class="sxs-lookup"><span data-stu-id="a2acb-111">Component</span></span>    |                                                                        <span data-ttu-id="a2acb-112">N/A</span><span class="sxs-lookup"><span data-stu-id="a2acb-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="a2acb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a2acb-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="a2acb-114">SSO_WARN_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="a2acb-114">SSO_WARN_DB_ACCESS</span></span>                                                                 |
|  <span data-ttu-id="a2acb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a2acb-115">Message Text</span></span>   | <span data-ttu-id="a2acb-116">无法访问 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="a2acb-116">Could not access the SSO database.</span></span> <span data-ttu-id="a2acb-117">如果此情况继续存在，SSO 服务将脱机。%r</span><span class="sxs-lookup"><span data-stu-id="a2acb-117">If this condition persists, the SSO service will go offline.%r</span></span><br /><br /> <span data-ttu-id="a2acb-118">%1.%r</span><span class="sxs-lookup"><span data-stu-id="a2acb-118">%1.%r</span></span><br /><br /> <span data-ttu-id="a2acb-119">SQL 错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="a2acb-119">SQL Error code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a2acb-120">解释</span><span class="sxs-lookup"><span data-stu-id="a2acb-120">Explanation</span></span>  
 <span data-ttu-id="a2acb-121">SSO 数据库不可用。</span><span class="sxs-lookup"><span data-stu-id="a2acb-121">The SSO database is unavailable.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2acb-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="a2acb-122">User Action</span></span>  
 <span data-ttu-id="a2acb-123">检查包含在警告中的 SQL 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a2acb-123">Check the SQL error code contained in the warning.</span></span> <span data-ttu-id="a2acb-124">错误代码中可能会提供一些指导信息。</span><span class="sxs-lookup"><span data-stu-id="a2acb-124">This may offer some guidance.</span></span> <span data-ttu-id="a2acb-125">如果没有，请联系 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="a2acb-125">If not, contact Microsoft Product Support Services.</span></span>