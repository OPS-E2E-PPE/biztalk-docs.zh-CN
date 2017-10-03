---
title: "单一登录： 事件 10555 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22cf26269a661673008a715fe0bfb2a442f30b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10555"></a><span data-ttu-id="f605e-102">单一登录： 事件 10555</span><span class="sxs-lookup"><span data-stu-id="f605e-102">Single Sign-On: Event 10555</span></span>
## <a name="details"></a><span data-ttu-id="f605e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f605e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f605e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f605e-104">Product Name</span></span>|<span data-ttu-id="f605e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f605e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f605e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f605e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f605e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f605e-107">Event ID</span></span>|<span data-ttu-id="f605e-108">10555</span><span class="sxs-lookup"><span data-stu-id="f605e-108">10555</span></span>|  
|<span data-ttu-id="f605e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f605e-109">Event Source</span></span>|<span data-ttu-id="f605e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f605e-110">ENTSSO</span></span>|  
|<span data-ttu-id="f605e-111">组件</span><span class="sxs-lookup"><span data-stu-id="f605e-111">Component</span></span>|<span data-ttu-id="f605e-112">N/A</span><span class="sxs-lookup"><span data-stu-id="f605e-112">N/A</span></span>|  
|<span data-ttu-id="f605e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f605e-113">Symbolic Name</span></span>|<span data-ttu-id="f605e-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="f605e-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="f605e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f605e-115">Message Text</span></span>|<span data-ttu-id="f605e-116">密钥服务器访问被拒绝。%r</span><span class="sxs-lookup"><span data-stu-id="f605e-116">Secret server access denied.%r</span></span><br /><br /> <span data-ttu-id="f605e-117">客户端用户： %1</span><span class="sxs-lookup"><span data-stu-id="f605e-117">Client User: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f605e-118">解释</span><span class="sxs-lookup"><span data-stu-id="f605e-118">Explanation</span></span>  
 <span data-ttu-id="f605e-119">消息已发送至服务器，但答复被阻止。</span><span class="sxs-lookup"><span data-stu-id="f605e-119">A message was sent to the server but the reply was blocked.</span></span> <span data-ttu-id="f605e-120">此错误可能由许多不同原因导致，如协议不正确或对服务器没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="f605e-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f605e-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="f605e-121">User Action</span></span>  
 <span data-ttu-id="f605e-122">请记录下错误日志中的信息，然后与产品支持服务部门联系。</span><span class="sxs-lookup"><span data-stu-id="f605e-122">Note the information in the error log and contact product support services.</span></span>