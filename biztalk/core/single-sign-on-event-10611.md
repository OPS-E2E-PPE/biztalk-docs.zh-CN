---
title: 单一登录：Event 10611 | Microsoft Docs
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
ms.openlocfilehash: b4b0e07a7d3151cf4a25334d1d6b01fb46c3ad75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397720"
---
# <a name="single-sign-on-event-10611"></a><span data-ttu-id="fd0cc-102">单一登录：事件 10611</span><span class="sxs-lookup"><span data-stu-id="fd0cc-102">Single Sign-On: Event 10611</span></span>
## <a name="details"></a><span data-ttu-id="fd0cc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd0cc-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd0cc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="fd0cc-104">Product Name</span></span>   |                                                                                                         <span data-ttu-id="fd0cc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="fd0cc-105">Enterprise Single Sign-On</span></span>                                                                                                         |
| <span data-ttu-id="fd0cc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="fd0cc-106">Product Version</span></span> |                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    <span data-ttu-id="fd0cc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fd0cc-107">Event ID</span></span>     |                                                                                                                   <span data-ttu-id="fd0cc-108">10611</span><span class="sxs-lookup"><span data-stu-id="fd0cc-108">10611</span></span>                                                                                                                   |
|  <span data-ttu-id="fd0cc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="fd0cc-109">Event Source</span></span>   |                                                                                                                  <span data-ttu-id="fd0cc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fd0cc-110">ENTSSO</span></span>                                                                                                                   |
|    <span data-ttu-id="fd0cc-111">组件</span><span class="sxs-lookup"><span data-stu-id="fd0cc-111">Component</span></span>    |                                                                                                                    <span data-ttu-id="fd0cc-112">不可用</span><span class="sxs-lookup"><span data-stu-id="fd0cc-112">N/A</span></span>                                                                                                                    |
|  <span data-ttu-id="fd0cc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="fd0cc-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="fd0cc-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span><span class="sxs-lookup"><span data-stu-id="fd0cc-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span></span>                                                                                                      |
|  <span data-ttu-id="fd0cc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="fd0cc-115">Message Text</span></span>   | <span data-ttu-id="fd0cc-116">SSO 服务正在 starting.%r</span><span class="sxs-lookup"><span data-stu-id="fd0cc-116">The SSO service is starting.%r</span></span><br /><br /> <span data-ttu-id="fd0cc-117">计算机名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fd0cc-117">Computer Name: %1%r</span></span><br /><br /> <span data-ttu-id="fd0cc-118">SQL Server 名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fd0cc-118">SQL Server Name: %2%r</span></span><br /><br /> <span data-ttu-id="fd0cc-119">SSO 数据库名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="fd0cc-119">SSO Database Name: %3%r</span></span><br /><br /> <span data-ttu-id="fd0cc-120">不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="fd0cc-120">Not using SSL.</span></span> <span data-ttu-id="fd0cc-121">有关如何保护 SQL Server 连接，请参阅文档的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fd0cc-121">See documentation for details on how to secure the SQL Server connection.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fd0cc-122">解释</span><span class="sxs-lookup"><span data-stu-id="fd0cc-122">Explanation</span></span>  
 <span data-ttu-id="fd0cc-123">ENTSSO 服务正在启动而无需使用安全套接字层 (SSL)。</span><span class="sxs-lookup"><span data-stu-id="fd0cc-123">The ENTSSO Service is starting without using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="fd0cc-124">建议为 SQL，SSO 服务从保护您的连接。</span><span class="sxs-lookup"><span data-stu-id="fd0cc-124">It is recommended that you secure your connection from the SSO Service to SQL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd0cc-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="fd0cc-125">User Action</span></span>  
 <span data-ttu-id="fd0cc-126">请参阅文档，[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)</span><span class="sxs-lookup"><span data-stu-id="fd0cc-126">See the documentation at [How to Enable SSL for SSO](../core/how-to-enable-ssl-for-sso.md)</span></span>  
  
 <span data-ttu-id="fd0cc-127">.</span><span class="sxs-lookup"><span data-stu-id="fd0cc-127">.</span></span>