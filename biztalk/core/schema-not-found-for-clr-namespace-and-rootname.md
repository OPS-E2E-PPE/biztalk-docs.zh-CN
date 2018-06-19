---
title: CLR Namespace 和 rootName 找不到架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db283d81-1cb0-460d-ace4-49a91ceb4a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06db4a89803b8386ccbb45372b72423e83c6ff7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269397"
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a><span data-ttu-id="a5650-102">找不到 CLR 命名空间和 rootName 的架构</span><span class="sxs-lookup"><span data-stu-id="a5650-102">Schema not found for CLR Namespace and rootName</span></span>
## <a name="details"></a><span data-ttu-id="a5650-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a5650-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5650-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a5650-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a5650-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a5650-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a5650-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a5650-106">Event ID</span></span>|-|  
|<span data-ttu-id="a5650-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a5650-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a5650-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a5650-108"> EDI</span></span>|  
|<span data-ttu-id="a5650-109">组件</span><span class="sxs-lookup"><span data-stu-id="a5650-109">Component</span></span>|<span data-ttu-id="a5650-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="a5650-110">EDI Engine</span></span>|  
|<span data-ttu-id="a5650-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a5650-111">Symbolic Name</span></span>|<span data-ttu-id="a5650-112">SchemaNotFoundForCLRAndRN</span><span class="sxs-lookup"><span data-stu-id="a5650-112">SchemaNotFoundForCLRAndRN</span></span>|  
|<span data-ttu-id="a5650-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="a5650-113">Message Text</span></span>|<span data-ttu-id="a5650-114">找不到 CLR Namespace 架构 = {0} 和 rootName = {1}</span><span class="sxs-lookup"><span data-stu-id="a5650-114">Schema not found for CLR Namespace = {0} and rootName = {1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5650-115">解释</span><span class="sxs-lookup"><span data-stu-id="a5650-115">Explanation</span></span>  
 <span data-ttu-id="a5650-116">此错误/警告/信息事件表明接收管道使用与交换关联的根名称以及与为交换解析的参与方关联的命名空间无法找到文档架构。</span><span class="sxs-lookup"><span data-stu-id="a5650-116">This Error/Warning/Information event indicates that the receive pipeline could not find the document schema using the root name associated with the interchange and the namespace associated with the party that was resolved for the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5650-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="a5650-117">User Action</span></span>  
 <span data-ttu-id="a5650-118">若要解决此错误，请确保从交换中获取的根名称以及从解析后的参与方的属性中确定的命名空间都与部署的架构相对应。</span><span class="sxs-lookup"><span data-stu-id="a5650-118">To resolve this error, ensure that the root name taken from the interchange and the namespace determined from the properties of the resolved party correspond together to a deployed schema.</span></span> <span data-ttu-id="a5650-119">BizTalk 从交换中的文档类型和版本中确定根名称。</span><span class="sxs-lookup"><span data-stu-id="a5650-119">BizTalk determines the root name from the document type and version in the interchange.</span></span> <span data-ttu-id="a5650-120">BizTalk 确定中 （对于默认架构） 的默认目标 Namespace 字段或"启用自定义事务设置定义"网格 （对自定义架构） 的交换处理属性中的架构。</span><span class="sxs-lookup"><span data-stu-id="a5650-120">BizTalk determines the schema from the Default Target Namespace field (for default schemas) or the "Enable custom transaction set definitions" grid (for custom schemas) in the Interchange Processing Properties.</span></span>