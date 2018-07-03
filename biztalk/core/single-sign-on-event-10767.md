---
title: 单一登录： 事件 10767 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef5efc04-a0b5-4fc7-9d0e-f7aa9a9c413d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a14733abb624207704b304ef9718608c9df1c4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977334"
---
# <a name="single-sign-on-event-10767"></a><span data-ttu-id="7a155-102">单一登录： 事件 10767</span><span class="sxs-lookup"><span data-stu-id="7a155-102">Single Sign-On: Event 10767</span></span>
## <a name="details"></a><span data-ttu-id="7a155-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7a155-103">Details</span></span>  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a155-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7a155-104">Product Name</span></span>   |                                                <span data-ttu-id="7a155-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7a155-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="7a155-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7a155-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                |
|    <span data-ttu-id="7a155-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7a155-107">Event ID</span></span>     |                                                          <span data-ttu-id="7a155-108">10767</span><span class="sxs-lookup"><span data-stu-id="7a155-108">10767</span></span>                                                          |
|  <span data-ttu-id="7a155-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7a155-109">Event Source</span></span>   |                                                         <span data-ttu-id="7a155-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a155-110">ENTSSO</span></span>                                                          |
|    <span data-ttu-id="7a155-111">组件</span><span class="sxs-lookup"><span data-stu-id="7a155-111">Component</span></span>    |                                                           <span data-ttu-id="7a155-112">N/A</span><span class="sxs-lookup"><span data-stu-id="7a155-112">N/A</span></span>                                                           |
|  <span data-ttu-id="7a155-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7a155-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="7a155-114">ENTSSO_E_NO_SSO_SERVER</span><span class="sxs-lookup"><span data-stu-id="7a155-114">ENTSSO_E_NO_SSO_SERVER</span></span>                                                  |
|  <span data-ttu-id="7a155-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7a155-115">Message Text</span></span>   | <span data-ttu-id="7a155-116">无法联系 SSO 服务器“%1”。</span><span class="sxs-lookup"><span data-stu-id="7a155-116">Could not contact the SSO server ‘%1’.</span></span> <span data-ttu-id="7a155-117">请检查是否正确配置了 SSO 以及 SSO 服务是否正在该服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="7a155-117">Check that SSO is configured and that the SSO service is running on that server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7a155-118">解释</span><span class="sxs-lookup"><span data-stu-id="7a155-118">Explanation</span></span>  
 <span data-ttu-id="7a155-119">ENTSSO 客户端无法联系 ENTSSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="7a155-119">The ENTSSO client is unable to contact the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a155-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="7a155-120">User Action</span></span>  
 <span data-ttu-id="7a155-121">检查网络连接性并确保您正确拼写了服务器名称。</span><span class="sxs-lookup"><span data-stu-id="7a155-121">Check network connectivity and make sure you spelled the server name correctly.</span></span>