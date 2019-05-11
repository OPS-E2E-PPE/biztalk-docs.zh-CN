---
title: 无法从绑定以验证地址获取方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d42116dff2ad72b4d076b7c6e5303f1d8636e9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358063"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a><span data-ttu-id="f225d-102">无法从绑定以验证地址获取方案</span><span class="sxs-lookup"><span data-stu-id="f225d-102">Cannot obtain scheme from binding to validate address</span></span>
## <a name="details"></a><span data-ttu-id="f225d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f225d-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f225d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f225d-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f225d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f225d-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f225d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f225d-106">Event ID</span></span>     |                                         <span data-ttu-id="f225d-107">0</span><span class="sxs-lookup"><span data-stu-id="f225d-107">0</span></span>                                          |
|  <span data-ttu-id="f225d-108">事件源</span><span class="sxs-lookup"><span data-stu-id="f225d-108">Event Source</span></span>   |                                         <span data-ttu-id="f225d-109">0</span><span class="sxs-lookup"><span data-stu-id="f225d-109">0</span></span>                                          |
|    <span data-ttu-id="f225d-110">组件</span><span class="sxs-lookup"><span data-stu-id="f225d-110">Component</span></span>    |                                         <span data-ttu-id="f225d-111">0</span><span class="sxs-lookup"><span data-stu-id="f225d-111">0</span></span>                                          |
|  <span data-ttu-id="f225d-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="f225d-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f225d-113">0</span><span class="sxs-lookup"><span data-stu-id="f225d-113">0</span></span>                                          |
|  <span data-ttu-id="f225d-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="f225d-114">Message Text</span></span>   |               <span data-ttu-id="f225d-115">无法从绑定以验证地址获取方案。</span><span class="sxs-lookup"><span data-stu-id="f225d-115">Cannot obtain scheme from binding to validate address.</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="f225d-116">解释</span><span class="sxs-lookup"><span data-stu-id="f225d-116">Explanation</span></span>  
 <span data-ttu-id="f225d-117">已指定的传输绑定元素没有一种方案。</span><span class="sxs-lookup"><span data-stu-id="f225d-117">The transport binding element that has been specified does not have a scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f225d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="f225d-118">User Action</span></span>  
 <span data-ttu-id="f225d-119">请确保传输绑定元素拥有有效的方案，或选择一个有效的传输绑定元素。</span><span class="sxs-lookup"><span data-stu-id="f225d-119">Make sure that the transport binding element has a valid scheme, or that a valid transport binding element is selected.</span></span> <span data-ttu-id="f225d-120">如果使用自定义绑定时，请确保指定有效的传输绑定元素。</span><span class="sxs-lookup"><span data-stu-id="f225d-120">If using a custom binding, make sure a valid transport binding element is specified.</span></span>  
  
 <span data-ttu-id="f225d-121">有关其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="f225d-121">For additional information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="f225d-122">配置 WCF-Custom 适配器</span><span class="sxs-lookup"><span data-stu-id="f225d-122">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)