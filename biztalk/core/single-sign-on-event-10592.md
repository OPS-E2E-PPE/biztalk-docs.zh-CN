---
title: 单一登录： 事件 10592 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fdf7259de2217c2e6cd616f58b3b1118bf991c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017253"
---
# <a name="single-sign-on-event-10592"></a><span data-ttu-id="3642a-102">单一登录： 事件 10592</span><span class="sxs-lookup"><span data-stu-id="3642a-102">Single Sign-On: Event 10592</span></span>
## <a name="details"></a><span data-ttu-id="3642a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3642a-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3642a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3642a-104">Product Name</span></span>   |                                                             <span data-ttu-id="3642a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3642a-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="3642a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3642a-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="3642a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3642a-107">Event ID</span></span>     |                                                                       <span data-ttu-id="3642a-108">10592</span><span class="sxs-lookup"><span data-stu-id="3642a-108">10592</span></span>                                                                        |
|  <span data-ttu-id="3642a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3642a-109">Event Source</span></span>   |                                                                       <span data-ttu-id="3642a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3642a-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="3642a-111">组件</span><span class="sxs-lookup"><span data-stu-id="3642a-111">Component</span></span>    |                                                                        <span data-ttu-id="3642a-112">N/A</span><span class="sxs-lookup"><span data-stu-id="3642a-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="3642a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3642a-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="3642a-114">SSO_WARN_TICKET_DECRYPT_FAILED</span><span class="sxs-lookup"><span data-stu-id="3642a-114">SSO_WARN_TICKET_DECRYPT_FAILED</span></span>                                                           |
|  <span data-ttu-id="3642a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3642a-115">Message Text</span></span>   | <span data-ttu-id="3642a-116">无法对票证进行解密。</span><span class="sxs-lookup"><span data-stu-id="3642a-116">The ticket could not be decrypted.</span></span> <span data-ttu-id="3642a-117">票证无效或者可能已过期。%r</span><span class="sxs-lookup"><span data-stu-id="3642a-117">The ticket is not valid or it may have expired.%r</span></span><br /><br /> <span data-ttu-id="3642a-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3642a-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="3642a-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="3642a-119">Error Code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3642a-120">解释</span><span class="sxs-lookup"><span data-stu-id="3642a-120">Explanation</span></span>  
 <span data-ttu-id="3642a-121">票证无效或者可能已过期。</span><span class="sxs-lookup"><span data-stu-id="3642a-121">The ticket is not valid or may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3642a-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="3642a-122">User Action</span></span>  
 <span data-ttu-id="3642a-123">确认要使用的票证是有效的并且尚未过期。</span><span class="sxs-lookup"><span data-stu-id="3642a-123">Confirm that the ticket you want to use is valid and has not expired.</span></span>