---
title: 单一登录：事件 10851 |Microsoft Docs
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
ms.openlocfilehash: 172eae8de676cb581dd07b823ab362bf1a2401b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306634"
---
# <a name="single-sign-on-event-10851"></a><span data-ttu-id="5a920-102">单一登录：事件 10851</span><span class="sxs-lookup"><span data-stu-id="5a920-102">Single Sign-On: Event 10851</span></span>
## <a name="details"></a><span data-ttu-id="5a920-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a920-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5a920-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5a920-104">Product Name</span></span>   |                                             <span data-ttu-id="5a920-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5a920-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="5a920-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5a920-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="5a920-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5a920-107">Event ID</span></span>     |                                                       <span data-ttu-id="5a920-108">10851</span><span class="sxs-lookup"><span data-stu-id="5a920-108">10851</span></span>                                                       |
|  <span data-ttu-id="5a920-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5a920-109">Event Source</span></span>   |                                                      <span data-ttu-id="5a920-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5a920-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="5a920-111">组件</span><span class="sxs-lookup"><span data-stu-id="5a920-111">Component</span></span>    |                                                        <span data-ttu-id="5a920-112">不可用</span><span class="sxs-lookup"><span data-stu-id="5a920-112">N/A</span></span>                                                        |
|  <span data-ttu-id="5a920-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5a920-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="5a920-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span><span class="sxs-lookup"><span data-stu-id="5a920-114">ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC</span></span>                                      |
|  <span data-ttu-id="5a920-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5a920-115">Message Text</span></span>   | <span data-ttu-id="5a920-116">应用程序不能分配到密码同步适配器，因为它具有直接密码同步标志设置。</span><span class="sxs-lookup"><span data-stu-id="5a920-116">The application cannot be assigned to a password sync adapter because it has the 'direct password sync' flag set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5a920-117">解释</span><span class="sxs-lookup"><span data-stu-id="5a920-117">Explanation</span></span>  
 <span data-ttu-id="5a920-118">应用程序不能使用直接密码同步和密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="5a920-118">An application cannot use both direct password sync and a password sync adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a920-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="5a920-119">User Action</span></span>  
 <span data-ttu-id="5a920-120">查看你的应用程序并确定它应具有直接密码同步。如果应该则保留标记设置，它是并不尝试分配到密码同步适配器应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a920-120">Review your application and decide whether or not it should have direct password sync. If it should, leave the flag set as it is and do not attempt to assign the application to a password sync adapter.</span></span> <span data-ttu-id="5a920-121">如果不应，然后关闭标志并将分配到密码同步适配器根据应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a920-121">If it should not, then turn the flag off and assign the application to a password sync adapter as appropriate.</span></span>