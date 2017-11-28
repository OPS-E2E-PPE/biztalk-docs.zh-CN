---
title: "配置跨字段验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f0c6ae8-0b8a-4826-9dfb-bf27e5ff7fa6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bde88ac82d69cdaa0dec7513e294953b7164b56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-cross-field-validation"></a><span data-ttu-id="a4670-102">配置跨字段验证</span><span class="sxs-lookup"><span data-stu-id="a4670-102">Configuring Cross-Field Validation</span></span>
<span data-ttu-id="a4670-103">本主题介绍如何对 EDI 编码消息中的事务集数据元素启用跨字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="a4670-103">This topic describes how to enable cross field/segment validation on transaction-set data elements in EDI-encoded messages.</span></span> <span data-ttu-id="a4670-104">为此，你需要执行两个设置：</span><span class="sxs-lookup"><span data-stu-id="a4670-104">To do so, you need to make two settings:</span></span>  
  
-   <span data-ttu-id="a4670-105">设置 EDI 架构的批注中的跨字段验证标志。</span><span class="sxs-lookup"><span data-stu-id="a4670-105">Set the cross-field validation flag in an annotation of the EDI schema.</span></span> <span data-ttu-id="a4670-106">对于 X12 或 HIPAA 架构，这是**X12ConditionDesignator_Check**标志。</span><span class="sxs-lookup"><span data-stu-id="a4670-106">For X12 or HIPAA schemas, this is the **X12ConditionDesignator_Check** flag.</span></span> <span data-ttu-id="a4670-107">对于 EDIFACT 架构，这是**EdifactDependencyRule_Check**标志。</span><span class="sxs-lookup"><span data-stu-id="a4670-107">For EDIFACT schemas, this is the **EdifactDependencyRule_Check** flag.</span></span>  
  
-   <span data-ttu-id="a4670-108">在协议属性中启用 EDI 类型验证。</span><span class="sxs-lookup"><span data-stu-id="a4670-108">Enable EDI-type validation in the agreement properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4670-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="a4670-109">Prerequisites</span></span>  
 <span data-ttu-id="a4670-110">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a4670-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="configuring-cross-field-validation"></a><span data-ttu-id="a4670-111">配置跨字段验证</span><span class="sxs-lookup"><span data-stu-id="a4670-111">Configuring Cross-Field Validation</span></span>  
  
1.  <span data-ttu-id="a4670-112">在 BizTalk 编辑器中打开你的架构。</span><span class="sxs-lookup"><span data-stu-id="a4670-112">Open your schema in BizTalk Editor.</span></span>  
  
2.  <span data-ttu-id="a4670-113">对于 X12 或 HIPAA 架构，查找**X12ConditionDesignator_Check**中的应用程序信息部分中的架构批注的标志。</span><span class="sxs-lookup"><span data-stu-id="a4670-113">For an X12 or HIPAA schema, find the **X12ConditionDesignator_Check** flag in an annotation in the appinfo section of the schema.</span></span> <span data-ttu-id="a4670-114">将其设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="a4670-114">Set it to **Yes**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4670-115">设置标志 X12ConditionDesignator_Check**是**无法执行从 BizTalk 架构编辑器。</span><span class="sxs-lookup"><span data-stu-id="a4670-115">Setting the flag X12ConditionDesignator_Check to **Yes** cannot be performed from BizTalk Schema Editor.</span></span> <span data-ttu-id="a4670-116">若要设置该标记，必须在记事本或类似的文本编辑器中打开它并进行编辑，然后保存架构文件 (.xsd)。</span><span class="sxs-lookup"><span data-stu-id="a4670-116">For setting the flag, you will have to open it in a notepad or similar text editor, edit, and then save the schema file (.xsd).</span></span>  
  
3.  <span data-ttu-id="a4670-117">对于 EDIFACT 架构，查找**EdifactDependencyRule_Check**批注中的架构的 appinfo 部分中的标志。</span><span class="sxs-lookup"><span data-stu-id="a4670-117">For an EDIFACT schema, find the **EdifactDependencyRule_Check** flag in the annotation in the appinfo section of the schema.</span></span> <span data-ttu-id="a4670-118">将其设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="a4670-118">Set it to **Yes**.</span></span>  
  
4.  <span data-ttu-id="a4670-119">对于适用的架构段，指定适用的关系条件（X12 和 HIPAA）或依赖规则 (EDIFACT)。</span><span class="sxs-lookup"><span data-stu-id="a4670-119">For the applicable segments of the schema, specify the relational conditions (X12 and HIPAA) or dependency rules (EDIFACT) that apply.</span></span> <span data-ttu-id="a4670-120">有关详细信息，请参阅[交叉字段段验证](../core/cross-field-segment-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="a4670-120">For more information, see [Cross Field-Segment Validation](../core/cross-field-segment-validation.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4670-121">跨字段验证条件或规则是针对 EDI 架构中的段输入的。</span><span class="sxs-lookup"><span data-stu-id="a4670-121">A cross-field validation condition or rule is entered for a segment in an EDI schema.</span></span> <span data-ttu-id="a4670-122">如果针对数据元素（而非段）输入跨字段验证规则，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将在执行架构验证时生成警告。</span><span class="sxs-lookup"><span data-stu-id="a4670-122">If you enter a cross-field validation rule for a data element, rather than a segment, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a warning when schema validation is performed.</span></span>  
  
5.  <span data-ttu-id="a4670-123">在**验证**页 (下**事务设置设置**部分) 的单向协议选项卡**协议属性**相关协议的对话框中请确保**EDI 类型验证**选择属性。</span><span class="sxs-lookup"><span data-stu-id="a4670-123">In the **Validation** page (under the **Transaction Set Settings** section) of the one-way agreement tab of the **Agreement Properties** dialog box for relevant agreement, make sure that the **EDI type Validation** property is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4670-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4670-124">See Also</span></span>  
 [<span data-ttu-id="a4670-125">开发 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="a4670-125">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)