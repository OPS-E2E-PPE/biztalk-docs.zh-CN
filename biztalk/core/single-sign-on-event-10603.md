---
title: 单一登录：Event 10603 | Microsoft Docs
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
ms.openlocfilehash: c57b75ba39be2b49606b351573f50c677077aa48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397783"
---
# <a name="single-sign-on-event-10603"></a><span data-ttu-id="ff120-102">单一登录：事件 10603</span><span class="sxs-lookup"><span data-stu-id="ff120-102">Single Sign-On: Event 10603</span></span>
## <a name="details"></a><span data-ttu-id="ff120-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ff120-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ff120-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ff120-104">Product Name</span></span>   |                                                             <span data-ttu-id="ff120-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ff120-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="ff120-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ff120-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="ff120-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ff120-107">Event ID</span></span>     |                                                                       <span data-ttu-id="ff120-108">10603</span><span class="sxs-lookup"><span data-stu-id="ff120-108">10603</span></span>                                                                        |
|  <span data-ttu-id="ff120-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ff120-109">Event Source</span></span>   |                                                                       <span data-ttu-id="ff120-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ff120-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="ff120-111">组件</span><span class="sxs-lookup"><span data-stu-id="ff120-111">Component</span></span>    |                                                                        <span data-ttu-id="ff120-112">不可用</span><span class="sxs-lookup"><span data-stu-id="ff120-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="ff120-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ff120-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="ff120-114">SSO_WARN_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="ff120-114">SSO_WARN_DB_ACCESS</span></span>                                                                 |
|  <span data-ttu-id="ff120-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ff120-115">Message Text</span></span>   | <span data-ttu-id="ff120-116">无法访问 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="ff120-116">Could not access the SSO database.</span></span> <span data-ttu-id="ff120-117">如果此状况继续存在，SSO 服务将脱机 offline.%r</span><span class="sxs-lookup"><span data-stu-id="ff120-117">If this condition persists, the SSO service will go offline.%r</span></span><br /><br /> <span data-ttu-id="ff120-118">%1.%r</span><span class="sxs-lookup"><span data-stu-id="ff120-118">%1.%r</span></span><br /><br /> <span data-ttu-id="ff120-119">SQL 错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="ff120-119">SQL Error code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ff120-120">解释</span><span class="sxs-lookup"><span data-stu-id="ff120-120">Explanation</span></span>  
 <span data-ttu-id="ff120-121">SSO 数据库不可用。</span><span class="sxs-lookup"><span data-stu-id="ff120-121">The SSO database is unavailable.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff120-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ff120-122">User Action</span></span>  
 <span data-ttu-id="ff120-123">检查警告中包含的 SQL 错误代码。</span><span class="sxs-lookup"><span data-stu-id="ff120-123">Check the SQL error code contained in the warning.</span></span> <span data-ttu-id="ff120-124">这可能会提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="ff120-124">This may offer some guidance.</span></span> <span data-ttu-id="ff120-125">如果没有，请与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="ff120-125">If not, contact Microsoft Product Support Services.</span></span>