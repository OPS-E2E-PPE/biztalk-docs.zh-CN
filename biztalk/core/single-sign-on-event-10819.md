---
title: 单一登录： 事件 10819 |Microsoft 文档
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
ms.openlocfilehash: 4f2a98586d9c139674c64db6ca03aaa6abd6ba6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276429"
---
# <a name="single-sign-on-event-10819"></a><span data-ttu-id="e92bf-102">单一登录： 事件 10819</span><span class="sxs-lookup"><span data-stu-id="e92bf-102">Single Sign-On: Event 10819</span></span>
## <a name="details"></a><span data-ttu-id="e92bf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e92bf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e92bf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e92bf-104">Product Name</span></span>|<span data-ttu-id="e92bf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e92bf-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e92bf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e92bf-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e92bf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e92bf-107">Event ID</span></span>|<span data-ttu-id="e92bf-108">10819</span><span class="sxs-lookup"><span data-stu-id="e92bf-108">10819</span></span>|  
|<span data-ttu-id="e92bf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e92bf-109">Event Source</span></span>|<span data-ttu-id="e92bf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e92bf-110">ENTSSO</span></span>|  
|<span data-ttu-id="e92bf-111">组件</span><span class="sxs-lookup"><span data-stu-id="e92bf-111">Component</span></span>|<span data-ttu-id="e92bf-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e92bf-112">N/A</span></span>|  
|<span data-ttu-id="e92bf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e92bf-113">Symbolic Name</span></span>|<span data-ttu-id="e92bf-114">ENTSSO_E_MAPPING_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="e92bf-114">ENTSSO_E_MAPPING_CONFLICT</span></span>|  
|<span data-ttu-id="e92bf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e92bf-115">Message Text</span></span>|<span data-ttu-id="e92bf-116">由于存在映射冲突，因此未更新外部帐户。</span><span class="sxs-lookup"><span data-stu-id="e92bf-116">The external account was not updated because there is a mapping conflict.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e92bf-117">解释</span><span class="sxs-lookup"><span data-stu-id="e92bf-117">Explanation</span></span>  
 <span data-ttu-id="e92bf-118">由于存在映射冲突，因此未更新外部帐户。</span><span class="sxs-lookup"><span data-stu-id="e92bf-118">The external account was not updated because there is a mapping conflict.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e92bf-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="e92bf-119">User Action</span></span>  
 <span data-ttu-id="e92bf-120">如果这是预期的行为，则不需要执行任何操作，此消息只是提供信息。</span><span class="sxs-lookup"><span data-stu-id="e92bf-120">If this is expected behavior then no action is required, this message is informational only.</span></span> <span data-ttu-id="e92bf-121">若要允许映射冲突，请对应用程序进行相应配置。</span><span class="sxs-lookup"><span data-stu-id="e92bf-121">If mapping conflicts should be allowed then configure the application accordingly.</span></span>  
  
 <span data-ttu-id="e92bf-122">有关映射冲突的详细信息，请参阅**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="e92bf-122">For more information on mapping conflicts, see **Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>