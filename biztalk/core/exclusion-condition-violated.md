---
title: 违反排除条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e508da6-7edc-45c0-a7ab-f23337dc1b54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a69740d9d5f5514ee3fadcb76a11fe760729ca1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388292"
---
# <a name="exclusion-condition-violated"></a><span data-ttu-id="9b162-102">违反排除条件</span><span class="sxs-lookup"><span data-stu-id="9b162-102">Exclusion Condition Violated</span></span>
## <a name="details"></a><span data-ttu-id="9b162-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9b162-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9b162-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9b162-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9b162-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9b162-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9b162-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9b162-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9b162-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9b162-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9b162-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9b162-108">EDI</span></span> |
|    <span data-ttu-id="9b162-109">组件</span><span class="sxs-lookup"><span data-stu-id="9b162-109">Component</span></span>    |                                       <span data-ttu-id="9b162-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9b162-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="9b162-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9b162-111">Symbolic Name</span></span>  |                       <span data-ttu-id="9b162-112">X12DeExclusionConditionViolatedDescription</span><span class="sxs-lookup"><span data-stu-id="9b162-112">X12DeExclusionConditionViolatedDescription</span></span>                       |
|  <span data-ttu-id="9b162-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9b162-113">Message Text</span></span>   |       <span data-ttu-id="9b162-114">违反排除条件，请参见实例中的字段值以了解详细信息</span><span class="sxs-lookup"><span data-stu-id="9b162-114">Exclusion Condition Violated, refer to field value in instance for details</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="9b162-115">解释</span><span class="sxs-lookup"><span data-stu-id="9b162-115">Explanation</span></span>  
 <span data-ttu-id="9b162-116">此错误/警告/信息事件表明在接收端或发送端，在设计时（使用 XML 验证工具）或在运行时对 X12 交换的验证失败，因为实例中的某个分段未通过跨字段验证排除规则。</span><span class="sxs-lookup"><span data-stu-id="9b162-116">This Error/Warning/Information event indicates that validation of an X12 interchange failed either at design time (using the XML validation tool) or at run time, on either the receive side or the send side, because a segment in the instance failed a cross-field validation exclusion rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b162-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="9b162-117">User Action</span></span>  
 <span data-ttu-id="9b162-118">若要解决此错误，请确保更改未通过排除规则的该分段，以便该分段通过跨字段验证，然后再次运行验证过程。</span><span class="sxs-lookup"><span data-stu-id="9b162-118">To resolve this error, ensure that the segment that failed the exclusion rule is changed so that it passes cross-field validation, and then run the validation process again.</span></span>