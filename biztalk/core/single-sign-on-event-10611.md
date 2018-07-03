---
title: 单一登录： 事件 10611 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca43eff86b20df7000c973f7c6ade472a8780de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023563"
---
# <a name="single-sign-on-event-10611"></a><span data-ttu-id="e529b-102">单一登录： 事件 10611</span><span class="sxs-lookup"><span data-stu-id="e529b-102">Single Sign-On: Event 10611</span></span>
## <a name="details"></a><span data-ttu-id="e529b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e529b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e529b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e529b-104">Product Name</span></span>   |                                                                                                         <span data-ttu-id="e529b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e529b-105">Enterprise Single Sign-On</span></span>                                                                                                         |
| <span data-ttu-id="e529b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e529b-106">Product Version</span></span> |                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    <span data-ttu-id="e529b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e529b-107">Event ID</span></span>     |                                                                                                                   <span data-ttu-id="e529b-108">10611</span><span class="sxs-lookup"><span data-stu-id="e529b-108">10611</span></span>                                                                                                                   |
|  <span data-ttu-id="e529b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e529b-109">Event Source</span></span>   |                                                                                                                  <span data-ttu-id="e529b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e529b-110">ENTSSO</span></span>                                                                                                                   |
|    <span data-ttu-id="e529b-111">组件</span><span class="sxs-lookup"><span data-stu-id="e529b-111">Component</span></span>    |                                                                                                                    <span data-ttu-id="e529b-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e529b-112">N/A</span></span>                                                                                                                    |
|  <span data-ttu-id="e529b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e529b-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="e529b-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span><span class="sxs-lookup"><span data-stu-id="e529b-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span></span>                                                                                                      |
|  <span data-ttu-id="e529b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e529b-115">Message Text</span></span>   | <span data-ttu-id="e529b-116">SSO 服务正在启动。%r</span><span class="sxs-lookup"><span data-stu-id="e529b-116">The SSO service is starting.%r</span></span><br /><br /> <span data-ttu-id="e529b-117">计算机名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e529b-117">Computer Name: %1%r</span></span><br /><br /> <span data-ttu-id="e529b-118">SQL Server 名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e529b-118">SQL Server Name: %2%r</span></span><br /><br /> <span data-ttu-id="e529b-119">SSO 数据库名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e529b-119">SSO Database Name: %3%r</span></span><br /><br /> <span data-ttu-id="e529b-120">不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="e529b-120">Not using SSL.</span></span> <span data-ttu-id="e529b-121">有关如何保护 SQL Server 连接安全的详细信息，请参阅文档。</span><span class="sxs-lookup"><span data-stu-id="e529b-121">See documentation for details on how to secure the SQL Server connection.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e529b-122">解释</span><span class="sxs-lookup"><span data-stu-id="e529b-122">Explanation</span></span>  
 <span data-ttu-id="e529b-123">ENTSSO 服务正在启动，但未使用安全套接字层 (SSL)。</span><span class="sxs-lookup"><span data-stu-id="e529b-123">The ENTSSO Service is starting without using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="e529b-124">建议您保护从 SSO 服务到 SQL 的连接安全。</span><span class="sxs-lookup"><span data-stu-id="e529b-124">It is recommended that you secure your connection from the SSO Service to SQL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e529b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="e529b-125">User Action</span></span>  
 <span data-ttu-id="e529b-126">请参阅文档，[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)</span><span class="sxs-lookup"><span data-stu-id="e529b-126">See the documentation at [How to Enable SSL for SSO](../core/how-to-enable-ssl-for-sso.md)</span></span>  
  
 <span data-ttu-id="e529b-127">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="e529b-127">.</span></span>