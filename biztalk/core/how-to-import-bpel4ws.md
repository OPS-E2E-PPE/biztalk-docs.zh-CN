---
title: 如何导入 BPEL4WS |Microsoft Docs
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
ms.openlocfilehash: d52dba33e4dadb788cca4ba60969989967fd9532
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384984"
---
# <a name="import-bpel4ws-in-biztalk-server"></a><span data-ttu-id="1a98b-102">在 BizTalk Server 中导入 BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="1a98b-102">Import BPEL4WS in BizTalk Server</span></span>
<span data-ttu-id="1a98b-103">您可以从现有的 BPEL4WS，若要创建一个业务流程导入。</span><span class="sxs-lookup"><span data-stu-id="1a98b-103">You can import from existing BPEL4WS to create an orchestration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1a98b-104">此版本的 BizTalk Server 支持 BPEL4WS 1.1。</span><span class="sxs-lookup"><span data-stu-id="1a98b-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="1a98b-105">无法导入或导出 BPEL4WS 1.0。</span><span class="sxs-lookup"><span data-stu-id="1a98b-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="1a98b-106">有关如何导入 BPEL4WS 的示例，请参阅[BPEL 导入 （BizTalk Server 示例）](../core/bpel-import-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="1a98b-106">For an example of how to import BPEL4WS, see [BPEL Import (BizTalk Server Sample)](../core/bpel-import-biztalk-server-sample.md).</span></span>  
  
## <a name="import-bpel4ws-into-an-orchestration"></a><span data-ttu-id="1a98b-107">导入 BPEL4WS 到业务流程</span><span class="sxs-lookup"><span data-stu-id="1a98b-107">Import BPEL4WS into an orchestration</span></span>  
  
1. <span data-ttu-id="1a98b-108">创建一个新的项目。</span><span class="sxs-lookup"><span data-stu-id="1a98b-108">Create a new project.</span></span>  
  
2. <span data-ttu-id="1a98b-109">从 BizTalk 项目类型中，双击 BizTalk Server BPEL 导入项目，或选择 BizTalk Server BPEL 导入项目，然后按确定。</span><span class="sxs-lookup"><span data-stu-id="1a98b-109">From the BizTalk Project types, double-click BizTalk Server BPEL Import Project, or select BizTalk Server BPEL Import Project and press OK.</span></span>  
  
3. <span data-ttu-id="1a98b-110">在向导中，选择要导入以形成新的 BizTalk 项目的 BPEL、 WSDL 和 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="1a98b-110">In the wizard, select the BPEL, WSDL and XSD files that should be imported to form the new BizTalk project.</span></span> <span data-ttu-id="1a98b-111">包括通过导入引用和 include 语句的所有文件。</span><span class="sxs-lookup"><span data-stu-id="1a98b-111">Include all files that are referenced via import and include statements.</span></span>  
  
4. <span data-ttu-id="1a98b-112">选择为调用 Web 服务的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="1a98b-112">Select WSDL files for invoked Web services.</span></span>  
  
    <span data-ttu-id="1a98b-113">现在可以修改或部署新的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1a98b-113">You can now modify or deploy the new orchestration.</span></span>  
  
   <span data-ttu-id="1a98b-114">**导入对 BPEL4WS 的限制**</span><span class="sxs-lookup"><span data-stu-id="1a98b-114">**Import restrictions on BPEL4WS**</span></span>  
  
-   <span data-ttu-id="1a98b-115">在导入 BPEL 和 WSDL，请确保 WSDL 定义节点和 BPEL 过程节点的 Name 属性不匹配。</span><span class="sxs-lookup"><span data-stu-id="1a98b-115">When importing BPEL and WSDL, make sure that the Name property of the WSDL definition node and the BPEL process node do not match.</span></span>  
  
-   <span data-ttu-id="1a98b-116">不要在您导入的 BPEL4WS 中使用 XLANG/s 保留字。</span><span class="sxs-lookup"><span data-stu-id="1a98b-116">Do not use XLANG/s reserved words in BPEL4WS that you import.</span></span> <span data-ttu-id="1a98b-117">有关完整列表，请参阅[XLANG/s 保留字](../core/xlang-s-reserved-words.md)。</span><span class="sxs-lookup"><span data-stu-id="1a98b-117">For a complete list, see [XLANG/s Reserved Words](../core/xlang-s-reserved-words.md).</span></span>  
  
-   <span data-ttu-id="1a98b-118">支持预定义的 XSD 简单类型。</span><span class="sxs-lookup"><span data-stu-id="1a98b-118">Only XSD predefined simple types are supported.</span></span>  
  
-   <span data-ttu-id="1a98b-119">不支持 xsd: qname;它将作为 System.String 导入。</span><span class="sxs-lookup"><span data-stu-id="1a98b-119">xsd:QName is not supported; it is imported as System.String.</span></span> <span data-ttu-id="1a98b-120">改为使用 xsd: string。</span><span class="sxs-lookup"><span data-stu-id="1a98b-120">Use xsd:string instead.</span></span>  
  
-   <span data-ttu-id="1a98b-121">请考虑导入 BPEL4WS 时使用规范化的 XPaths。</span><span class="sxs-lookup"><span data-stu-id="1a98b-121">Consider using canonical XPaths when importing BPEL4WS.</span></span>  
  
     <span data-ttu-id="1a98b-122">它是很好的做法导入规范化的 XPaths，以便获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="1a98b-122">It is good practice to import only canonical XPaths in order to achieve optimal performance.</span></span> <span data-ttu-id="1a98b-123">从根到升级节点的整个路径必须使用拼写 / \* [local-name ="someName"和命名空间 uri （） ="someUri"]。</span><span class="sxs-lookup"><span data-stu-id="1a98b-123">The entire path from root to the promoted node must be spelled out by using '/\*[local-name()="someName" and namespace-uri()="someUri"]'.</span></span>  
  
     <span data-ttu-id="1a98b-124">如果导入非规范化 XPath，可以删除升级，以便让架构编辑器创建正确的规范化 XPath 重新升级相同字段。</span><span class="sxs-lookup"><span data-stu-id="1a98b-124">If you import a non-canonical XPath, you can remove a promotion and repromote the same field in order to have the Schema Editor create the correct canonical XPath.</span></span>  
  
     <span data-ttu-id="1a98b-125">示例: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span><span class="sxs-lookup"><span data-stu-id="1a98b-125">Example: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span></span>  
  
    ```  
    <element name=Root type=complexType>  
                <sequence>  
                            <element name=promotedField/>  
                </sequence>  
    </element>  
    ```  
  
     `XPath - /*[local-name()='Root' and namespace-uri()='http://BizTalk_Server_Project3.Schema1']/\*[local-name()='promotedField' and namespace-uri()='']` 
  
    |<span data-ttu-id="1a98b-126">规范化 XPath</span><span class="sxs-lookup"><span data-stu-id="1a98b-126">Canonical XPath</span></span>|<span data-ttu-id="1a98b-127">非规范化 XPath</span><span class="sxs-lookup"><span data-stu-id="1a98b-127">Non-Canonical XPath</span></span>|  
    |---------------------|--------------------------|  
    |<span data-ttu-id="1a98b-128">BizTalk 编辑器将显示一个特殊的图标 (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) 来表示字段已升级。</span><span class="sxs-lookup"><span data-stu-id="1a98b-128">BizTalk Editor displays a special icon (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) to denote that the field has been promoted.</span></span> <span data-ttu-id="1a98b-129">使用情况的规范化 XPath 表达式将字段升级可以提高性能通过更有效地遍历 XML</span><span class="sxs-lookup"><span data-stu-id="1a98b-129">Usage of canonical XPath expressions to promote fields improves performance through more efficient traversal of the XML</span></span>|<span data-ttu-id="1a98b-130">BizTalk 编辑器不显示特殊图标。</span><span class="sxs-lookup"><span data-stu-id="1a98b-130">BizTalk Editor does not display a special icon.</span></span> <span data-ttu-id="1a98b-131">编译器和升级对话框发出警告。</span><span class="sxs-lookup"><span data-stu-id="1a98b-131">Both the compiler and the promotion dialog give warnings.</span></span> <span data-ttu-id="1a98b-132">没有对消息大小增加时的性能的线性明显影响。</span><span class="sxs-lookup"><span data-stu-id="1a98b-132">There is a linear but nontrivial effect on performance as the message size increases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a98b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a98b-133">See Also</span></span>  
 <span data-ttu-id="1a98b-134">[如何导出 BPEL4WS](../core/how-to-export-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="1a98b-134">[How to Export BPEL4WS](../core/how-to-export-bpel4ws.md) </span></span>  
 [<span data-ttu-id="1a98b-135">XLANG-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="1a98b-135">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)
