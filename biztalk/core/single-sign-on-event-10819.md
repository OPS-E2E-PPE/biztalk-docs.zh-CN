---
title: 单一登录：Event 10819 | Microsoft Docs
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
ms.openlocfilehash: d1f338b78cd9c19b337b83eb829736cb7e81612e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396640"
---
# <a name="single-sign-on-event-10819"></a><span data-ttu-id="4037e-102">单一登录：事件 10819</span><span class="sxs-lookup"><span data-stu-id="4037e-102">Single Sign-On: Event 10819</span></span>
## <a name="details"></a><span data-ttu-id="4037e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4037e-103">Details</span></span>  
  
|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="4037e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4037e-104">Product Name</span></span>   |                         <span data-ttu-id="4037e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="4037e-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="4037e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="4037e-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="4037e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4037e-107">Event ID</span></span>     |                                   <span data-ttu-id="4037e-108">10819</span><span class="sxs-lookup"><span data-stu-id="4037e-108">10819</span></span>                                   |
|  <span data-ttu-id="4037e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="4037e-109">Event Source</span></span>   |                                  <span data-ttu-id="4037e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4037e-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="4037e-111">组件</span><span class="sxs-lookup"><span data-stu-id="4037e-111">Component</span></span>    |                                    <span data-ttu-id="4037e-112">不可用</span><span class="sxs-lookup"><span data-stu-id="4037e-112">N/A</span></span>                                    |
|  <span data-ttu-id="4037e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="4037e-113">Symbolic Name</span></span>  |                         <span data-ttu-id="4037e-114">ENTSSO_E_MAPPING_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="4037e-114">ENTSSO_E_MAPPING_CONFLICT</span></span>                         |
|  <span data-ttu-id="4037e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="4037e-115">Message Text</span></span>   | <span data-ttu-id="4037e-116">因为存在映射冲突未更新外部帐户。</span><span class="sxs-lookup"><span data-stu-id="4037e-116">The external account was not updated because there is a mapping conflict.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4037e-117">解释</span><span class="sxs-lookup"><span data-stu-id="4037e-117">Explanation</span></span>  
 <span data-ttu-id="4037e-118">因为存在映射冲突未更新外部帐户。</span><span class="sxs-lookup"><span data-stu-id="4037e-118">The external account was not updated because there is a mapping conflict.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4037e-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="4037e-119">User Action</span></span>  
 <span data-ttu-id="4037e-120">如果这是预期的行为，则不不需要任何操作，此消息仅供参考。</span><span class="sxs-lookup"><span data-stu-id="4037e-120">If this is expected behavior then no action is required, this message is informational only.</span></span> <span data-ttu-id="4037e-121">如果应允许映射冲突然后相应地配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="4037e-121">If mapping conflicts should be allowed then configure the application accordingly.</span></span>  
  
 <span data-ttu-id="4037e-122">有关映射冲突的详细信息，请参阅**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="4037e-122">For more information on mapping conflicts, see **Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>