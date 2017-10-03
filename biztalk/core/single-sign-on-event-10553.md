---
title: "单一登录： 事件 10553 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0da8faf-8127-4d2e-a2ef-e5af20aff34f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab089c5732661f38578501229934dde218e34cb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10553"></a><span data-ttu-id="2b21c-102">单一登录： 事件 10553</span><span class="sxs-lookup"><span data-stu-id="2b21c-102">Single Sign-On: Event 10553</span></span>
## <a name="details"></a><span data-ttu-id="2b21c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2b21c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b21c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2b21c-104">Product Name</span></span>|<span data-ttu-id="2b21c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2b21c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2b21c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2b21c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2b21c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b21c-107">Event ID</span></span>|<span data-ttu-id="2b21c-108">10553</span><span class="sxs-lookup"><span data-stu-id="2b21c-108">10553</span></span>|  
|<span data-ttu-id="2b21c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2b21c-109">Event Source</span></span>|<span data-ttu-id="2b21c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2b21c-110">ENTSSO</span></span>|  
|<span data-ttu-id="2b21c-111">组件</span><span class="sxs-lookup"><span data-stu-id="2b21c-111">Component</span></span>|<span data-ttu-id="2b21c-112">N/A</span><span class="sxs-lookup"><span data-stu-id="2b21c-112">N/A</span></span>|  
|<span data-ttu-id="2b21c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2b21c-113">Symbolic Name</span></span>|<span data-ttu-id="2b21c-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="2b21c-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="2b21c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2b21c-115">Message Text</span></span>|<span data-ttu-id="2b21c-116">管理服务器访问被拒绝。%r</span><span class="sxs-lookup"><span data-stu-id="2b21c-116">Admin server access denied.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b21c-117">解释</span><span class="sxs-lookup"><span data-stu-id="2b21c-117">Explanation</span></span>  
 <span data-ttu-id="2b21c-118">发出了一个从客户端到管理服务器的调用，但是该调用未被接受。</span><span class="sxs-lookup"><span data-stu-id="2b21c-118">A call was made from a client to the Admin server but was not accepted.</span></span> <span data-ttu-id="2b21c-119">这可能是由许多不同原因引起的，例如协议不正确或客户端没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="2b21c-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b21c-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="2b21c-120">User Action</span></span>  
 <span data-ttu-id="2b21c-121">请记录下错误日志中的信息，然后与产品支持服务部门联系。</span><span class="sxs-lookup"><span data-stu-id="2b21c-121">Note the information in the error log and contact product support services.</span></span>