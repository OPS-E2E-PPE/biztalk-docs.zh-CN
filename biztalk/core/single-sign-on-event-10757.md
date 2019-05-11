---
title: 单一登录：Event 10757 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f62cdb2cbf0e5c3ba3477fdfc79376d1c22d3d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307715"
---
# <a name="single-sign-on-event-10757"></a><span data-ttu-id="755ff-102">单一登录：事件 10757</span><span class="sxs-lookup"><span data-stu-id="755ff-102">Single Sign-On: Event 10757</span></span>
## <a name="details"></a><span data-ttu-id="755ff-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="755ff-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="755ff-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="755ff-104">Product Name</span></span>   |                                  <span data-ttu-id="755ff-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="755ff-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="755ff-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="755ff-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="755ff-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="755ff-107">Event ID</span></span>     |                                            <span data-ttu-id="755ff-108">10757</span><span class="sxs-lookup"><span data-stu-id="755ff-108">10757</span></span>                                             |
|  <span data-ttu-id="755ff-109">事件源</span><span class="sxs-lookup"><span data-stu-id="755ff-109">Event Source</span></span>   |                                            <span data-ttu-id="755ff-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="755ff-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="755ff-111">组件</span><span class="sxs-lookup"><span data-stu-id="755ff-111">Component</span></span>    |                                             <span data-ttu-id="755ff-112">不可用</span><span class="sxs-lookup"><span data-stu-id="755ff-112">N/A</span></span>                                              |
|  <span data-ttu-id="755ff-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="755ff-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="755ff-114">ENTSSO_E_NO_MAPPING</span><span class="sxs-lookup"><span data-stu-id="755ff-114">ENTSSO_E_NO_MAPPING</span></span>                                      |
|  <span data-ttu-id="755ff-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="755ff-115">Message Text</span></span>   | <span data-ttu-id="755ff-116">映射不存在。</span><span class="sxs-lookup"><span data-stu-id="755ff-116">The mapping does not exist.</span></span> <span data-ttu-id="755ff-117">配置存储应用程序的配置信息尚未设置。</span><span class="sxs-lookup"><span data-stu-id="755ff-117">For Config Store applications, the config info has not been set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="755ff-118">解释</span><span class="sxs-lookup"><span data-stu-id="755ff-118">Explanation</span></span>  
 <span data-ttu-id="755ff-119">如果这是个人或组类型的应用程序，则该映射不存在。</span><span class="sxs-lookup"><span data-stu-id="755ff-119">If this is an Individual or Group type application, then the mapping does not exist.</span></span>  
  
 <span data-ttu-id="755ff-120">如果这是配置存储区的应用程序，则尚未设置的配置数据。</span><span class="sxs-lookup"><span data-stu-id="755ff-120">If this is a Config Store application, then the configuration data has not been set.</span></span> <span data-ttu-id="755ff-121">这可能已重新初始化 SSO 数据库，但 BizTalk 管理数据库已不是，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="755ff-121">This can occur when the SSO database has been reinitialized but the BizTalk Management database has not, or vice versa.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="755ff-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="755ff-122">User Action</span></span>  
 <span data-ttu-id="755ff-123">如果这是个人或组类型的应用程序，创建所需的映射。</span><span class="sxs-lookup"><span data-stu-id="755ff-123">If this is an Individual or Group type application, create the desired mapping.</span></span> <span data-ttu-id="755ff-124">有关详细信息，请参阅[如何创建用户映射](../core/how-to-create-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="755ff-124">For more information, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>