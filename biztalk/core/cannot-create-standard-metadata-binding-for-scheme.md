---
title: 无法创建标准元数据绑定方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce441c3e-0f6e-46ed-90cf-825dbf89d910
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d45e8e983e626db3b48c4875573fd7e3a92d50e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357653"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a><span data-ttu-id="505e1-102">无法为架构创建标准元数据绑定</span><span class="sxs-lookup"><span data-stu-id="505e1-102">Cannot create standard metadata binding for scheme</span></span>
## <a name="details"></a><span data-ttu-id="505e1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="505e1-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="505e1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="505e1-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="505e1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="505e1-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="505e1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="505e1-106">Event ID</span></span>     |                                                         <span data-ttu-id="505e1-107">0</span><span class="sxs-lookup"><span data-stu-id="505e1-107">0</span></span>                                                          |
|  <span data-ttu-id="505e1-108">事件源</span><span class="sxs-lookup"><span data-stu-id="505e1-108">Event Source</span></span>   |                                                         <span data-ttu-id="505e1-109">0</span><span class="sxs-lookup"><span data-stu-id="505e1-109">0</span></span>                                                          |
|    <span data-ttu-id="505e1-110">组件</span><span class="sxs-lookup"><span data-stu-id="505e1-110">Component</span></span>    |                                                         <span data-ttu-id="505e1-111">0</span><span class="sxs-lookup"><span data-stu-id="505e1-111">0</span></span>                                                          |
|  <span data-ttu-id="505e1-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="505e1-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="505e1-113">0</span><span class="sxs-lookup"><span data-stu-id="505e1-113">0</span></span>                                                          |
|  <span data-ttu-id="505e1-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="505e1-114">Message Text</span></span>   | <span data-ttu-id="505e1-115">无法创建标准元数据绑定方案"{0}"。</span><span class="sxs-lookup"><span data-stu-id="505e1-115">Cannot create standard metadata binding for scheme "{0}".</span></span> <span data-ttu-id="505e1-116">支持的方案是 http、 https、 net.pipe 和 net.tcp</span><span class="sxs-lookup"><span data-stu-id="505e1-116">Supported schemes are http, https, net.pipe, and net.tcp</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="505e1-117">解释</span><span class="sxs-lookup"><span data-stu-id="505e1-117">Explanation</span></span>  
 <span data-ttu-id="505e1-118">此错误表示从其元数据尝试使用此服务处于不受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="505e1-118">This error indicates the service from which the metadata is trying to be consumed is not a supported scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="505e1-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="505e1-119">User Action</span></span>  
 <span data-ttu-id="505e1-120">发布具有有效的方案的元数据，然后再次运行向导，针对新的元数据位置。</span><span class="sxs-lookup"><span data-stu-id="505e1-120">Publish the metadata with a valid scheme and then run the wizard again, against the new metadata location.</span></span>  
  
 <span data-ttu-id="505e1-121">有关适配器和绑定的其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="505e1-121">For additional information on adapters and binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="505e1-122">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="505e1-122">WCF Adapters</span></span>](../core/wcf-adapters.md)