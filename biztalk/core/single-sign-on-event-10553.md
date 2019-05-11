---
title: 单一登录：Event 10553 | Microsoft Docs
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
ms.openlocfilehash: d5c2448180e963f7ecf0b0f9da694f2d31bb94f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398867"
---
# <a name="single-sign-on-event-10553"></a><span data-ttu-id="1972e-102">单一登录：事件 10553</span><span class="sxs-lookup"><span data-stu-id="1972e-102">Single Sign-On: Event 10553</span></span>
## <a name="details"></a><span data-ttu-id="1972e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1972e-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="1972e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1972e-104">Product Name</span></span>   |                 <span data-ttu-id="1972e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1972e-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="1972e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1972e-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="1972e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1972e-107">Event ID</span></span>     |                           <span data-ttu-id="1972e-108">10553</span><span class="sxs-lookup"><span data-stu-id="1972e-108">10553</span></span>                            |
|  <span data-ttu-id="1972e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1972e-109">Event Source</span></span>   |                           <span data-ttu-id="1972e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1972e-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="1972e-111">组件</span><span class="sxs-lookup"><span data-stu-id="1972e-111">Component</span></span>    |                            <span data-ttu-id="1972e-112">不可用</span><span class="sxs-lookup"><span data-stu-id="1972e-112">N/A</span></span>                             |
|  <span data-ttu-id="1972e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1972e-113">Symbolic Name</span></span>  |           <span data-ttu-id="1972e-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="1972e-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="1972e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1972e-115">Message Text</span></span>   |               <span data-ttu-id="1972e-116">管理服务器访问 denied.%r</span><span class="sxs-lookup"><span data-stu-id="1972e-116">Admin server access denied.%r</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="1972e-117">解释</span><span class="sxs-lookup"><span data-stu-id="1972e-117">Explanation</span></span>  
 <span data-ttu-id="1972e-118">调用对管理服务器进行从客户端，但未被接受。</span><span class="sxs-lookup"><span data-stu-id="1972e-118">A call was made from a client to the Admin server but was not accepted.</span></span> <span data-ttu-id="1972e-119">原因可能是多种不同原因，例如协议不正确或客户端上没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="1972e-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1972e-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="1972e-120">User Action</span></span>  
 <span data-ttu-id="1972e-121">请注意错误日志中的信息，请与产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="1972e-121">Note the information in the error log and contact product support services.</span></span>