---
title: 单一登录： 事件 10851 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15121c1d7829f04bd9c106ed71da391d401ae564
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987230"
---
# <a name="single-sign-on-event-10851"></a><span data-ttu-id="cff4d-102">单一登录： 事件 10851</span><span class="sxs-lookup"><span data-stu-id="cff4d-102">Single Sign-On: Event 10851</span></span>
## <a name="details"></a><span data-ttu-id="cff4d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cff4d-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cff4d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cff4d-104">Product Name</span></span>   |                                             <span data-ttu-id="cff4d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cff4d-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="cff4d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cff4d-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="cff4d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cff4d-107">Event ID</span></span>     |                                                       <span data-ttu-id="cff4d-108">10851</span><span class="sxs-lookup"><span data-stu-id="cff4d-108">10851</span></span>                                                       |
|  <span data-ttu-id="cff4d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cff4d-109">Event Source</span></span>   |                                                      <span data-ttu-id="cff4d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cff4d-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="cff4d-111">组件</span><span class="sxs-lookup"><span data-stu-id="cff4d-111">Component</span></span>    |                                                        <span data-ttu-id="cff4d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="cff4d-112">N/A</span></span>                                                        |
|  <span data-ttu-id="cff4d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cff4d-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="cff4d-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span><span class="sxs-lookup"><span data-stu-id="cff4d-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span></span>                                      |
|  <span data-ttu-id="cff4d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cff4d-115">Message Text</span></span>   | <span data-ttu-id="cff4d-116">应用程序无法分配到密码同步适配器，因为其已设置“直接密码同步”标志。</span><span class="sxs-lookup"><span data-stu-id="cff4d-116">The application cannot be assigned to a password sync adapter because it has the 'direct password sync' flag set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cff4d-117">解释</span><span class="sxs-lookup"><span data-stu-id="cff4d-117">Explanation</span></span>  
 <span data-ttu-id="cff4d-118">应用程序无法使用直接密码同步和密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="cff4d-118">An application cannot use both direct password sync and a password sync adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cff4d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="cff4d-119">User Action</span></span>  
 <span data-ttu-id="cff4d-120">检查您的应用程序并决定其是否应具有直接密码同步。如果应该，则保留标记设置，并且不要尝试将应用程序分配到密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="cff4d-120">Review your application and decide whether or not it should have direct password sync. If it should, leave the flag set as it is and do not attempt to assign the application to a password sync adapter.</span></span> <span data-ttu-id="cff4d-121">如果不应该，则关闭标志并根据需要将应用程序分配到密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="cff4d-121">If it should not, then turn the flag off and assign the application to a password sync adapter as appropriate.</span></span>