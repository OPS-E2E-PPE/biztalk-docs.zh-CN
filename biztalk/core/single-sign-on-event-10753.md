---
title: 单一登录： 事件 10753 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc43f8ffba195b7a0156a9004d140f1e3c585db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277661"
---
# <a name="single-sign-on-event-10753"></a><span data-ttu-id="1859d-102">单一登录： 事件 10753</span><span class="sxs-lookup"><span data-stu-id="1859d-102">Single Sign-On: Event 10753</span></span>
## <a name="details"></a><span data-ttu-id="1859d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1859d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1859d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1859d-104">Product Name</span></span>|<span data-ttu-id="1859d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1859d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1859d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1859d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1859d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1859d-107">Event ID</span></span>|<span data-ttu-id="1859d-108">10753</span><span class="sxs-lookup"><span data-stu-id="1859d-108">10753</span></span>|  
|<span data-ttu-id="1859d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1859d-109">Event Source</span></span>|<span data-ttu-id="1859d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1859d-110">ENTSSO</span></span>|  
|<span data-ttu-id="1859d-111">组件</span><span class="sxs-lookup"><span data-stu-id="1859d-111">Component</span></span>|<span data-ttu-id="1859d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="1859d-112">N/A</span></span>|  
|<span data-ttu-id="1859d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1859d-113">Symbolic Name</span></span>|<span data-ttu-id="1859d-114">ENTSSO_E_MAPPING_EXISTS</span><span class="sxs-lookup"><span data-stu-id="1859d-114">ENTSSO_E_MAPPING_EXISTS</span></span>|  
|<span data-ttu-id="1859d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1859d-115">Message Text</span></span>|<span data-ttu-id="1859d-116">映射已存在。</span><span class="sxs-lookup"><span data-stu-id="1859d-116">The mapping already exists.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1859d-117">解释</span><span class="sxs-lookup"><span data-stu-id="1859d-117">Explanation</span></span>  
 <span data-ttu-id="1859d-118">此映射已经存在于已经使用的 Windows 帐户或外部帐户。</span><span class="sxs-lookup"><span data-stu-id="1859d-118">This mapping already exists, either on the Windows account already in use or the external account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1859d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="1859d-119">User Action</span></span>  
 <span data-ttu-id="1859d-120">检查现有映射和您尝试创建的映射。</span><span class="sxs-lookup"><span data-stu-id="1859d-120">Check the existing mappings and the mapping you are trying to create.</span></span> <span data-ttu-id="1859d-121">如果您需要的映射已经存在，则使用该映射并删除新映射。</span><span class="sxs-lookup"><span data-stu-id="1859d-121">If the mapping you want already exists, use it and delete your new one.</span></span> <span data-ttu-id="1859d-122">如果不存在，则删除新映射并重新创建。</span><span class="sxs-lookup"><span data-stu-id="1859d-122">If not, delete your new one and recreate it.</span></span>