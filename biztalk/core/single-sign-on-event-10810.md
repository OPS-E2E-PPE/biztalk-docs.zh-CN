---
title: 单一登录： 事件 10810 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2d22ad-d5a8-4d32-af1d-8fa7237fd7ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92259f18dda8633e72eaded2b988281bcbc02520
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986118"
---
# <a name="single-sign-on-event-10810"></a><span data-ttu-id="d0c97-102">单一登录： 事件 10810</span><span class="sxs-lookup"><span data-stu-id="d0c97-102">Single Sign-On: Event 10810</span></span>
## <a name="details"></a><span data-ttu-id="d0c97-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d0c97-103">Details</span></span>  
  
|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="d0c97-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d0c97-104">Product Name</span></span>   |                            <span data-ttu-id="d0c97-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d0c97-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="d0c97-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d0c97-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="d0c97-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d0c97-107">Event ID</span></span>     |                                      <span data-ttu-id="d0c97-108">10810</span><span class="sxs-lookup"><span data-stu-id="d0c97-108">10810</span></span>                                       |
|  <span data-ttu-id="d0c97-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d0c97-109">Event Source</span></span>   |                                      <span data-ttu-id="d0c97-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d0c97-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="d0c97-111">组件</span><span class="sxs-lookup"><span data-stu-id="d0c97-111">Component</span></span>    |                                       <span data-ttu-id="d0c97-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d0c97-112">N/A</span></span>                                        |
|  <span data-ttu-id="d0c97-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d0c97-113">Symbolic Name</span></span>  |                        <span data-ttu-id="d0c97-114">ENTSSO_E_HISSO_INVALID_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="d0c97-114">ENTSSO_E_HISSO_INVALID_CREDENTIALS</span></span>                        |
|  <span data-ttu-id="d0c97-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d0c97-115">Message Text</span></span>   | <span data-ttu-id="d0c97-116">指定的凭据无效或与 SSO 数据库中的凭据不匹配。</span><span class="sxs-lookup"><span data-stu-id="d0c97-116">The specified credentials are invalid or do not match those in the SSO database.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d0c97-117">解释</span><span class="sxs-lookup"><span data-stu-id="d0c97-117">Explanation</span></span>  
 <span data-ttu-id="d0c97-118">指定的凭据无效或与 SSO 数据库中的凭据不匹配。</span><span class="sxs-lookup"><span data-stu-id="d0c97-118">The specified credentials are invalid or do not match those in the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0c97-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="d0c97-119">User Action</span></span>  
 <span data-ttu-id="d0c97-120">将 SSO 数据库中的信息设置为与外部系统的信息匹配。</span><span class="sxs-lookup"><span data-stu-id="d0c97-120">Set the information in the SSO database to match the information from the external system.</span></span>