---
title: 如何导入 BPEL4WS |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3626fcb9-8e7d-4812-a0c9-bde6e7954ec8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e82dd80e280eff39ff5c1678b5c9751e378ee1b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31008472"
---
# <a name="import-bpel4ws-in-biztalk-server"></a><span data-ttu-id="f6dc6-102">BizTalk Server 中的导入 BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="f6dc6-102">Import BPEL4WS in BizTalk Server</span></span>
<span data-ttu-id="f6dc6-103">可以从现有的 BPEL4WS 进行导入以创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-103">You can import from existing BPEL4WS to create an orchestration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f6dc6-104">此版本的 BizTalk Server 支持 BPEL4WS 1.1。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="f6dc6-105">无法导入或导出 BPEL4WS 1.0。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="f6dc6-106">有关如何导入 BPEL4WS 的示例，请参阅[BPEL 导入 （BizTalk Server 示例）](../core/bpel-import-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-106">For an example of how to import BPEL4WS, see [BPEL Import (BizTalk Server Sample)](../core/bpel-import-biztalk-server-sample.md).</span></span>  
  
## <a name="import-bpel4ws-into-an-orchestration"></a><span data-ttu-id="f6dc6-107">导入 BPEL4WS 到业务流程</span><span class="sxs-lookup"><span data-stu-id="f6dc6-107">Import BPEL4WS into an orchestration</span></span>  
  
1.  <span data-ttu-id="f6dc6-108">创建一个新的项目。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-108">Create a new project.</span></span>  
  
2.  <span data-ttu-id="f6dc6-109">在 BizTalk 项目类型中，双击“BizTalk Server BPEL 导入项目”，或选择“BizTalk Server BPEL 导入项目”，然后按“确定”。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-109">From the BizTalk Project types, double-click BizTalk Server BPEL Import Project, or select BizTalk Server BPEL Import Project and press OK.</span></span>  
  
3.  <span data-ttu-id="f6dc6-110">在向导中，选择要导入以形成新的 BizTalk 项目的 BPEL、WSDL 和 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-110">In the wizard, select the BPEL, WSDL and XSD files that should be imported to form the new BizTalk project.</span></span> <span data-ttu-id="f6dc6-111">包括通过 import 和 include 语句引用的所有文件。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-111">Include all files that are referenced via import and include statements.</span></span>  
  
4.  <span data-ttu-id="f6dc6-112">为所调用的 Web Services 选择 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-112">Select WSDL files for invoked Web services.</span></span>  
  
     <span data-ttu-id="f6dc6-113">现在，您可以修改或部署新的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-113">You can now modify or deploy the new orchestration.</span></span>  
  
 <span data-ttu-id="f6dc6-114">**导入 BPEL4WS 的限制**</span><span class="sxs-lookup"><span data-stu-id="f6dc6-114">**Import restrictions on BPEL4WS**</span></span>  
  
-   <span data-ttu-id="f6dc6-115">在导入 BPEL 和 WSDL 时，请确保 WSDL 定义节点和 BPEL 过程节点的 Name 属性不匹配。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-115">When importing BPEL and WSDL, make sure that the Name property of the WSDL definition node and the BPEL process node do not match.</span></span>  
  
-   <span data-ttu-id="f6dc6-116">不要在导入的 BPEL4WS 中使用 XLANG/s 保留字。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-116">Do not use XLANG/s reserved words in BPEL4WS that you import.</span></span> <span data-ttu-id="f6dc6-117">完整列表，请参阅[XLANG/s 保留字](../core/xlang-s-reserved-words.md)。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-117">For a complete list, see [XLANG/s Reserved Words](../core/xlang-s-reserved-words.md).</span></span>  
  
-   <span data-ttu-id="f6dc6-118">仅支持 XSD 预定义的简单类型。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-118">Only XSD predefined simple types are supported.</span></span>  
  
-   <span data-ttu-id="f6dc6-119">不支持 xsd:QName;它是作为 System.String 导入。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-119">xsd:QName is not supported; it is imported as System.String.</span></span> <span data-ttu-id="f6dc6-120">改为使用 xsd: string。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-120">Use xsd:string instead.</span></span>  
  
-   <span data-ttu-id="f6dc6-121">请考虑在导入 BPEL4WS 时使用规范化的 XPaths。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-121">Consider using canonical XPaths when importing BPEL4WS.</span></span>  
  
     <span data-ttu-id="f6dc6-122">最好只导入规范化的 XPaths，以便获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-122">It is good practice to import only canonical XPaths in order to achieve optimal performance.</span></span> <span data-ttu-id="f6dc6-123">必须通过使用“/\*[local-name()="someName" and namespace-uri()="someUri"]”将从根到升级节点的完整路径拼写出来。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-123">The entire path from root to the promoted node must be spelled out by using '/\*[local-name()="someName" and namespace-uri()="someUri"]'.</span></span>  
  
     <span data-ttu-id="f6dc6-124">如果导入非规范化的 XPath，则可以删除升级并重新升级相同字段，以便让架构编辑器创建正确的规范化 XPath。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-124">If you import a non-canonical XPath, you can remove a promotion and repromote the same field in order to have the Schema Editor create the correct canonical XPath.</span></span>  
  
     <span data-ttu-id="f6dc6-125">示例: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span><span class="sxs-lookup"><span data-stu-id="f6dc6-125">Example: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span></span>  
  
    ```  
    <element name=Root type=complexType>  
                <sequence>  
                            <element name=promotedField/>  
                </sequence>  
    </element>  
    ```  
  
     `XPath - /*[local-name()='Root' and namespace-uri()='http://BizTalk_Server_Project3.Schema1']/\*[local-name()='promotedField' and namespace-uri()='']` 
  
    |<span data-ttu-id="f6dc6-126">规范化 XPath</span><span class="sxs-lookup"><span data-stu-id="f6dc6-126">Canonical XPath</span></span>|<span data-ttu-id="f6dc6-127">非规范化 XPath</span><span class="sxs-lookup"><span data-stu-id="f6dc6-127">Non-Canonical XPath</span></span>|  
    |---------------------|--------------------------|  
    |<span data-ttu-id="f6dc6-128">BizTalk 编辑器将显示一个特殊图标 (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) 来表示字段已被提升。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-128">BizTalk Editor displays a special icon (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) to denote that the field has been promoted.</span></span> <span data-ttu-id="f6dc6-129">如果使用规范化 XPath 表达式升级字段，则可以通过更有效地遍历 XML 来改进性能。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-129">Usage of canonical XPath expressions to promote fields improves performance through more efficient traversal of the XML</span></span>|<span data-ttu-id="f6dc6-130">BizTalk 编辑器不显示特殊图标。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-130">BizTalk Editor does not display a special icon.</span></span> <span data-ttu-id="f6dc6-131">编译器和升级对话框都会发出警告。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-131">Both the compiler and the promotion dialog give warnings.</span></span> <span data-ttu-id="f6dc6-132">随着消息大小的增长，会对性能产生明显的线性影响。</span><span class="sxs-lookup"><span data-stu-id="f6dc6-132">There is a linear but nontrivial effect on performance as the message size increases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6dc6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6dc6-133">See Also</span></span>  
 <span data-ttu-id="f6dc6-134">[如何导出 BPEL4WS](../core/how-to-export-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="f6dc6-134">[How to Export BPEL4WS](../core/how-to-export-bpel4ws.md) </span></span>  
 [<span data-ttu-id="f6dc6-135">XLANG-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="f6dc6-135">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)
