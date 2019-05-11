---
title: 单一登录：Event 10555 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6522295b1f6efe3be224739ff1adfe6316abaf7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398855"
---
# <a name="single-sign-on-event-10555"></a><span data-ttu-id="5828c-102">单一登录：事件 10555</span><span class="sxs-lookup"><span data-stu-id="5828c-102">Single Sign-On: Event 10555</span></span>
## <a name="details"></a><span data-ttu-id="5828c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5828c-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="5828c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5828c-104">Product Name</span></span>   |                 <span data-ttu-id="5828c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5828c-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="5828c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5828c-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="5828c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5828c-107">Event ID</span></span>     |                           <span data-ttu-id="5828c-108">10555</span><span class="sxs-lookup"><span data-stu-id="5828c-108">10555</span></span>                            |
|  <span data-ttu-id="5828c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5828c-109">Event Source</span></span>   |                           <span data-ttu-id="5828c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5828c-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="5828c-111">组件</span><span class="sxs-lookup"><span data-stu-id="5828c-111">Component</span></span>    |                            <span data-ttu-id="5828c-112">不可用</span><span class="sxs-lookup"><span data-stu-id="5828c-112">N/A</span></span>                             |
|  <span data-ttu-id="5828c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5828c-113">Symbolic Name</span></span>  |          <span data-ttu-id="5828c-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="5828c-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="5828c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5828c-115">Message Text</span></span>   | <span data-ttu-id="5828c-116">Denied.%r 访问密钥服务器</span><span class="sxs-lookup"><span data-stu-id="5828c-116">Secret server access denied.%r</span></span><br /><br /> <span data-ttu-id="5828c-117">客户端用户： %1</span><span class="sxs-lookup"><span data-stu-id="5828c-117">Client User: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5828c-118">解释</span><span class="sxs-lookup"><span data-stu-id="5828c-118">Explanation</span></span>  
 <span data-ttu-id="5828c-119">一条消息已发送到服务器但回复受到阻止。</span><span class="sxs-lookup"><span data-stu-id="5828c-119">A message was sent to the server but the reply was blocked.</span></span> <span data-ttu-id="5828c-120">原因可能是多种不同原因，例如协议不正确或服务器上没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="5828c-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5828c-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="5828c-121">User Action</span></span>  
 <span data-ttu-id="5828c-122">请注意错误日志中的信息，请与产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="5828c-122">Note the information in the error log and contact product support services.</span></span>