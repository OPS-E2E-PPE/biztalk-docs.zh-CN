---
title: 单一登录：Event 10814 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d61d17eb-4cc7-48ac-942d-e7b94fee5931
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 215ab39f98f8f516917640d7ff21960b401f7419
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396137"
---
# <a name="single-sign-on-event-10814"></a><span data-ttu-id="e09d9-102">单一登录：事件 10814</span><span class="sxs-lookup"><span data-stu-id="e09d9-102">Single Sign-On: Event 10814</span></span>
## <a name="details"></a><span data-ttu-id="e09d9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e09d9-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="e09d9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e09d9-104">Product Name</span></span>   |                 <span data-ttu-id="e09d9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e09d9-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="e09d9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e09d9-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="e09d9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e09d9-107">Event ID</span></span>     |                           <span data-ttu-id="e09d9-108">10814</span><span class="sxs-lookup"><span data-stu-id="e09d9-108">10814</span></span>                            |
|  <span data-ttu-id="e09d9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e09d9-109">Event Source</span></span>   |                           <span data-ttu-id="e09d9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e09d9-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="e09d9-111">组件</span><span class="sxs-lookup"><span data-stu-id="e09d9-111">Component</span></span>    |                            <span data-ttu-id="e09d9-112">不可用</span><span class="sxs-lookup"><span data-stu-id="e09d9-112">N/A</span></span>                             |
|  <span data-ttu-id="e09d9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e09d9-113">Symbolic Name</span></span>  |               <span data-ttu-id="e09d9-114">ENTSSO_E_REENCRYPT_IN_PROGRESS</span><span class="sxs-lookup"><span data-stu-id="e09d9-114">ENTSSO_E_REENCRYPT_IN_PROGRESS</span></span>               |
|  <span data-ttu-id="e09d9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e09d9-115">Message Text</span></span>   |         <span data-ttu-id="e09d9-116">SSO 数据库重新加密正在进行中。</span><span class="sxs-lookup"><span data-stu-id="e09d9-116">SSO database re-encryption is in progress.</span></span>         |
  
## <a name="explanation"></a><span data-ttu-id="e09d9-117">解释</span><span class="sxs-lookup"><span data-stu-id="e09d9-117">Explanation</span></span>  
 <span data-ttu-id="e09d9-118">重新加密 SSO 数据库时，不能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e09d9-118">This action cannot be performed while the SSO database is being re-encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e09d9-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="e09d9-119">User Action</span></span>  
 <span data-ttu-id="e09d9-120">重试该操作。</span><span class="sxs-lookup"><span data-stu-id="e09d9-120">Try the action again later.</span></span>