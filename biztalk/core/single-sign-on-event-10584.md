---
title: 单一登录： 事件 10584 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9377d-b4fd-48a6-961a-3629b3db644a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d08be0100d53f081eb7d8f4faa27d1e7f46f6f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270365"
---
# <a name="single-sign-on-event-10584"></a><span data-ttu-id="ae62f-102">单一登录： 事件 10584</span><span class="sxs-lookup"><span data-stu-id="ae62f-102">Single Sign-On: Event 10584</span></span>
## <a name="details"></a><span data-ttu-id="ae62f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ae62f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae62f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ae62f-104">Product Name</span></span>|<span data-ttu-id="ae62f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ae62f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ae62f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ae62f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ae62f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ae62f-107">Event ID</span></span>|<span data-ttu-id="ae62f-108">10584</span><span class="sxs-lookup"><span data-stu-id="ae62f-108">10584</span></span>|  
|<span data-ttu-id="ae62f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ae62f-109">Event Source</span></span>|<span data-ttu-id="ae62f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ae62f-110">ENTSSO</span></span>|  
|<span data-ttu-id="ae62f-111">组件</span><span class="sxs-lookup"><span data-stu-id="ae62f-111">Component</span></span>|<span data-ttu-id="ae62f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ae62f-112">N/A</span></span>|  
|<span data-ttu-id="ae62f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ae62f-113">Symbolic Name</span></span>|<span data-ttu-id="ae62f-114">SSO_WARN_NO_IMPERSONATION</span><span class="sxs-lookup"><span data-stu-id="ae62f-114">SSO_WARN_NO_IMPERSONATION</span></span>|  
|<span data-ttu-id="ae62f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ae62f-115">Message Text</span></span>|<span data-ttu-id="ae62f-116">无法模拟客户端。%r</span><span class="sxs-lookup"><span data-stu-id="ae62f-116">Could not impersonate the client.%r</span></span><br /><br /> <span data-ttu-id="ae62f-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="ae62f-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae62f-118">解释</span><span class="sxs-lookup"><span data-stu-id="ae62f-118">Explanation</span></span>  
 <span data-ttu-id="ae62f-119">模拟客户端是 ENTSSO 系统为验证客户端的标识而执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ae62f-119">Impersonating the client is something the ENTSSO System does to verify the client’s identity.</span></span> <span data-ttu-id="ae62f-120">当系统无法模拟客户端时，可能发生了以下三种情况之一。</span><span class="sxs-lookup"><span data-stu-id="ae62f-120">When the system is unable to impersonate a client, one of three things may have occurred.</span></span> <span data-ttu-id="ae62f-121">客户端可能尝试执行一个常见操作，客户端可能尝试渗入系统安全，或客户端应用程序可能被设计为阻止模拟。</span><span class="sxs-lookup"><span data-stu-id="ae62f-121">The client may be attempting to perform an usual activity, the client may be attempting to infiltrate system security, or the client application may have been designed to block impersonation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae62f-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ae62f-122">User Action</span></span>  
 <span data-ttu-id="ae62f-123">找到该客户端应用程序，确定其尝试执行的操作，以及其是否阻止模拟。</span><span class="sxs-lookup"><span data-stu-id="ae62f-123">Locate the client application and determine what it is attempting to do, and whether or not it is blocking impersonation.</span></span>