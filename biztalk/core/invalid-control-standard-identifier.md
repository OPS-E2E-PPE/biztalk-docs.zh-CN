---
title: 控制标准标识符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d2b5a54-7f29-49c9-8bcf-a5b4b6d07ad3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cadbb2ed9458199433b62ecb918668fda8a1def0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966230"
---
# <a name="invalid-control-standard-identifier"></a><span data-ttu-id="652c5-102">控制标准标识符无效</span><span class="sxs-lookup"><span data-stu-id="652c5-102">Invalid Control Standard Identifier</span></span>
## <a name="details"></a><span data-ttu-id="652c5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="652c5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="652c5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="652c5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="652c5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="652c5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="652c5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="652c5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="652c5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="652c5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="652c5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="652c5-108"> EDI</span></span> |
|    <span data-ttu-id="652c5-109">组件</span><span class="sxs-lookup"><span data-stu-id="652c5-109">Component</span></span>    |                                       <span data-ttu-id="652c5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="652c5-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="652c5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="652c5-111">Symbolic Name</span></span>  |                   <span data-ttu-id="652c5-112">X12Ta1InvalidControlStandardIdentifierDescription</span><span class="sxs-lookup"><span data-stu-id="652c5-112">X12Ta1InvalidControlStandardIdentifierDescription</span></span>                    |
|  <span data-ttu-id="652c5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="652c5-113">Message Text</span></span>   |                          <span data-ttu-id="652c5-114">控制标准标识符无效</span><span class="sxs-lookup"><span data-stu-id="652c5-114">Invalid Control Standard Identifier</span></span>                           |
  
## <a name="explanation"></a><span data-ttu-id="652c5-115">解释</span><span class="sxs-lookup"><span data-stu-id="652c5-115">Explanation</span></span>  
 <span data-ttu-id="652c5-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中交换控制标准标识符的值（字段 ISA11）与架构指定的枚举中的条目不匹配。</span><span class="sxs-lookup"><span data-stu-id="652c5-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the interchange control standards identifier (field ISA11) in the interchange did not match an entry in the enumeration specified by the schema.</span></span> <span data-ttu-id="652c5-117">在 BaseArtifacts.dll 中，架构为 X12ServiceSchema 或 EdifactServiceSchema。</span><span class="sxs-lookup"><span data-stu-id="652c5-117">The schema is the X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="652c5-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="652c5-118">User Action</span></span>  
 <span data-ttu-id="652c5-119">若要解决此错误，请确保交换中使用的交换控制标准标识符与 ISA11 字段的枚举中的条目相匹配，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="652c5-119">To resolve this error, make sure that the interchange control standards identifier used in the interchange matches an entry in the enumeration for the ISA11 field, and then have the interchange resent.</span></span>