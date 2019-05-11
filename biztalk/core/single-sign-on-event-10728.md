---
title: 单一登录：Event 10728 | Microsoft Docs
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
ms.openlocfilehash: a9c7469a60ba0143f3e6674f5b140a452eebfe63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394338"
---
# <a name="single-sign-on-event-10728"></a><span data-ttu-id="40d56-102">单一登录：事件 10728</span><span class="sxs-lookup"><span data-stu-id="40d56-102">Single Sign-On: Event 10728</span></span>
## <a name="details"></a><span data-ttu-id="40d56-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="40d56-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="40d56-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="40d56-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="40d56-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="40d56-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="40d56-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="40d56-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="40d56-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="40d56-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="40d56-108">10728</span><span class="sxs-lookup"><span data-stu-id="40d56-108">10728</span></span>                                                                                                                               |
|  <span data-ttu-id="40d56-109">事件源</span><span class="sxs-lookup"><span data-stu-id="40d56-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="40d56-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="40d56-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="40d56-111">组件</span><span class="sxs-lookup"><span data-stu-id="40d56-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="40d56-112">N\A</span><span class="sxs-lookup"><span data-stu-id="40d56-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="40d56-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="40d56-113">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="40d56-114">SSO_ERROR_VERSION</span><span class="sxs-lookup"><span data-stu-id="40d56-114">SSO_ERROR_VERSION</span></span>                                                                                                                         |
|  <span data-ttu-id="40d56-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="40d56-115">Message Text</span></span>   | <span data-ttu-id="40d56-116">此版本的 SSO 服务器不兼容与 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="40d56-116">This version of the SSO server is not compatible with the SSO database.</span></span> <span data-ttu-id="40d56-117">请升级你主 server.%r</span><span class="sxs-lookup"><span data-stu-id="40d56-117">Please upgrade your master secret server.%r</span></span><br /><br /> <span data-ttu-id="40d56-118">SQL Server 名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="40d56-118">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="40d56-119">SSO 数据库名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="40d56-119">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="40d56-120">SSO 数据库版本: %3 %r</span><span class="sxs-lookup"><span data-stu-id="40d56-120">SSO Database Version: %3%r</span></span><br /><br /> <span data-ttu-id="40d56-121">所需的版本： %4</span><span class="sxs-lookup"><span data-stu-id="40d56-121">Required Version: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="40d56-122">解释</span><span class="sxs-lookup"><span data-stu-id="40d56-122">Explanation</span></span>  
 <span data-ttu-id="40d56-123">此错误事件表示 SSO 服务器版本是比 （最初创建的版本） 更新 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="40d56-123">This Error event indicates that the SSO server version is more recent than (the version that originally created) the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="40d56-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="40d56-124">User Action</span></span>  
 <span data-ttu-id="40d56-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="40d56-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="40d56-126">升级 SSO 主密钥服务器以匹配此 SSO 服务器的当前版本。</span><span class="sxs-lookup"><span data-stu-id="40d56-126">Upgrade the SSO master secret server to match the current version of this SSO server.</span></span> <span data-ttu-id="40d56-127">这将升级到最新版本的 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="40d56-127">This will upgrade the SSO database to the current version.</span></span>  

  <span data-ttu-id="40d56-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="40d56-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="40d56-129">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="40d56-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
