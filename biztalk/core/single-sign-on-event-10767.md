---
title: 单一登录：事件 10767 |Microsoft Docs
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
ms.openlocfilehash: 3f225e6e80467aa269e579846c6c8ece05963cdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394296"
---
# <a name="single-sign-on-event-10767"></a><span data-ttu-id="61891-102">单一登录：事件 10767</span><span class="sxs-lookup"><span data-stu-id="61891-102">Single Sign-On: Event 10767</span></span>
## <a name="details"></a><span data-ttu-id="61891-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="61891-103">Details</span></span>  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="61891-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="61891-104">Product Name</span></span>   |                                                <span data-ttu-id="61891-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="61891-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="61891-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="61891-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                |
|    <span data-ttu-id="61891-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="61891-107">Event ID</span></span>     |                                                          <span data-ttu-id="61891-108">10767</span><span class="sxs-lookup"><span data-stu-id="61891-108">10767</span></span>                                                          |
|  <span data-ttu-id="61891-109">事件源</span><span class="sxs-lookup"><span data-stu-id="61891-109">Event Source</span></span>   |                                                         <span data-ttu-id="61891-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="61891-110">ENTSSO</span></span>                                                          |
|    <span data-ttu-id="61891-111">组件</span><span class="sxs-lookup"><span data-stu-id="61891-111">Component</span></span>    |                                                           <span data-ttu-id="61891-112">不可用</span><span class="sxs-lookup"><span data-stu-id="61891-112">N/A</span></span>                                                           |
|  <span data-ttu-id="61891-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="61891-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="61891-114">ENTSSO_E_NO_SSO_SERVER</span><span class="sxs-lookup"><span data-stu-id="61891-114">ENTSSO_E_NO_SSO_SERVER</span></span>                                                  |
|  <span data-ttu-id="61891-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="61891-115">Message Text</span></span>   | <span data-ttu-id="61891-116">无法联系 SSO 服务器"%1"。</span><span class="sxs-lookup"><span data-stu-id="61891-116">Could not contact the SSO server ‘%1’.</span></span> <span data-ttu-id="61891-117">检查配置了 SSO 以及 SSO 服务正在该服务器上。</span><span class="sxs-lookup"><span data-stu-id="61891-117">Check that SSO is configured and that the SSO service is running on that server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="61891-118">解释</span><span class="sxs-lookup"><span data-stu-id="61891-118">Explanation</span></span>  
 <span data-ttu-id="61891-119">ENTSSO 客户端将无法联系 ENTSSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="61891-119">The ENTSSO client is unable to contact the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="61891-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="61891-120">User Action</span></span>  
 <span data-ttu-id="61891-121">检查网络连接，并确保正确拼写了服务器名称。</span><span class="sxs-lookup"><span data-stu-id="61891-121">Check network connectivity and make sure you spelled the server name correctly.</span></span>