---
title: 找不到 CLR Namespace 和 rootName 的架构 |Microsoft Docs
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
ms.openlocfilehash: 1f4a854357a8f1e217273c1a3380a446dcbe7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396927"
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a><span data-ttu-id="279dc-102">找不到 CLR Namespace 和 rootName 的架构</span><span class="sxs-lookup"><span data-stu-id="279dc-102">Schema not found for CLR Namespace and rootName</span></span>
## <a name="details"></a><span data-ttu-id="279dc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="279dc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="279dc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="279dc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="279dc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="279dc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="279dc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="279dc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="279dc-107">事件源</span><span class="sxs-lookup"><span data-stu-id="279dc-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="279dc-108">EDI</span><span class="sxs-lookup"><span data-stu-id="279dc-108">EDI</span></span> |
|    <span data-ttu-id="279dc-109">组件</span><span class="sxs-lookup"><span data-stu-id="279dc-109">Component</span></span>    |                                       <span data-ttu-id="279dc-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="279dc-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="279dc-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="279dc-111">Symbolic Name</span></span>  |                               <span data-ttu-id="279dc-112">SchemaNotFoundForCLRAndRN</span><span class="sxs-lookup"><span data-stu-id="279dc-112">SchemaNotFoundForCLRAndRN</span></span>                                |
|  <span data-ttu-id="279dc-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="279dc-113">Message Text</span></span>   |              <span data-ttu-id="279dc-114">找不到 CLR Namespace 架构 ={0}和 rootName = {1}</span><span class="sxs-lookup"><span data-stu-id="279dc-114">Schema not found for CLR Namespace = {0} and rootName = {1}</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="279dc-115">解释</span><span class="sxs-lookup"><span data-stu-id="279dc-115">Explanation</span></span>  
 <span data-ttu-id="279dc-116">此错误/警告/信息事件表明接收管道找不到使用与交换关联的根名称和命名空间与已为交换解析的参与方相关联的文档架构。</span><span class="sxs-lookup"><span data-stu-id="279dc-116">This Error/Warning/Information event indicates that the receive pipeline could not find the document schema using the root name associated with the interchange and the namespace associated with the party that was resolved for the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="279dc-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="279dc-117">User Action</span></span>  
 <span data-ttu-id="279dc-118">若要解决此错误，请确保，从交换中获取的根名称和命名空间解析的参与方的属性从确定对应一起部署架构。</span><span class="sxs-lookup"><span data-stu-id="279dc-118">To resolve this error, ensure that the root name taken from the interchange and the namespace determined from the properties of the resolved party correspond together to a deployed schema.</span></span> <span data-ttu-id="279dc-119">BizTalk 确定在文档类型和交换中的版本中的根名称。</span><span class="sxs-lookup"><span data-stu-id="279dc-119">BizTalk determines the root name from the document type and version in the interchange.</span></span> <span data-ttu-id="279dc-120">BizTalk 确定在将架构从默认目标 Namespace 字段 （对于默认架构） 或"启用自定义事务集定义"网格 （适用于自定义架构） 中交换处理属性。</span><span class="sxs-lookup"><span data-stu-id="279dc-120">BizTalk determines the schema from the Default Target Namespace field (for default schemas) or the "Enable custom transaction set definitions" grid (for custom schemas) in the Interchange Processing Properties.</span></span>