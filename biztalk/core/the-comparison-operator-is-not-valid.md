---
title: "比较运算符不是有效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8383230d-9bf6-4bc5-9300-4cfd0ad38f28
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12652fbd59fde08d8321c6fdd85bb0998ce8ccc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-comparison-operator-is-not-valid"></a><span data-ttu-id="d417d-102">比较运算符无效</span><span class="sxs-lookup"><span data-stu-id="d417d-102">The comparison operator is not valid</span></span>
## <a name="details"></a><span data-ttu-id="d417d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d417d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d417d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d417d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d417d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d417d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d417d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d417d-106">Event ID</span></span>|-|  
|<span data-ttu-id="d417d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d417d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d417d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d417d-108"> EDI</span></span>|  
|<span data-ttu-id="d417d-109">组件</span><span class="sxs-lookup"><span data-stu-id="d417d-109">Component</span></span>|<span data-ttu-id="d417d-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="d417d-110">Batching Engine</span></span>|  
|<span data-ttu-id="d417d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d417d-111">Symbolic Name</span></span>|<span data-ttu-id="d417d-112">InvalidComparisonOperator</span><span class="sxs-lookup"><span data-stu-id="d417d-112">InvalidComparisonOperator</span></span>|  
|<span data-ttu-id="d417d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d417d-113">Message Text</span></span>|<span data-ttu-id="d417d-114">比较运算符无效。</span><span class="sxs-lookup"><span data-stu-id="d417d-114">The comparison operator is not valid.</span></span> <span data-ttu-id="d417d-115">异常消息 = {0}</span><span class="sxs-lookup"><span data-stu-id="d417d-115">Exception message = {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d417d-116">解释</span><span class="sxs-lookup"><span data-stu-id="d417d-116">Explanation</span></span>  
 <span data-ttu-id="d417d-117">此错误/警告/信息事件指示输入批处理筛选器对话框中的行的比较运算符对属性和值无效。</span><span class="sxs-lookup"><span data-stu-id="d417d-117">This Error/Warning/Information event indicates that the comparison operator entered for a row of the Batch Filter dialog box was not valid for the property and the value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d417d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="d417d-118">User Action</span></span>  
 <span data-ttu-id="d417d-119">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="d417d-119">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="d417d-120">确保为“批处理筛选器”网格中的行输入的比较运算符对于该属性和值来说无效。</span><span class="sxs-lookup"><span data-stu-id="d417d-120">Make sure that the comparison operators entered for rows in the Batch Filter grid are valid for the property and the value.</span></span>