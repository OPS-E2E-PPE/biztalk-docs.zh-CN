---
title: 单一登录： 事件 10552 |Microsoft Docs
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
ms.openlocfilehash: e4f78ce40f827e6c06e59e1382aba8faac0337f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001206"
---
# <a name="single-sign-on-event-10552"></a><span data-ttu-id="de5b9-102">单一登录： 事件 10552</span><span class="sxs-lookup"><span data-stu-id="de5b9-102">Single Sign-On: Event 10552</span></span>
## <a name="details"></a><span data-ttu-id="de5b9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="de5b9-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="de5b9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="de5b9-104">Product Name</span></span>   |                 <span data-ttu-id="de5b9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="de5b9-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="de5b9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="de5b9-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="de5b9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="de5b9-107">Event ID</span></span>     |                           <span data-ttu-id="de5b9-108">10552</span><span class="sxs-lookup"><span data-stu-id="de5b9-108">10552</span></span>                            |
|  <span data-ttu-id="de5b9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="de5b9-109">Event Source</span></span>   |                           <span data-ttu-id="de5b9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="de5b9-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="de5b9-111">组件</span><span class="sxs-lookup"><span data-stu-id="de5b9-111">Component</span></span>    |                            <span data-ttu-id="de5b9-112">N/A</span><span class="sxs-lookup"><span data-stu-id="de5b9-112">N/A</span></span>                             |
|  <span data-ttu-id="de5b9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="de5b9-113">Symbolic Name</span></span>  |          <span data-ttu-id="de5b9-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="de5b9-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="de5b9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="de5b9-115">Message Text</span></span>   |              <span data-ttu-id="de5b9-116">映射服务器访问被拒绝。%r</span><span class="sxs-lookup"><span data-stu-id="de5b9-116">Mapping server access denied.%r</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="de5b9-117">解释</span><span class="sxs-lookup"><span data-stu-id="de5b9-117">Explanation</span></span>  
 <span data-ttu-id="de5b9-118">发出了一个从客户端到映射服务器的调用，但是该调用未被接受。</span><span class="sxs-lookup"><span data-stu-id="de5b9-118">A call was made from a client to the mapping server but was not accepted.</span></span> <span data-ttu-id="de5b9-119">这可能是由许多不同原因引起的，例如协议不正确或客户端没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="de5b9-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="de5b9-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="de5b9-120">User Action</span></span>  
 <span data-ttu-id="de5b9-121">请记录下错误日志中的信息，然后与产品支持服务部门联系。</span><span class="sxs-lookup"><span data-stu-id="de5b9-121">Note the information in the error log and contact product support services.</span></span>