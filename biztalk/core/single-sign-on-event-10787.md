---
title: 单一登录： 事件 10787 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f50d8f2-01b1-40cc-ab1e-7d601e4793c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de40f3601f141b3da1e107a28aac604795bb2c68
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997110"
---
# <a name="single-sign-on-event-10787"></a><span data-ttu-id="dfa94-102">单一登录： 事件 10787</span><span class="sxs-lookup"><span data-stu-id="dfa94-102">Single Sign-On: Event 10787</span></span>
## <a name="details"></a><span data-ttu-id="dfa94-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dfa94-103">Details</span></span>  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dfa94-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dfa94-104">Product Name</span></span>   |                                                   <span data-ttu-id="dfa94-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="dfa94-105">Enterprise Single Sign-On</span></span>                                                   |
| <span data-ttu-id="dfa94-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="dfa94-106">Product Version</span></span> |                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="dfa94-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dfa94-107">Event ID</span></span>     |                                                             <span data-ttu-id="dfa94-108">10787</span><span class="sxs-lookup"><span data-stu-id="dfa94-108">10787</span></span>                                                             |
|  <span data-ttu-id="dfa94-109">事件源</span><span class="sxs-lookup"><span data-stu-id="dfa94-109">Event Source</span></span>   |                                                            <span data-ttu-id="dfa94-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dfa94-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="dfa94-111">组件</span><span class="sxs-lookup"><span data-stu-id="dfa94-111">Component</span></span>    |                                                              <span data-ttu-id="dfa94-112">N/A</span><span class="sxs-lookup"><span data-stu-id="dfa94-112">N/A</span></span>                                                              |
|  <span data-ttu-id="dfa94-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="dfa94-113">Symbolic Name</span></span>  |                                                   <span data-ttu-id="dfa94-114">ENTSSO_E_FLAGS_NOT_VALID</span><span class="sxs-lookup"><span data-stu-id="dfa94-114">ENTSSO_E_FLAGS_NOT_VALID</span></span>                                                    |
|  <span data-ttu-id="dfa94-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="dfa94-115">Message Text</span></span>   | <span data-ttu-id="dfa94-116">指定的标志无效或相互不兼容。</span><span class="sxs-lookup"><span data-stu-id="dfa94-116">The specified flags are not valid or are incompatible with each other.</span></span> <span data-ttu-id="dfa94-117">有关详细信息，请查看计算机“%1”上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="dfa94-117">See the event log (on computer ‘%1’) for more details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dfa94-118">解释</span><span class="sxs-lookup"><span data-stu-id="dfa94-118">Explanation</span></span>  
 <span data-ttu-id="dfa94-119">指定的标志无效或相互不兼容。</span><span class="sxs-lookup"><span data-stu-id="dfa94-119">The specified flags are not valid or are incompatible with each other.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dfa94-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="dfa94-120">User Action</span></span>  
 <span data-ttu-id="dfa94-121">检查指定计算机上的事件日志，以查看应用程序的有效和无效标志，以及相关错误。</span><span class="sxs-lookup"><span data-stu-id="dfa94-121">Check the event log on the specified computer to see this application’s valid and invalid flags, and for related errors.</span></span>