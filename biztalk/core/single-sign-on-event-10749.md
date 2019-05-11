---
title: 单一登录：Event 10749 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25392ade6b6db955a3f5d1b99086f01f920f2ff1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395478"
---
# <a name="single-sign-on-event-10749"></a><span data-ttu-id="62f4b-102">单一登录：事件 10749</span><span class="sxs-lookup"><span data-stu-id="62f4b-102">Single Sign-On: Event 10749</span></span>
## <a name="details"></a><span data-ttu-id="62f4b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="62f4b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="62f4b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="62f4b-104">Product Name</span></span>   |                                                                                                                      <span data-ttu-id="62f4b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="62f4b-105">Enterprise Single Sign-On</span></span>                                                                                                                      |
| <span data-ttu-id="62f4b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="62f4b-106">Product Version</span></span> |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    <span data-ttu-id="62f4b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="62f4b-107">Event ID</span></span>     |                                                                                                                                <span data-ttu-id="62f4b-108">10749</span><span class="sxs-lookup"><span data-stu-id="62f4b-108">10749</span></span>                                                                                                                                |
|  <span data-ttu-id="62f4b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="62f4b-109">Event Source</span></span>   |                                                                                                                               <span data-ttu-id="62f4b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="62f4b-110">ENTSSO</span></span>                                                                                                                                |
|    <span data-ttu-id="62f4b-111">组件</span><span class="sxs-lookup"><span data-stu-id="62f4b-111">Component</span></span>    |                                                                                                                                 <span data-ttu-id="62f4b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="62f4b-112">N\A</span></span>                                                                                                                                 |
|  <span data-ttu-id="62f4b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="62f4b-113">Symbolic Name</span></span>  |                                                                                                                       <span data-ttu-id="62f4b-114">SSO_WARN_PS_CLIENT_PING</span><span class="sxs-lookup"><span data-stu-id="62f4b-114">SSO_WARN_PS_CLIENT_PING</span></span>                                                                                                                       |
|  <span data-ttu-id="62f4b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="62f4b-115">Message Text</span></span>   | <span data-ttu-id="62f4b-116">无法联系目标 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="62f4b-116">Could not contact the destination SSO server.</span></span><br /><br /> <span data-ttu-id="62f4b-117">检查 SSO 服务正在运行该服务器上并且它可以 contacted.%r</span><span class="sxs-lookup"><span data-stu-id="62f4b-117">Check that the SSO service is running on that server and that it can be contacted.%r</span></span><br /><br /> <span data-ttu-id="62f4b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="62f4b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="62f4b-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="62f4b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="62f4b-120">SSO 服务器名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="62f4b-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="62f4b-121">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="62f4b-121">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="62f4b-122">解释</span><span class="sxs-lookup"><span data-stu-id="62f4b-122">Explanation</span></span>  
 <span data-ttu-id="62f4b-123">此警告事件表明 SSO 密码同步无法联系指定的目标 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="62f4b-123">This Warning event indicates that SSO Password Sync could not contact the specified destination SSO server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="62f4b-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="62f4b-124">User Action</span></span>  
 <span data-ttu-id="62f4b-125">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="62f4b-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="62f4b-126">使用 ENTSSO 服务器管理单元中，若要检查的服务器。</span><span class="sxs-lookup"><span data-stu-id="62f4b-126">Use the ENTSSO Servers Snap-In to check the server.</span></span>  

- <span data-ttu-id="62f4b-127">如果未运行，请启动企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="62f4b-127">Start the Enterprise Single Sign-On Service if it is not running.</span></span>  

- <span data-ttu-id="62f4b-128">检查与目标 SSO 服务器的网络连接。</span><span class="sxs-lookup"><span data-stu-id="62f4b-128">Check the network connection to the destination SSO server.</span></span>  

- <span data-ttu-id="62f4b-129">请检查目标 SSO 服务器上的防火墙。</span><span class="sxs-lookup"><span data-stu-id="62f4b-129">Check firewall on the destination SSO Server.</span></span>  

  <span data-ttu-id="62f4b-130">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="62f4b-130">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="62f4b-131">如何使用服务器管理单元</span><span class="sxs-lookup"><span data-stu-id="62f4b-131">How to Use the Servers Snap-in</span></span>](../core/how-to-use-the-servers-snap-in.md)
