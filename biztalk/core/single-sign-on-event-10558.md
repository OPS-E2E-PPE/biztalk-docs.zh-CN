---
title: 单一登录：Event 10558 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7161e732fc95aa2fb62ee2ba5e8f188266804206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398824"
---
# <a name="single-sign-on-event-10558"></a><span data-ttu-id="e97bb-102">单一登录：事件 10558</span><span class="sxs-lookup"><span data-stu-id="e97bb-102">Single Sign-On: Event 10558</span></span>
## <a name="details"></a><span data-ttu-id="e97bb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e97bb-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e97bb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e97bb-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="e97bb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e97bb-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="e97bb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e97bb-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="e97bb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e97bb-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="e97bb-108">10558</span><span class="sxs-lookup"><span data-stu-id="e97bb-108">10558</span></span>                                                                                             |
|  <span data-ttu-id="e97bb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e97bb-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="e97bb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e97bb-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="e97bb-111">组件</span><span class="sxs-lookup"><span data-stu-id="e97bb-111">Component</span></span>    |                                                                                             <span data-ttu-id="e97bb-112">不可用</span><span class="sxs-lookup"><span data-stu-id="e97bb-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="e97bb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e97bb-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="e97bb-114">SSO_WARN_USER_OWN_MAPPINGS</span><span class="sxs-lookup"><span data-stu-id="e97bb-114">SSO_WARN_USER_OWN_MAPPINGS</span></span>                                                                                  |
|  <span data-ttu-id="e97bb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e97bb-115">Message Text</span></span>   | <span data-ttu-id="e97bb-116">仅允许应用程序用户控制其自己 mappings.%r</span><span class="sxs-lookup"><span data-stu-id="e97bb-116">Application Users are only allowed to control their own mappings.%r</span></span><br /><br /> <span data-ttu-id="e97bb-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e97bb-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="e97bb-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e97bb-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="e97bb-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e97bb-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="e97bb-120">客户端用户： %4</span><span class="sxs-lookup"><span data-stu-id="e97bb-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e97bb-121">解释</span><span class="sxs-lookup"><span data-stu-id="e97bb-121">Explanation</span></span>  
 <span data-ttu-id="e97bb-122">已尝试通过应用程序用户控制其他用户的映射。</span><span class="sxs-lookup"><span data-stu-id="e97bb-122">An attempt was made by an Application User to control the mappings of a different user.</span></span> <span data-ttu-id="e97bb-123">这不是允许。</span><span class="sxs-lookup"><span data-stu-id="e97bb-123">This is not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e97bb-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="e97bb-124">User Action</span></span>  
 <span data-ttu-id="e97bb-125">仅可通过特定映射应用程序用户控制的映射。</span><span class="sxs-lookup"><span data-stu-id="e97bb-125">Mappings can only be controlled by the Application Users for those specific mappings.</span></span>