---
title: 单一登录：Event 10849 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdfb1cea-e445-4318-9891-b6b70a266ca9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d42ef5752b1b3bf37445d57771d00482008a7c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306672"
---
# <a name="single-sign-on-event-10849"></a><span data-ttu-id="6903d-102">单一登录：事件 10849</span><span class="sxs-lookup"><span data-stu-id="6903d-102">Single Sign-On: Event 10849</span></span>
## <a name="details"></a><span data-ttu-id="6903d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6903d-103">Details</span></span>  
  
|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  <span data-ttu-id="6903d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6903d-104">Product Name</span></span>   |                            <span data-ttu-id="6903d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6903d-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="6903d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6903d-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="6903d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6903d-107">Event ID</span></span>     |                                      <span data-ttu-id="6903d-108">10849</span><span class="sxs-lookup"><span data-stu-id="6903d-108">10849</span></span>                                       |
|  <span data-ttu-id="6903d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6903d-109">Event Source</span></span>   |                                      <span data-ttu-id="6903d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6903d-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="6903d-111">组件</span><span class="sxs-lookup"><span data-stu-id="6903d-111">Component</span></span>    |                                       <span data-ttu-id="6903d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="6903d-112">N/A</span></span>                                        |
|  <span data-ttu-id="6903d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6903d-113">Symbolic Name</span></span>  |                     <span data-ttu-id="6903d-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="6903d-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span></span>                      |
|  <span data-ttu-id="6903d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6903d-115">Message Text</span></span>   | <span data-ttu-id="6903d-116">指定了直接密码同步标志不能创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6903d-116">An application cannot be created with the ‘direct password sync’ flag specified.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6903d-117">解释</span><span class="sxs-lookup"><span data-stu-id="6903d-117">Explanation</span></span>  
 <span data-ttu-id="6903d-118">指定了直接密码同步标志不能创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6903d-118">An application cannot be created with the ‘direct password sync’ flag specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6903d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="6903d-119">User Action</span></span>  
 <span data-ttu-id="6903d-120">创建应用程序而无需直接密码同步标志。</span><span class="sxs-lookup"><span data-stu-id="6903d-120">Create the application without the direct password sync flag.</span></span> <span data-ttu-id="6903d-121">然后添加和创建字段，使应用程序，并指定直接密码同步标志。</span><span class="sxs-lookup"><span data-stu-id="6903d-121">Then add and create the fields, enable the application, and specify the direct password sync flag.</span></span>