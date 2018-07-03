---
title: 条件性必需数据元素缺失 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5105c03-fa26-4c38-a276-c656f3076d5f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43ebf2ba593ad5133b93400bf0e9cb1151dc45b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978438"
---
# <a name="conditional-required-data-element-missing"></a><span data-ttu-id="c3014-102">条件性必需数据元素缺失</span><span class="sxs-lookup"><span data-stu-id="c3014-102">Conditional required data element missing</span></span>
## <a name="details"></a><span data-ttu-id="c3014-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3014-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c3014-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c3014-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c3014-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c3014-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c3014-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c3014-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c3014-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c3014-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c3014-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c3014-108"> EDI</span></span> |
|    <span data-ttu-id="c3014-109">组件</span><span class="sxs-lookup"><span data-stu-id="c3014-109">Component</span></span>    |                                       <span data-ttu-id="c3014-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c3014-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c3014-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c3014-111">Symbolic Name</span></span>  |                 <span data-ttu-id="c3014-112">X12DeConditionalRequiredDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="c3014-112">X12DeConditionalRequiredDataElementMissingDescription</span></span>                  |
|  <span data-ttu-id="c3014-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c3014-113">Message Text</span></span>   |                       <span data-ttu-id="c3014-114">条件性必需数据元素缺失</span><span class="sxs-lookup"><span data-stu-id="c3014-114">Conditional required data element missing</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="c3014-115">解释</span><span class="sxs-lookup"><span data-stu-id="c3014-115">Explanation</span></span>  
 <span data-ttu-id="c3014-116">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为交换中不存在 X12ConditionDesignatorX 规则所需的数据元素。</span><span class="sxs-lookup"><span data-stu-id="c3014-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because a data element that is required by the X12ConditionDesignatorX rule does not exist in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3014-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c3014-117">User Action</span></span>  
 <span data-ttu-id="c3014-118">此错误可能是传入的交换出现了问题，而不是 BizTalk Server 的配置或操作出现了问题。</span><span class="sxs-lookup"><span data-stu-id="c3014-118">This error is likely an issue with the incoming interchange, not with the configuration or operation of BizTalk Server.</span></span> <span data-ttu-id="c3014-119">若要解决此错误，请与交换的发送方联系并指出他们需要更改交换中使用的字符或字段 UNB1.1 中标识的字符集以便它们相匹配。</span><span class="sxs-lookup"><span data-stu-id="c3014-119">To resolve this error, contact the sender of the interchange and indicate that they need to change either the characters used in the interchange or the character set identified in field UNB1.1 so that they match.</span></span>