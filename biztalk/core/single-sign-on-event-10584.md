---
title: 单一登录：Event 10584 | Microsoft Docs
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
ms.openlocfilehash: 478d33b1ef00930617a32f18dc7cf942210e0162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395255"
---
# <a name="single-sign-on-event-10584"></a><span data-ttu-id="0c1a4-102">单一登录：事件 10584</span><span class="sxs-lookup"><span data-stu-id="0c1a4-102">Single Sign-On: Event 10584</span></span>
## <a name="details"></a><span data-ttu-id="0c1a4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0c1a4-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="0c1a4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0c1a4-104">Product Name</span></span>   |                   <span data-ttu-id="0c1a4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0c1a4-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="0c1a4-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0c1a4-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="0c1a4-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0c1a4-107">Event ID</span></span>     |                             <span data-ttu-id="0c1a4-108">10584</span><span class="sxs-lookup"><span data-stu-id="0c1a4-108">10584</span></span>                              |
|  <span data-ttu-id="0c1a4-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0c1a4-109">Event Source</span></span>   |                             <span data-ttu-id="0c1a4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0c1a4-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="0c1a4-111">组件</span><span class="sxs-lookup"><span data-stu-id="0c1a4-111">Component</span></span>    |                              <span data-ttu-id="0c1a4-112">不可用</span><span class="sxs-lookup"><span data-stu-id="0c1a4-112">N/A</span></span>                               |
|  <span data-ttu-id="0c1a4-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0c1a4-113">Symbolic Name</span></span>  |                   <span data-ttu-id="0c1a4-114">SSO_WARN_NO_IMPERSONATION</span><span class="sxs-lookup"><span data-stu-id="0c1a4-114">SSO_WARN_NO_IMPERSONATION</span></span>                    |
|  <span data-ttu-id="0c1a4-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0c1a4-115">Message Text</span></span>   | <span data-ttu-id="0c1a4-116">无法模拟 client.%r</span><span class="sxs-lookup"><span data-stu-id="0c1a4-116">Could not impersonate the client.%r</span></span><br /><br /> <span data-ttu-id="0c1a4-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="0c1a4-117">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0c1a4-118">解释</span><span class="sxs-lookup"><span data-stu-id="0c1a4-118">Explanation</span></span>  
 <span data-ttu-id="0c1a4-119">模拟客户端是 ENTSSO 系统执行的操作以验证客户端的标识。</span><span class="sxs-lookup"><span data-stu-id="0c1a4-119">Impersonating the client is something the ENTSSO System does to verify the client’s identity.</span></span> <span data-ttu-id="0c1a4-120">当系统无法模拟客户端时，以下三种情况可能会发生。</span><span class="sxs-lookup"><span data-stu-id="0c1a4-120">When the system is unable to impersonate a client, one of three things may have occurred.</span></span> <span data-ttu-id="0c1a4-121">客户端可能尝试执行一个常见操作、 客户端可能尝试渗入系统安全，或客户端应用程序可能被设计为阻止模拟。</span><span class="sxs-lookup"><span data-stu-id="0c1a4-121">The client may be attempting to perform an usual activity, the client may be attempting to infiltrate system security, or the client application may have been designed to block impersonation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c1a4-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="0c1a4-122">User Action</span></span>  
 <span data-ttu-id="0c1a4-123">找到客户端应用程序，并确定它正尝试执行操作，以及它阻止模拟。</span><span class="sxs-lookup"><span data-stu-id="0c1a4-123">Locate the client application and determine what it is attempting to do, and whether or not it is blocking impersonation.</span></span>