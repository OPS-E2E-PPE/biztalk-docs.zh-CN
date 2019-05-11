---
title: 单一登录：Event 10753 | Microsoft Docs
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
ms.openlocfilehash: ca0c0066e1643ec6cc84f19eaf1ca5ece9822e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307793"
---
# <a name="single-sign-on-event-10753"></a><span data-ttu-id="b41f4-102">单一登录：事件 10753</span><span class="sxs-lookup"><span data-stu-id="b41f4-102">Single Sign-On: Event 10753</span></span>
## <a name="details"></a><span data-ttu-id="b41f4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b41f4-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="b41f4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b41f4-104">Product Name</span></span>   |                 <span data-ttu-id="b41f4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b41f4-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="b41f4-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b41f4-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="b41f4-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b41f4-107">Event ID</span></span>     |                           <span data-ttu-id="b41f4-108">10753</span><span class="sxs-lookup"><span data-stu-id="b41f4-108">10753</span></span>                            |
|  <span data-ttu-id="b41f4-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b41f4-109">Event Source</span></span>   |                           <span data-ttu-id="b41f4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b41f4-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="b41f4-111">组件</span><span class="sxs-lookup"><span data-stu-id="b41f4-111">Component</span></span>    |                            <span data-ttu-id="b41f4-112">不可用</span><span class="sxs-lookup"><span data-stu-id="b41f4-112">N/A</span></span>                             |
|  <span data-ttu-id="b41f4-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b41f4-113">Symbolic Name</span></span>  |                  <span data-ttu-id="b41f4-114">ENTSSO_E_MAPPING_EXISTS</span><span class="sxs-lookup"><span data-stu-id="b41f4-114">ENTSSO_E_MAPPING_EXISTS</span></span>                   |
|  <span data-ttu-id="b41f4-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b41f4-115">Message Text</span></span>   |                <span data-ttu-id="b41f4-116">映射已存在。</span><span class="sxs-lookup"><span data-stu-id="b41f4-116">The mapping already exists.</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="b41f4-117">解释</span><span class="sxs-lookup"><span data-stu-id="b41f4-117">Explanation</span></span>  
 <span data-ttu-id="b41f4-118">此映射已经存在于已在使用中的 Windows 帐户或外部帐户。</span><span class="sxs-lookup"><span data-stu-id="b41f4-118">This mapping already exists, either on the Windows account already in use or the external account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b41f4-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="b41f4-119">User Action</span></span>  
 <span data-ttu-id="b41f4-120">检查现有映射以及想要创建的映射。</span><span class="sxs-lookup"><span data-stu-id="b41f4-120">Check the existing mappings and the mapping you are trying to create.</span></span> <span data-ttu-id="b41f4-121">如果存在所需的映射，使用它，并删除新映射。</span><span class="sxs-lookup"><span data-stu-id="b41f4-121">If the mapping you want already exists, use it and delete your new one.</span></span> <span data-ttu-id="b41f4-122">如果没有，请删除新映射并重新创建它。</span><span class="sxs-lookup"><span data-stu-id="b41f4-122">If not, delete your new one and recreate it.</span></span>