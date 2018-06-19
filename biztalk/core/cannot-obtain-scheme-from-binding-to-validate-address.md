---
title: 无法从绑定来验证地址获取方案 |Microsoft 文档
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
ms.openlocfilehash: c952e967a391011bbd887513d58e426d90d325a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230957"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a><span data-ttu-id="40348-102">无法从绑定来验证地址获取方案</span><span class="sxs-lookup"><span data-stu-id="40348-102">Cannot obtain scheme from binding to validate address</span></span>
## <a name="details"></a><span data-ttu-id="40348-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="40348-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="40348-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="40348-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="40348-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="40348-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="40348-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="40348-106">Event ID</span></span>|<span data-ttu-id="40348-107">0</span><span class="sxs-lookup"><span data-stu-id="40348-107">0</span></span>|  
|<span data-ttu-id="40348-108">事件源</span><span class="sxs-lookup"><span data-stu-id="40348-108">Event Source</span></span>|<span data-ttu-id="40348-109">0</span><span class="sxs-lookup"><span data-stu-id="40348-109">0</span></span>|  
|<span data-ttu-id="40348-110">组件</span><span class="sxs-lookup"><span data-stu-id="40348-110">Component</span></span>|<span data-ttu-id="40348-111">0</span><span class="sxs-lookup"><span data-stu-id="40348-111">0</span></span>|  
|<span data-ttu-id="40348-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="40348-112">Symbolic Name</span></span>|<span data-ttu-id="40348-113">0</span><span class="sxs-lookup"><span data-stu-id="40348-113">0</span></span>|  
|<span data-ttu-id="40348-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="40348-114">Message Text</span></span>|<span data-ttu-id="40348-115">无法从绑定中获取方案以验证地址。</span><span class="sxs-lookup"><span data-stu-id="40348-115">Cannot obtain scheme from binding to validate address.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="40348-116">解释</span><span class="sxs-lookup"><span data-stu-id="40348-116">Explanation</span></span>  
 <span data-ttu-id="40348-117">已经指定的传输绑定元素没有方案。</span><span class="sxs-lookup"><span data-stu-id="40348-117">The transport binding element that has been specified does not have a scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40348-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="40348-118">User Action</span></span>  
 <span data-ttu-id="40348-119">确保传输绑定元素拥有有效的方案，或选择了有效的传输绑定元素。</span><span class="sxs-lookup"><span data-stu-id="40348-119">Make sure that the transport binding element has a valid scheme, or that a valid transport binding element is selected.</span></span> <span data-ttu-id="40348-120">如果使用自定义绑定，请确保指定了有效的传输绑定元素。</span><span class="sxs-lookup"><span data-stu-id="40348-120">If using a custom binding, make sure a valid transport binding element is specified.</span></span>  
  
 <span data-ttu-id="40348-121">有关其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="40348-121">For additional information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="40348-122">配置 WCF 自定义适配器</span><span class="sxs-lookup"><span data-stu-id="40348-122">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)