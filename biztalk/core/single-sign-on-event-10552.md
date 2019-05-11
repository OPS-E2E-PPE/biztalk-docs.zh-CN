---
title: 单一登录：Event 10552 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f85ae0b3-d8f8-4341-8bd3-423e85402d58
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 744ecbd42d4a62fd72b792e7491f3f127ebf14f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398897"
---
# <a name="single-sign-on-event-10552"></a><span data-ttu-id="bd376-102">单一登录：事件 10552</span><span class="sxs-lookup"><span data-stu-id="bd376-102">Single Sign-On: Event 10552</span></span>
## <a name="details"></a><span data-ttu-id="bd376-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bd376-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="bd376-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bd376-104">Product Name</span></span>   |                 <span data-ttu-id="bd376-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bd376-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="bd376-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bd376-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="bd376-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bd376-107">Event ID</span></span>     |                           <span data-ttu-id="bd376-108">10552</span><span class="sxs-lookup"><span data-stu-id="bd376-108">10552</span></span>                            |
|  <span data-ttu-id="bd376-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bd376-109">Event Source</span></span>   |                           <span data-ttu-id="bd376-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bd376-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="bd376-111">组件</span><span class="sxs-lookup"><span data-stu-id="bd376-111">Component</span></span>    |                            <span data-ttu-id="bd376-112">不可用</span><span class="sxs-lookup"><span data-stu-id="bd376-112">N/A</span></span>                             |
|  <span data-ttu-id="bd376-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bd376-113">Symbolic Name</span></span>  |          <span data-ttu-id="bd376-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="bd376-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="bd376-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bd376-115">Message Text</span></span>   |              <span data-ttu-id="bd376-116">映射服务器访问 denied.%r</span><span class="sxs-lookup"><span data-stu-id="bd376-116">Mapping server access denied.%r</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="bd376-117">解释</span><span class="sxs-lookup"><span data-stu-id="bd376-117">Explanation</span></span>  
 <span data-ttu-id="bd376-118">调用对映射服务器进行从客户端，但未被接受。</span><span class="sxs-lookup"><span data-stu-id="bd376-118">A call was made from a client to the mapping server but was not accepted.</span></span> <span data-ttu-id="bd376-119">原因可能是多种不同原因，例如协议不正确或客户端上没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="bd376-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd376-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="bd376-120">User Action</span></span>  
 <span data-ttu-id="bd376-121">请注意错误日志中的信息，请与产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="bd376-121">Note the information in the error log and contact product support services.</span></span>