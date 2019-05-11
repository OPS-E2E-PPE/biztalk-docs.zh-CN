---
title: 单一登录：Event 10817 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c4f05181db88c58a5e29857cbe2ce80bb3ab369
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396106"
---
# <a name="single-sign-on-event-10817"></a><span data-ttu-id="53617-102">单一登录：事件 10817</span><span class="sxs-lookup"><span data-stu-id="53617-102">Single Sign-On: Event 10817</span></span>
## <a name="details"></a><span data-ttu-id="53617-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="53617-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="53617-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="53617-104">Product Name</span></span>   |                 <span data-ttu-id="53617-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="53617-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="53617-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="53617-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="53617-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="53617-107">Event ID</span></span>     |                           <span data-ttu-id="53617-108">10817</span><span class="sxs-lookup"><span data-stu-id="53617-108">10817</span></span>                            |
|  <span data-ttu-id="53617-109">事件源</span><span class="sxs-lookup"><span data-stu-id="53617-109">Event Source</span></span>   |                           <span data-ttu-id="53617-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="53617-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="53617-111">组件</span><span class="sxs-lookup"><span data-stu-id="53617-111">Component</span></span>    |                            <span data-ttu-id="53617-112">不可用</span><span class="sxs-lookup"><span data-stu-id="53617-112">N/A</span></span>                             |
|  <span data-ttu-id="53617-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="53617-113">Symbolic Name</span></span>  |              <span data-ttu-id="53617-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="53617-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span></span>               |
|  <span data-ttu-id="53617-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="53617-115">Message Text</span></span>   |         <span data-ttu-id="53617-116">找不到指定的通知。</span><span class="sxs-lookup"><span data-stu-id="53617-116">The specified notification was not found.</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="53617-117">解释</span><span class="sxs-lookup"><span data-stu-id="53617-117">Explanation</span></span>  
 <span data-ttu-id="53617-118">密码更改所指定的通知找不到 GUID。</span><span class="sxs-lookup"><span data-stu-id="53617-118">The password change specified a notification GUID which cannot be found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53617-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="53617-119">User Action</span></span>  
 <span data-ttu-id="53617-120">请参阅此密码同步适配器，以确定相应的通知 GUID 的配置。</span><span class="sxs-lookup"><span data-stu-id="53617-120">See the configuration for this password sync adapter to determine the proper GUID of the notification.</span></span>