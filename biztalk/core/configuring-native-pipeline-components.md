---
title: "配置本机管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, pipeline components
- pipeline components, configuring
- Pipeline Designer, code sample
- IPersistPropertyBag interface
ms.assetid: a3332a60-8cd6-43fa-9ecf-e1e54e71fef7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94475334395f8c360bbb636cfa9cbadcf3bf4fe3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-native-pipeline-components"></a><span data-ttu-id="51ec7-102">配置本地管道组件</span><span class="sxs-lookup"><span data-stu-id="51ec7-102">Configuring Native Pipeline Components</span></span>
<span data-ttu-id="51ec7-103">管道组件可以在设计时公开自己的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="51ec7-103">Pipeline components can expose their own custom properties at design time.</span></span> <span data-ttu-id="51ec7-104">如果已实现相应属性的读取和写入存取方法，在组件中定义的任何公共属性都将呈现在管道设计器中。</span><span class="sxs-lookup"><span data-stu-id="51ec7-104">Any public property defined in the component will be rendered in Pipeline Designer providing that read and write accessors for that property are implemented.</span></span> <span data-ttu-id="51ec7-105">管道设计器将根据组件属性的声明来显示这些属性；例如，如果属性声明为只读，在管道设计器中就会显示为只读。</span><span class="sxs-lookup"><span data-stu-id="51ec7-105">Pipeline Designer will display the component properties in accordance with their declaration; for example, if the property is declared as read-only, it will be displayed as such in Pipeline Designer.</span></span>  
  
 <span data-ttu-id="51ec7-106">必须实现自定义管道组件**IPersistPropertyBag**使这些自定义属性创建的接口。</span><span class="sxs-lookup"><span data-stu-id="51ec7-106">Custom pipeline components must implement the **IPersistPropertyBag** interface to enable the creation of these custom properties.</span></span> <span data-ttu-id="51ec7-107">使用创建属性**IPersistPropertyBag**接口可以在 Microsoft 的属性窗口中设置[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，就像本机管道组件的所有属性。</span><span class="sxs-lookup"><span data-stu-id="51ec7-107">Properties created with the **IPersistPropertyBag** interface can be set in the Properties window of Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], just like all the properties of the native pipeline components.</span></span> <span data-ttu-id="51ec7-108">本部分将介绍配置所包括的各管道组件的过程。</span><span class="sxs-lookup"><span data-stu-id="51ec7-108">This section contains procedures for configuring each of the included pipeline components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51ec7-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="51ec7-109">In This Section</span></span>  
  
-   [<span data-ttu-id="51ec7-110">如何配置本机管道组件</span><span class="sxs-lookup"><span data-stu-id="51ec7-110">How to Configure Native Pipeline Components</span></span>](../core/how-to-configure-native-pipeline-components.md)  
  
-   [<span data-ttu-id="51ec7-111">如何将 BizTalk Framework 汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="51ec7-111">How to Configure the BizTalk Framework Assembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-112">如何将 BizTalk Framework 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="51ec7-112">How to Configure the BizTalk Framework Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-113">BizTalk Framework 架构和属性</span><span class="sxs-lookup"><span data-stu-id="51ec7-113">BizTalk Framework Schema and Properties</span></span>](../core/biztalk-framework-schema-and-properties.md)  
  
-   [<span data-ttu-id="51ec7-114">如何配置平面文件汇编管道组件</span><span class="sxs-lookup"><span data-stu-id="51ec7-114">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-115">如何配置平面文件反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="51ec7-115">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-116">如何配置 MIME SMIME 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="51ec7-116">How to Configure the MIME-SMIME Decoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-117">如何配置 MIME-SMIME 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="51ec7-117">How to Configure the MIME-SMIME Encoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-118">MIME SMIME 属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="51ec7-118">MIME-SMIME Property Schema and Properties</span></span>](../core/mime-smime-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="51ec7-119">如何配置参与方解析管道组件</span><span class="sxs-lookup"><span data-stu-id="51ec7-119">How to Configure the Party Resolution Pipeline Component</span></span>](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-120">如何将 XML 汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="51ec7-120">How to Configure the XML Assembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-121">如何将 XML 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="51ec7-121">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="51ec7-122">XML、 平面文件属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="51ec7-122">XML and Flat File Property Schema and Properties</span></span>](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="51ec7-123">如何将 XML 验证程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="51ec7-123">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)