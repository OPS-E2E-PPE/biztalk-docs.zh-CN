---
title: 单一登录：Event 10613 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9a2743e19ef393409df934c811698557e9b0078
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397703"
---
# <a name="single-sign-on-event-10613"></a><span data-ttu-id="61cee-102">单一登录：事件 10613</span><span class="sxs-lookup"><span data-stu-id="61cee-102">Single Sign-On: Event 10613</span></span>
## <a name="details"></a><span data-ttu-id="61cee-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="61cee-103">Details</span></span>  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="61cee-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="61cee-104">Product Name</span></span>   |                                                   <span data-ttu-id="61cee-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="61cee-105">Enterprise Single Sign-On</span></span>                                                    |
| <span data-ttu-id="61cee-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="61cee-106">Product Version</span></span> |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="61cee-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="61cee-107">Event ID</span></span>     |                                                             <span data-ttu-id="61cee-108">10613</span><span class="sxs-lookup"><span data-stu-id="61cee-108">10613</span></span>                                                              |
|  <span data-ttu-id="61cee-109">事件源</span><span class="sxs-lookup"><span data-stu-id="61cee-109">Event Source</span></span>   |                                                             <span data-ttu-id="61cee-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="61cee-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="61cee-111">组件</span><span class="sxs-lookup"><span data-stu-id="61cee-111">Component</span></span>    |                                                              <span data-ttu-id="61cee-112">不可用</span><span class="sxs-lookup"><span data-stu-id="61cee-112">N/A</span></span>                                                               |
|  <span data-ttu-id="61cee-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="61cee-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="61cee-114">SSO_ERROR_RPC_CALLBACK</span><span class="sxs-lookup"><span data-stu-id="61cee-114">SSO_ERROR_RPC_CALLBACK</span></span>                                                     |
|  <span data-ttu-id="61cee-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="61cee-115">Message Text</span></span>   | <span data-ttu-id="61cee-116">SSO 服务器访问 denied.%r</span><span class="sxs-lookup"><span data-stu-id="61cee-116">SSO server access denied.%r</span></span><br /><br /> <span data-ttu-id="61cee-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="61cee-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="61cee-118">RPC 调用信息: %2: %3 %r</span><span class="sxs-lookup"><span data-stu-id="61cee-118">RPC call information: %2:%3%r</span></span><br /><br /> <span data-ttu-id="61cee-119">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="61cee-119">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="61cee-120">解释</span><span class="sxs-lookup"><span data-stu-id="61cee-120">Explanation</span></span>  
 <span data-ttu-id="61cee-121">调用到 SSO 服务器进行从客户端，但未被接受。</span><span class="sxs-lookup"><span data-stu-id="61cee-121">A call was made from a client to the SSO Server but was not accepted.</span></span> <span data-ttu-id="61cee-122">原因可能是多种不同原因，例如协议不正确或客户端上没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="61cee-122">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="61cee-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="61cee-123">User Action</span></span>  
 <span data-ttu-id="61cee-124">请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="61cee-124">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>