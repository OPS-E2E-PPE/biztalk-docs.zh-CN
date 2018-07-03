---
title: 单一登录： 事件 10728 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f579189c-c9a5-4d2c-a3d5-f0ba03c5a3ef
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5e37738d0bf566b2faf3b5b65c1152cd3ef6405
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995286"
---
# <a name="single-sign-on-event-10728"></a><span data-ttu-id="9c74d-102">单一登录： 事件 10728</span><span class="sxs-lookup"><span data-stu-id="9c74d-102">Single Sign-On: Event 10728</span></span>
## <a name="details"></a><span data-ttu-id="9c74d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c74d-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9c74d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9c74d-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="9c74d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9c74d-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="9c74d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="9c74d-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="9c74d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9c74d-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="9c74d-108">10728</span><span class="sxs-lookup"><span data-stu-id="9c74d-108">10728</span></span>                                                                                                                               |
|  <span data-ttu-id="9c74d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9c74d-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="9c74d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9c74d-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="9c74d-111">组件</span><span class="sxs-lookup"><span data-stu-id="9c74d-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="9c74d-112">N\A</span><span class="sxs-lookup"><span data-stu-id="9c74d-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="9c74d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9c74d-113">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="9c74d-114">SSO_ERROR_VERSION</span><span class="sxs-lookup"><span data-stu-id="9c74d-114">SSO_ERROR_VERSION</span></span>                                                                                                                         |
|  <span data-ttu-id="9c74d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9c74d-115">Message Text</span></span>   | <span data-ttu-id="9c74d-116">此版本的 SSO 服务器与 SSO 数据库不兼容。</span><span class="sxs-lookup"><span data-stu-id="9c74d-116">This version of the SSO server is not compatible with the SSO database.</span></span> <span data-ttu-id="9c74d-117">请升级您的主密钥服务器。%r</span><span class="sxs-lookup"><span data-stu-id="9c74d-117">Please upgrade your master secret server.%r</span></span><br /><br /> <span data-ttu-id="9c74d-118">SQL Server 名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9c74d-118">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="9c74d-119">SSO 数据库名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="9c74d-119">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="9c74d-120">SSO 数据库版本: %3 %r</span><span class="sxs-lookup"><span data-stu-id="9c74d-120">SSO Database Version: %3%r</span></span><br /><br /> <span data-ttu-id="9c74d-121">所需的版本： %4</span><span class="sxs-lookup"><span data-stu-id="9c74d-121">Required Version: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="9c74d-122">解释</span><span class="sxs-lookup"><span data-stu-id="9c74d-122">Explanation</span></span>  
 <span data-ttu-id="9c74d-123">此错误事件表示，SSO 服务器版本比（最初创建的版本）SSO 数据库更新。</span><span class="sxs-lookup"><span data-stu-id="9c74d-123">This Error event indicates that the SSO server version is more recent than (the version that originally created) the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9c74d-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="9c74d-124">User Action</span></span>  
 <span data-ttu-id="9c74d-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c74d-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="9c74d-126">升级 SSO 主密钥服务器以匹配此 SSO 服务器的当前版本。</span><span class="sxs-lookup"><span data-stu-id="9c74d-126">Upgrade the SSO master secret server to match the current version of this SSO server.</span></span> <span data-ttu-id="9c74d-127">此操作会将 SSO 数据库升级到当前版本。</span><span class="sxs-lookup"><span data-stu-id="9c74d-127">This will upgrade the SSO database to the current version.</span></span>  

  <span data-ttu-id="9c74d-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="9c74d-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="9c74d-129">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="9c74d-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
