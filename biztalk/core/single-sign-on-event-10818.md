---
title: 单一登录：Event 10818 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa489e88a3742dfb7acbd1995a6f996bdc58142c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295916"
---
# <a name="single-sign-on-event-10818"></a><span data-ttu-id="6c27a-102">单一登录：事件 10818</span><span class="sxs-lookup"><span data-stu-id="6c27a-102">Single Sign-On: Event 10818</span></span>
## <a name="details"></a><span data-ttu-id="6c27a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6c27a-103">Details</span></span>  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  <span data-ttu-id="6c27a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6c27a-104">Product Name</span></span>   |                            <span data-ttu-id="6c27a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6c27a-105">Enterprise Single Sign-On</span></span>                            |
| <span data-ttu-id="6c27a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6c27a-106">Product Version</span></span> |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    <span data-ttu-id="6c27a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6c27a-107">Event ID</span></span>     |                                      <span data-ttu-id="6c27a-108">10818</span><span class="sxs-lookup"><span data-stu-id="6c27a-108">10818</span></span>                                      |
|  <span data-ttu-id="6c27a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6c27a-109">Event Source</span></span>   |                                     <span data-ttu-id="6c27a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6c27a-110">ENTSSO</span></span>                                      |
|    <span data-ttu-id="6c27a-111">组件</span><span class="sxs-lookup"><span data-stu-id="6c27a-111">Component</span></span>    |                                       <span data-ttu-id="6c27a-112">不可用</span><span class="sxs-lookup"><span data-stu-id="6c27a-112">N/A</span></span>                                       |
|  <span data-ttu-id="6c27a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6c27a-113">Symbolic Name</span></span>  |                         <span data-ttu-id="6c27a-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span><span class="sxs-lookup"><span data-stu-id="6c27a-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span></span>                          |
|  <span data-ttu-id="6c27a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6c27a-115">Message Text</span></span>   | <span data-ttu-id="6c27a-116">应用程序必须具有两个字段或者只有一个字段必须标记为进行同步。</span><span class="sxs-lookup"><span data-stu-id="6c27a-116">The application must have two fields or only one field must be marked for sync.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6c27a-117">解释</span><span class="sxs-lookup"><span data-stu-id="6c27a-117">Explanation</span></span>  
 <span data-ttu-id="6c27a-118">如果有两个以上字段，则有并且只有一个必须标记为密码同步。</span><span class="sxs-lookup"><span data-stu-id="6c27a-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6c27a-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="6c27a-119">User Action</span></span>  
 <span data-ttu-id="6c27a-120">若要纠正这种情况下，必须删除该应用程序并重新创建它，以便它遵循这些准则。</span><span class="sxs-lookup"><span data-stu-id="6c27a-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>