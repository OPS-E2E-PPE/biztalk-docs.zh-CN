---
title: 单一登录： 事件 10600 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cab2c98-d576-488c-aba5-093b34489bb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86a4bf3671da5b49e981a652d311136a9ae5c0eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972046"
---
# <a name="single-sign-on-event-10600"></a><span data-ttu-id="28f41-102">单一登录： 事件 10600</span><span class="sxs-lookup"><span data-stu-id="28f41-102">Single Sign-On: Event 10600</span></span>
## <a name="details"></a><span data-ttu-id="28f41-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="28f41-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="28f41-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="28f41-104">Product Name</span></span>   |                 <span data-ttu-id="28f41-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="28f41-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="28f41-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="28f41-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="28f41-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="28f41-107">Event ID</span></span>     |                           <span data-ttu-id="28f41-108">10600</span><span class="sxs-lookup"><span data-stu-id="28f41-108">10600</span></span>                            |
|  <span data-ttu-id="28f41-109">事件源</span><span class="sxs-lookup"><span data-stu-id="28f41-109">Event Source</span></span>   |                           <span data-ttu-id="28f41-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="28f41-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="28f41-111">组件</span><span class="sxs-lookup"><span data-stu-id="28f41-111">Component</span></span>    |                            <span data-ttu-id="28f41-112">N/A</span><span class="sxs-lookup"><span data-stu-id="28f41-112">N/A</span></span>                             |
|  <span data-ttu-id="28f41-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="28f41-113">Symbolic Name</span></span>  |            <span data-ttu-id="28f41-114">SSO_ERROR_CS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="28f41-114">SSO_ERROR_CS_CALLBACK_ACCESS_DENIED</span></span>             |
|  <span data-ttu-id="28f41-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="28f41-115">Message Text</span></span>   |            <span data-ttu-id="28f41-116">配置存储服务器访问被拒绝。%r</span><span class="sxs-lookup"><span data-stu-id="28f41-116">Config Store server access denied.%r</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="28f41-117">解释</span><span class="sxs-lookup"><span data-stu-id="28f41-117">Explanation</span></span>  
 <span data-ttu-id="28f41-118">消息发送到配置存储服务器但未被接受。</span><span class="sxs-lookup"><span data-stu-id="28f41-118">A message was sent to the Config Store server but was not accepted.</span></span> <span data-ttu-id="28f41-119">这可能是由许多不同原因引起的，例如协议不正确或没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="28f41-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28f41-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="28f41-120">User Action</span></span>  
 <span data-ttu-id="28f41-121">请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="28f41-121">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>