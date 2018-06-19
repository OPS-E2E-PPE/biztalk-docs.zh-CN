---
title: 在序列化过程根节点不放入开始元素处 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3dced7e36802dd9d9ec9620272fc8a96bd6b590
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240045"
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a><span data-ttu-id="ee83c-102">在序列化过程根节点不放入开始元素处</span><span class="sxs-lookup"><span data-stu-id="ee83c-102">During serialization root node is not placed at start element</span></span>
## <a name="details"></a><span data-ttu-id="ee83c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee83c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee83c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ee83c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ee83c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ee83c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ee83c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ee83c-106">Event ID</span></span>|-|  
|<span data-ttu-id="ee83c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ee83c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ee83c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ee83c-108"> EDI</span></span>|  
|<span data-ttu-id="ee83c-109">组件</span><span class="sxs-lookup"><span data-stu-id="ee83c-109">Component</span></span>|<span data-ttu-id="ee83c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ee83c-110">EDI Engine</span></span>|  
|<span data-ttu-id="ee83c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ee83c-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="ee83c-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="ee83c-112">Message Text</span></span>|<span data-ttu-id="ee83c-113">在序列化过程根节点不放入开始元素处</span><span class="sxs-lookup"><span data-stu-id="ee83c-113">During serialization root node is not placed at start element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ee83c-114">解释</span><span class="sxs-lookup"><span data-stu-id="ee83c-114">Explanation</span></span>  
 <span data-ttu-id="ee83c-115">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为事务集未以 ST 或 UNH 标头开头。</span><span class="sxs-lookup"><span data-stu-id="ee83c-115">This Error/Warning/Information event indicates that the receive pipeline could not process an incoming interchange because the transaction set does not start with an ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee83c-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="ee83c-116">User Action</span></span>  
 <span data-ttu-id="ee83c-117">若要解决此错误，请确保交换中的每个事务集都以 ST 段（对于 X12 交换）或 UNH 段（对于 EDIFACT 交换），然后重新提交交换。</span><span class="sxs-lookup"><span data-stu-id="ee83c-117">To resolve this error, ensure that each of the transaction sets in an interchange starts with an ST segment (for X12 interchanges) or an UNH segment (for EDIFACT interchanges), and then resubmit the interchange.</span></span>