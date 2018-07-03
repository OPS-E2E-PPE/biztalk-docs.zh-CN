---
title: 单一登录： 事件 10830 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd149be1-0a4f-4d39-9b0e-35202dc140cb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28bd8c50fecf5fec1f9e1ed6c6414ed4d852f877
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019091"
---
# <a name="single-sign-on-event-10830"></a><span data-ttu-id="9030b-102">单一登录： 事件 10830</span><span class="sxs-lookup"><span data-stu-id="9030b-102">Single Sign-On: Event 10830</span></span>
## <a name="details"></a><span data-ttu-id="9030b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9030b-103">Details</span></span>  
  
|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
|  <span data-ttu-id="9030b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9030b-104">Product Name</span></span>   |                        <span data-ttu-id="9030b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9030b-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="9030b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="9030b-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]        |
|    <span data-ttu-id="9030b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9030b-107">Event ID</span></span>     |                                  <span data-ttu-id="9030b-108">10830</span><span class="sxs-lookup"><span data-stu-id="9030b-108">10830</span></span>                                   |
|  <span data-ttu-id="9030b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9030b-109">Event Source</span></span>   |                                  <span data-ttu-id="9030b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9030b-110">ENTSSO</span></span>                                  |
|    <span data-ttu-id="9030b-111">组件</span><span class="sxs-lookup"><span data-stu-id="9030b-111">Component</span></span>    |                                   <span data-ttu-id="9030b-112">N/A</span><span class="sxs-lookup"><span data-stu-id="9030b-112">N/A</span></span>                                    |
|  <span data-ttu-id="9030b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9030b-113">Symbolic Name</span></span>  |                  <span data-ttu-id="9030b-114">ENTSSO_E_PSADMIN_ADAPTER_SAME_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="9030b-114">ENTSSO_E_PSADMIN_ADAPTER_SAME_COMPUTER</span></span>                  |
|  <span data-ttu-id="9030b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9030b-115">Message Text</span></span>   | <span data-ttu-id="9030b-116">指定的适配器必须位于组适配器所在的计算机上。</span><span class="sxs-lookup"><span data-stu-id="9030b-116">The specified adapter must be on the same computer as the group adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9030b-117">解释</span><span class="sxs-lookup"><span data-stu-id="9030b-117">Explanation</span></span>  
 <span data-ttu-id="9030b-118">组适配器中的每个适配器必须使用与计算机同名组适配器配置。</span><span class="sxs-lookup"><span data-stu-id="9030b-118">Each adapter in a group adapter must be configured with the same computer name as the group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9030b-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="9030b-119">User Action</span></span>  
 <span data-ttu-id="9030b-120">有关详细信息，请参阅[密码同步](../core/password-synchronization2.md)</span><span class="sxs-lookup"><span data-stu-id="9030b-120">For more information, see [Password Synchronization](../core/password-synchronization2.md)</span></span>  
  
 <span data-ttu-id="9030b-121">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="9030b-121">.</span></span>