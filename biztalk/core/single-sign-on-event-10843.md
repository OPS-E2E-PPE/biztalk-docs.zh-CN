---
title: 单一登录： 事件 10843 |Microsoft Docs
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
ms.openlocfilehash: 40b7e03f54d4c4ac2b7074d2aa13d771ce20a9e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012998"
---
# <a name="single-sign-on-event-10843"></a><span data-ttu-id="c45f5-102">单一登录： 事件 10843</span><span class="sxs-lookup"><span data-stu-id="c45f5-102">Single Sign-On: Event 10843</span></span>
## <a name="details"></a><span data-ttu-id="c45f5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c45f5-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c45f5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c45f5-104">Product Name</span></span>   |                                                                      <span data-ttu-id="c45f5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c45f5-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="c45f5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c45f5-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="c45f5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c45f5-107">Event ID</span></span>     |                                                                                <span data-ttu-id="c45f5-108">10843</span><span class="sxs-lookup"><span data-stu-id="c45f5-108">10843</span></span>                                                                                |
|  <span data-ttu-id="c45f5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c45f5-109">Event Source</span></span>   |                                                                               <span data-ttu-id="c45f5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c45f5-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="c45f5-111">组件</span><span class="sxs-lookup"><span data-stu-id="c45f5-111">Component</span></span>    |                                                                                 <span data-ttu-id="c45f5-112">N/A</span><span class="sxs-lookup"><span data-stu-id="c45f5-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="c45f5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c45f5-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="c45f5-114">ENTSSO_E_NO_SECRET2</span><span class="sxs-lookup"><span data-stu-id="c45f5-114">ENTSSO_E_NO_SECRET2</span></span>                                                                         |
|  <span data-ttu-id="c45f5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c45f5-115">Message Text</span></span>   | <span data-ttu-id="c45f5-116">无法执行加密或解密，因为密钥不在主密钥服务器中。</span><span class="sxs-lookup"><span data-stu-id="c45f5-116">Cannot perform encryption or decryption because the secret is not available from the master secret server.</span></span> <span data-ttu-id="c45f5-117">有关相关错误，请参阅事件日志（在计算机 %1 上）。</span><span class="sxs-lookup"><span data-stu-id="c45f5-117">See the event log (on computer ‘%1’) for related errors.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c45f5-118">解释</span><span class="sxs-lookup"><span data-stu-id="c45f5-118">Explanation</span></span>  
 <span data-ttu-id="c45f5-119">拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="c45f5-119">Access is denied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c45f5-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="c45f5-120">User Action</span></span>  
 <span data-ttu-id="c45f5-121">主密钥服务器脱机，或主密钥服务器缺少所需的主密钥。</span><span class="sxs-lookup"><span data-stu-id="c45f5-121">Either the master secret server is off-line, or the master secret server is missing the required master secret.</span></span> <span data-ttu-id="c45f5-122">参阅指定计算机上的事件日志，了解相关错误。</span><span class="sxs-lookup"><span data-stu-id="c45f5-122">See the event log on the specified computer for related errors.</span></span>