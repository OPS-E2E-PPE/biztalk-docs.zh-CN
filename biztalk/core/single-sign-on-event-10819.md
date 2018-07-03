---
title: 单一登录： 事件 10819 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa5e977-c8b9-4568-8963-0d4cf44b5637
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f196bb49cd0e5825551bbffe45757c327e2cbcca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972110"
---
# <a name="single-sign-on-event-10819"></a><span data-ttu-id="be779-102">单一登录： 事件 10819</span><span class="sxs-lookup"><span data-stu-id="be779-102">Single Sign-On: Event 10819</span></span>
## <a name="details"></a><span data-ttu-id="be779-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="be779-103">Details</span></span>  
  
|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="be779-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="be779-104">Product Name</span></span>   |                         <span data-ttu-id="be779-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="be779-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="be779-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="be779-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="be779-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="be779-107">Event ID</span></span>     |                                   <span data-ttu-id="be779-108">10819</span><span class="sxs-lookup"><span data-stu-id="be779-108">10819</span></span>                                   |
|  <span data-ttu-id="be779-109">事件源</span><span class="sxs-lookup"><span data-stu-id="be779-109">Event Source</span></span>   |                                  <span data-ttu-id="be779-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="be779-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="be779-111">组件</span><span class="sxs-lookup"><span data-stu-id="be779-111">Component</span></span>    |                                    <span data-ttu-id="be779-112">N/A</span><span class="sxs-lookup"><span data-stu-id="be779-112">N/A</span></span>                                    |
|  <span data-ttu-id="be779-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="be779-113">Symbolic Name</span></span>  |                         <span data-ttu-id="be779-114">ENTSSO_E_MAPPING_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="be779-114">ENTSSO_E_MAPPING_CONFLICT</span></span>                         |
|  <span data-ttu-id="be779-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="be779-115">Message Text</span></span>   | <span data-ttu-id="be779-116">由于存在映射冲突，因此未更新外部帐户。</span><span class="sxs-lookup"><span data-stu-id="be779-116">The external account was not updated because there is a mapping conflict.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="be779-117">解释</span><span class="sxs-lookup"><span data-stu-id="be779-117">Explanation</span></span>  
 <span data-ttu-id="be779-118">由于存在映射冲突，因此未更新外部帐户。</span><span class="sxs-lookup"><span data-stu-id="be779-118">The external account was not updated because there is a mapping conflict.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be779-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="be779-119">User Action</span></span>  
 <span data-ttu-id="be779-120">如果这是预期的行为，则不需要执行任何操作，此消息只是提供信息。</span><span class="sxs-lookup"><span data-stu-id="be779-120">If this is expected behavior then no action is required, this message is informational only.</span></span> <span data-ttu-id="be779-121">若要允许映射冲突，请对应用程序进行相应配置。</span><span class="sxs-lookup"><span data-stu-id="be779-121">If mapping conflicts should be allowed then configure the application accordingly.</span></span>  
  
 <span data-ttu-id="be779-122">有关映射冲突的详细信息，请参阅**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="be779-122">For more information on mapping conflicts, see **Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>