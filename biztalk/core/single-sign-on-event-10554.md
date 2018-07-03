---
title: 单一登录： 事件 10554 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c2aa327-edde-4bf1-8904-7ad1da941443
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4b4c30804f553c4cda86641098c4a6db56a83e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977438"
---
# <a name="single-sign-on-event-10554"></a><span data-ttu-id="062b9-102">单一登录： 事件 10554</span><span class="sxs-lookup"><span data-stu-id="062b9-102">Single Sign-On: Event 10554</span></span>
## <a name="details"></a><span data-ttu-id="062b9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="062b9-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="062b9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="062b9-104">Product Name</span></span>   |                 <span data-ttu-id="062b9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="062b9-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="062b9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="062b9-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="062b9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="062b9-107">Event ID</span></span>     |                           <span data-ttu-id="062b9-108">10554</span><span class="sxs-lookup"><span data-stu-id="062b9-108">10554</span></span>                            |
|  <span data-ttu-id="062b9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="062b9-109">Event Source</span></span>   |                           <span data-ttu-id="062b9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="062b9-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="062b9-111">组件</span><span class="sxs-lookup"><span data-stu-id="062b9-111">Component</span></span>    |                            <span data-ttu-id="062b9-112">N/A</span><span class="sxs-lookup"><span data-stu-id="062b9-112">N/A</span></span>                             |
|  <span data-ttu-id="062b9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="062b9-113">Symbolic Name</span></span>  |          <span data-ttu-id="062b9-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="062b9-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="062b9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="062b9-115">Message Text</span></span>   |               <span data-ttu-id="062b9-116">查找服务器访问被拒绝。%r</span><span class="sxs-lookup"><span data-stu-id="062b9-116">Lookup server access denied.%r</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="062b9-117">解释</span><span class="sxs-lookup"><span data-stu-id="062b9-117">Explanation</span></span>  
 <span data-ttu-id="062b9-118">消息已发送至服务器，但答复被阻止。</span><span class="sxs-lookup"><span data-stu-id="062b9-118">A message was sent to the server but the reply was blocked.</span></span> <span data-ttu-id="062b9-119">此错误可能由许多不同原因导致，如协议不正确或对服务器没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="062b9-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="062b9-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="062b9-120">User Action</span></span>  
 <span data-ttu-id="062b9-121">请记录下错误日志中的信息，然后与产品支持服务部门联系。</span><span class="sxs-lookup"><span data-stu-id="062b9-121">Note the information in the error log and contact product support services.</span></span>