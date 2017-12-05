---
title: "命名约定的 SWIFT 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14245a185adcccdfb1f2ea2ed9382820fb84177e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="swift-schema-naming-conventions"></a><span data-ttu-id="95acb-102">SWIFT 架构的命名约定</span><span class="sxs-lookup"><span data-stu-id="95acb-102">SWIFT Schema Naming Conventions</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="95acb-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括用于互联网协会用于使用 BizTalk 编辑器创建的全球 Interbank 财务电信 (SWIFT) FIN 消息的架构。</span><span class="sxs-lookup"><span data-stu-id="95acb-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes schemas for Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages that were created using BizTalk Editor.</span></span> <span data-ttu-id="95acb-104">这些架构符合在整个以下约定：</span><span class="sxs-lookup"><span data-stu-id="95acb-104">These schemas conform to the following conventions throughout:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95acb-105">所有架构都是版本控制的。</span><span class="sxs-lookup"><span data-stu-id="95acb-105">All schemas are versioned.</span></span> <span data-ttu-id="95acb-106">若要查看版本，请打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后右键单击解决方案资源管理器中的架构。</span><span class="sxs-lookup"><span data-stu-id="95acb-106">To see the version, open [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and right-click the schema in Solution Explorer.</span></span> <span data-ttu-id="95acb-107">与\<架构\>BizTalk 编辑器中，选定属性窗格中向下滚动到标准版本属性中的节点。</span><span class="sxs-lookup"><span data-stu-id="95acb-107">With the \<Schema\> node selected in BizTalk Editor, in the Properties pane scroll down to the Standard Version property.</span></span>  
  
-   <span data-ttu-id="95acb-108">每个交换架构文件的名称是 **MT*xxx*.xsd * *，其中*xxx*是 FIN 消息类型。</span><span class="sxs-lookup"><span data-stu-id="95acb-108">The name of each interchange schema file is **MT*xxx*.xsd**, where *xxx* is the FIN message type.</span></span>  
  
-   <span data-ttu-id="95acb-109">为每个消息关联的主策略文件的名称是 **MT*xxx*_Master_Policy.xml**，并且相应的名称在业务规则引擎 (BRE) 为 **MT*xxx*_Master_Policy**，列表名称为 **MT*xxx*_PolicyList * *。</span><span class="sxs-lookup"><span data-stu-id="95acb-109">The name of the associated master policy file for each message is **MT*xxx*_Master_Policy.xml**, and the corresponding name in the Business Rule Engine (BRE) is **MT*xxx*_Master_Policy**, with a list name of **MT*xxx*_PolicyList**.</span></span>  
  
-   <span data-ttu-id="95acb-110">为每个消息关联的验证策略文件的名称是 **MT*xxx*_Validation_Policy.xml**，BRE 中的相应名称和 **MT*xxx*_Validation_Policy**。</span><span class="sxs-lookup"><span data-stu-id="95acb-110">The name of the associated validation policy file for each message is **MT*xxx*_Validation_Policy.xml**, and the corresponding name in the BRE is **MT*xxx*_Validation_Policy**.</span></span>  
  
-   <span data-ttu-id="95acb-111">在每个消息架构，根的名称是 **SWIFT_CATEGORY*z*_MT*zxx*_Interchange * *，其中*z*消息类别（消息类型的第一个数字） 和*zxx*是消息类型。</span><span class="sxs-lookup"><span data-stu-id="95acb-111">Within each message schema, the name of the root is **SWIFT_CATEGORY*z*_MT*zxx*_Interchange**, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="95acb-112">每个消息架构的目标命名空间是 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx** *，其中*z*消息类别 （第一个数字的消息类型） 和*zxx*是消息类型。</span><span class="sxs-lookup"><span data-stu-id="95acb-112">The target namespace for each message schema is **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx***, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="95acb-113">文档类型是 **MT*zxx** *，其中*zxx*是消息类型。</span><span class="sxs-lookup"><span data-stu-id="95acb-113">The document type is **MT*zxx***, where *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="95acb-114">不带编号的字段和子字段的名称包含描述性业务名称。</span><span class="sxs-lookup"><span data-stu-id="95acb-114">The names of fields that are not numbered and sub-fields include descriptive business names.</span></span> <span data-ttu-id="95acb-115">每个单词的第一个字母大写，并且名称不包括干预空格或单词之间的标点符号 (例如，则名称将为**ServiceIdentifier**，而不**服务标识符**).</span><span class="sxs-lookup"><span data-stu-id="95acb-115">The first letter of each word is capitalized, and the names do not include an intervening space or punctuation between words (for example, the name would be **ServiceIdentifier**, not **Service Identifier**).</span></span>  
  
-   <span data-ttu-id="95acb-116">在消息的序列的标签符合*SWIFT 参考指南*(例如， **SequenceA**)。</span><span class="sxs-lookup"><span data-stu-id="95acb-116">The labels of sequences within messages conform to the *SWIFT Reference Guide* (for example, **SequenceA**).</span></span>  
  
-   <span data-ttu-id="95acb-117">标签编号 SWIFT 字段包括序列中 （如果存在） 后, 跟一个描述性标题跟的数字代码和可选字母格式 (例如， **Reference_A_20C**)。</span><span class="sxs-lookup"><span data-stu-id="95acb-117">The labels of numbered SWIFT fields include a descriptive title followed by the sequence (if present), followed by the number code and optional letter format (for example, **Reference_A_20C**).</span></span>  
  
-   <span data-ttu-id="95acb-118">选择的多个字段的格式，节点的标签是  **\<*选择*\>* *，，然后每个选项的已编号的字段 (例如， **Date_A_98A**和**DateTime_A_98C**)。</span><span class="sxs-lookup"><span data-stu-id="95acb-118">Where there is a choice of multiple formats for a field, the label of the node is **\<*Choice*\>**, and then each option is a numbered field (for example, **Date_A_98A** and **DateTime_A_98C**).</span></span>  
  
-   <span data-ttu-id="95acb-119">最低级别的元素定义的子字段的名称包含跟子字段的名称**类型**(例如， **accountType**帐户)。</span><span class="sxs-lookup"><span data-stu-id="95acb-119">The name of the lowest level element definition of a sub-field consists of the name of the sub-field followed by **Type** (for example, **accountType** for Account).</span></span>  
  
 <span data-ttu-id="95acb-120">其他命名空间中的消息架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="95acb-120">Other namespaces in the message schema include the following:</span></span>  
  
-   <span data-ttu-id="95acb-121">xmlns:xs ="http://www.w3.org/2001/XMLSchema"。</span><span class="sxs-lookup"><span data-stu-id="95acb-121">xmlns:xs="http://www.w3.org/2001/XMLSchema".</span></span> <span data-ttu-id="95acb-122">这是默认 W3C XML 架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="95acb-122">This is the default W3C XML Schema namespace.</span></span>  
  
-   <span data-ttu-id="95acb-123">xmlns:b ="http://schemas.microsoft.com/BizTalk/2003"。</span><span class="sxs-lookup"><span data-stu-id="95acb-123">xmlns:b="http://schemas.microsoft.com/BizTalk/2003".</span></span> <span data-ttu-id="95acb-124">这是默认 BizTalk 命名空间。</span><span class="sxs-lookup"><span data-stu-id="95acb-124">This is the default BizTalk namespace.</span></span>  
  
 <span data-ttu-id="95acb-125">每个消息架构直接引用的基类型和通用数据类型的架构。</span><span class="sxs-lookup"><span data-stu-id="95acb-125">Each message schema directly references the base type and common data type schemas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95acb-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95acb-126">See Also</span></span>  
 [<span data-ttu-id="95acb-127">处理架构</span><span class="sxs-lookup"><span data-stu-id="95acb-127">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)