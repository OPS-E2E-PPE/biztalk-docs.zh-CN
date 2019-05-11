---
title: 单一登录：Event 10843 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8389a1b6443fbe2d4abe592b305508b2780afdf6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307307"
---
# <a name="single-sign-on-event-10843"></a><span data-ttu-id="abaeb-102">单一登录：事件 10843</span><span class="sxs-lookup"><span data-stu-id="abaeb-102">Single Sign-On: Event 10843</span></span>
## <a name="details"></a><span data-ttu-id="abaeb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="abaeb-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="abaeb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="abaeb-104">Product Name</span></span>   |                                                                      <span data-ttu-id="abaeb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="abaeb-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="abaeb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="abaeb-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="abaeb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="abaeb-107">Event ID</span></span>     |                                                                                <span data-ttu-id="abaeb-108">10843</span><span class="sxs-lookup"><span data-stu-id="abaeb-108">10843</span></span>                                                                                |
|  <span data-ttu-id="abaeb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="abaeb-109">Event Source</span></span>   |                                                                               <span data-ttu-id="abaeb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="abaeb-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="abaeb-111">组件</span><span class="sxs-lookup"><span data-stu-id="abaeb-111">Component</span></span>    |                                                                                 <span data-ttu-id="abaeb-112">不可用</span><span class="sxs-lookup"><span data-stu-id="abaeb-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="abaeb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="abaeb-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="abaeb-114">ENTSSO_E_NO_SECRET2</span><span class="sxs-lookup"><span data-stu-id="abaeb-114">ENTSSO_E_NO_SECRET2</span></span>                                                                         |
|  <span data-ttu-id="abaeb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="abaeb-115">Message Text</span></span>   | <span data-ttu-id="abaeb-116">无法执行加密或解密，因为密钥不能从主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="abaeb-116">Cannot perform encryption or decryption because the secret is not available from the master secret server.</span></span> <span data-ttu-id="abaeb-117">请参阅事件日志中 （在计算机"%1"） 相关的错误。</span><span class="sxs-lookup"><span data-stu-id="abaeb-117">See the event log (on computer ‘%1’) for related errors.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="abaeb-118">解释</span><span class="sxs-lookup"><span data-stu-id="abaeb-118">Explanation</span></span>  
 <span data-ttu-id="abaeb-119">拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="abaeb-119">Access is denied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="abaeb-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="abaeb-120">User Action</span></span>  
 <span data-ttu-id="abaeb-121">主密钥服务器脱机，或在主密钥服务器缺少所需的主密钥。</span><span class="sxs-lookup"><span data-stu-id="abaeb-121">Either the master secret server is off-line, or the master secret server is missing the required master secret.</span></span> <span data-ttu-id="abaeb-122">有关相关错误指定的计算机上，请参阅事件日志。</span><span class="sxs-lookup"><span data-stu-id="abaeb-122">See the event log on the specified computer for related errors.</span></span>