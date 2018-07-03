---
title: 单一登录： 事件 10553 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0da8faf-8127-4d2e-a2ef-e5af20aff34f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0103305692cfb978820cd94e9a42a3b384f5ba4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013454"
---
# <a name="single-sign-on-event-10553"></a><span data-ttu-id="c2a67-102">单一登录： 事件 10553</span><span class="sxs-lookup"><span data-stu-id="c2a67-102">Single Sign-On: Event 10553</span></span>
## <a name="details"></a><span data-ttu-id="c2a67-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c2a67-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="c2a67-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c2a67-104">Product Name</span></span>   |                 <span data-ttu-id="c2a67-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c2a67-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="c2a67-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c2a67-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="c2a67-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c2a67-107">Event ID</span></span>     |                           <span data-ttu-id="c2a67-108">10553</span><span class="sxs-lookup"><span data-stu-id="c2a67-108">10553</span></span>                            |
|  <span data-ttu-id="c2a67-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c2a67-109">Event Source</span></span>   |                           <span data-ttu-id="c2a67-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c2a67-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="c2a67-111">组件</span><span class="sxs-lookup"><span data-stu-id="c2a67-111">Component</span></span>    |                            <span data-ttu-id="c2a67-112">N/A</span><span class="sxs-lookup"><span data-stu-id="c2a67-112">N/A</span></span>                             |
|  <span data-ttu-id="c2a67-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c2a67-113">Symbolic Name</span></span>  |           <span data-ttu-id="c2a67-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="c2a67-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="c2a67-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c2a67-115">Message Text</span></span>   |               <span data-ttu-id="c2a67-116">管理服务器访问被拒绝。%r</span><span class="sxs-lookup"><span data-stu-id="c2a67-116">Admin server access denied.%r</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="c2a67-117">解释</span><span class="sxs-lookup"><span data-stu-id="c2a67-117">Explanation</span></span>  
 <span data-ttu-id="c2a67-118">发出了一个从客户端到管理服务器的调用，但是该调用未被接受。</span><span class="sxs-lookup"><span data-stu-id="c2a67-118">A call was made from a client to the Admin server but was not accepted.</span></span> <span data-ttu-id="c2a67-119">这可能是由许多不同原因引起的，例如协议不正确或客户端没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="c2a67-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2a67-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="c2a67-120">User Action</span></span>  
 <span data-ttu-id="c2a67-121">请记录下错误日志中的信息，然后与产品支持服务部门联系。</span><span class="sxs-lookup"><span data-stu-id="c2a67-121">Note the information in the error log and contact product support services.</span></span>