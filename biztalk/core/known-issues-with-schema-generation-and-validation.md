---
title: 使用架构生成和验证的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298376e0d8e22e84964c2a70df165664f0da9b45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968214"
---
# <a name="known-issues-with-schema-generation-and-validation"></a><span data-ttu-id="40cec-102">架构生成和验证的已知的问题</span><span class="sxs-lookup"><span data-stu-id="40cec-102">Known Issues with Schema Generation and Validation</span></span>
<span data-ttu-id="40cec-103">本主题提供架构生成和验证的已知问题的相关信息。</span><span class="sxs-lookup"><span data-stu-id="40cec-103">This topic provides information about known issues with schema generation and validation.</span></span>  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a><span data-ttu-id="40cec-104">为带有标记的位置记录生成的实例消息可能不正确</span><span class="sxs-lookup"><span data-stu-id="40cec-104">An instance message generated for a positional record with tags could be incorrect</span></span>  
 <span data-ttu-id="40cec-105">对于位置记录，标记可能在字段内，也可能跨两个字段。</span><span class="sxs-lookup"><span data-stu-id="40cec-105">For positional records, the tag can be within a field or can span between fields.</span></span> <span data-ttu-id="40cec-106">无论在哪种情况下，生成的实例都将无效，并导致在解析阶段中解析引擎出现故障。</span><span class="sxs-lookup"><span data-stu-id="40cec-106">In either case, the instance generated will not be valid and will cause a failure in the Parsing Engine during the parsing stage.</span></span>  
  
 <span data-ttu-id="40cec-107">如果标记不是任何子级（子节点或子字段）的一部分，则不会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="40cec-107">If the tag is not part of any children (child records or child fields), this problem will not occur.</span></span>  
  
 <span data-ttu-id="40cec-108">若要解决此问题，请将标记的实际值包含为架构中的默认值。</span><span class="sxs-lookup"><span data-stu-id="40cec-108">To work around this issue, include the actual value of the tag as the default in the schema.</span></span> <span data-ttu-id="40cec-109">在 BizTalk 编辑器的平面文件扩展功能，可以设置**固定值**或**默认值**的相应位置字段具有标记的值的属性。</span><span class="sxs-lookup"><span data-stu-id="40cec-109">In the flat file extension of the BizTalk Editor, you can set the **Fixed Value** or **Default Value** property of the appropriate positional field with the value of the tag.</span></span>  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a><span data-ttu-id="40cec-110">为具有某些限制的字段生成的实例消息可能未通过验证</span><span class="sxs-lookup"><span data-stu-id="40cec-110">An instance message generated for a field with some restrictions may not pass validation</span></span>  
 <span data-ttu-id="40cec-111">从包含一个或多个架构生成实例消息时**Field 元素**并**字段属性**具有使用限制机制，如派生的数据类型的节点当**模式**使用属性时，生成的此类字段的示例数据可能不符合要求的限制，从而防止使用相同的架构从该实例消息的验证成功它生成。</span><span class="sxs-lookup"><span data-stu-id="40cec-111">When you generate an instance message from a schema that contains one or more **Field Element** and **Field Attribute** nodes that have data types that have been derived using the restriction mechanism, such as when the **Pattern** property is used, the sample data generated for such fields may not conform to the requirements of the restriction, thereby preventing successful validation of that instance message using the same schema from which it was generated.</span></span>  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a><span data-ttu-id="40cec-112">为包含无限循环的架构生成的实例消息可能无效。</span><span class="sxs-lookup"><span data-stu-id="40cec-112">An instance message generated for a schema that contains an infinite loop may not be valid.</span></span>  
 <span data-ttu-id="40cec-113">包含与节点的循环引用时，您的架构可以包含无限循环**最小出现次数**属性值大于或等于一，实质上阻止终止条件。</span><span class="sxs-lookup"><span data-stu-id="40cec-113">Your schema can contain an infinite loop when it contains a circular reference to a node with a **Min Occurs** property value greater than or equal to one, essentially preventing a termination condition.</span></span> <span data-ttu-id="40cec-114">实例消息的生成将人为终止，以便生成操作可以完成，但生成的实例消息因此将不符合生成该消息所基于的架构。</span><span class="sxs-lookup"><span data-stu-id="40cec-114">Instance message generation will artificially terminate so that the generation operation can complete, but the produced instance message will thereby not conform to the schema from which it was generated.</span></span> <span data-ttu-id="40cec-115">此类架构通常是可疑的。</span><span class="sxs-lookup"><span data-stu-id="40cec-115">Such schemas are usually suspect.</span></span>  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a><span data-ttu-id="40cec-116">验证 XML 实例的失败的文档架构目标命名空间 ="<http://www.w3.org/XML/1998/namespace>"</span><span class="sxs-lookup"><span data-stu-id="40cec-116">Validation of XML instance fails for document schema which has the target namespace="<http://www.w3.org/XML/1998/namespace>"</span></span>  
 <span data-ttu-id="40cec-117">超链接"<http://www.w3.org/XML/1998/namespace>"是保留的命名空间，其前缀应为"XML"。</span><span class="sxs-lookup"><span data-stu-id="40cec-117">The HYPERLINK "<http://www.w3.org/XML/1998/namespace>" is a reserved namespace whose prefix should be “XML”.</span></span> <span data-ttu-id="40cec-118">您可以手动编辑为"XML"前缀。</span><span class="sxs-lookup"><span data-stu-id="40cec-118">You can manually edit the prefix to “XML”.</span></span>

## <a name="see-also"></a><span data-ttu-id="40cec-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40cec-119">See also</span></span>
<span data-ttu-id="40cec-120">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="40cec-120">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
