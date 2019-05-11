---
title: 单一登录：Event 10848 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccec085ec74ab06a57232c0fa81afd6e9bfadd32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306697"
---
# <a name="single-sign-on-event-10848"></a><span data-ttu-id="46633-102">单一登录：事件 10848</span><span class="sxs-lookup"><span data-stu-id="46633-102">Single Sign-On: Event 10848</span></span>
## <a name="details"></a><span data-ttu-id="46633-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="46633-103">Details</span></span>  
  
|                 |                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------|
|  <span data-ttu-id="46633-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="46633-104">Product Name</span></span>   |                                 <span data-ttu-id="46633-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="46633-105">Enterprise Single Sign-On</span></span>                                  |
| <span data-ttu-id="46633-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="46633-106">Product Version</span></span> |                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    <span data-ttu-id="46633-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="46633-107">Event ID</span></span>     |                                           <span data-ttu-id="46633-108">10848</span><span class="sxs-lookup"><span data-stu-id="46633-108">10848</span></span>                                            |
|  <span data-ttu-id="46633-109">事件源</span><span class="sxs-lookup"><span data-stu-id="46633-109">Event Source</span></span>   |                                           <span data-ttu-id="46633-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="46633-110">ENTSSO</span></span>                                           |
|    <span data-ttu-id="46633-111">组件</span><span class="sxs-lookup"><span data-stu-id="46633-111">Component</span></span>    |                                            <span data-ttu-id="46633-112">不可用</span><span class="sxs-lookup"><span data-stu-id="46633-112">N/A</span></span>                                             |
|  <span data-ttu-id="46633-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="46633-113">Symbolic Name</span></span>  |                         <span data-ttu-id="46633-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="46633-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS</span></span>                         |
|  <span data-ttu-id="46633-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="46633-115">Message Text</span></span>   | <span data-ttu-id="46633-116">此应用程序不允许直接密码同步，因为其字段不明确。</span><span class="sxs-lookup"><span data-stu-id="46633-116">Direct password sync is not allowed for this application because its fields are ambiguous.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="46633-117">解释</span><span class="sxs-lookup"><span data-stu-id="46633-117">Explanation</span></span>  
 <span data-ttu-id="46633-118">如果有两个以上字段，则有并且只有一个必须标记为密码同步。</span><span class="sxs-lookup"><span data-stu-id="46633-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46633-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="46633-119">User Action</span></span>  
 <span data-ttu-id="46633-120">若要纠正这种情况下，必须删除该应用程序并重新创建它，以便它遵循这些准则。</span><span class="sxs-lookup"><span data-stu-id="46633-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>