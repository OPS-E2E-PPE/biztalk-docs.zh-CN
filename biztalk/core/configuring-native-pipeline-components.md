---
title: 配置本地管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, pipeline components
- pipeline components, configuring
- Pipeline Designer, code sample
- IPersistPropertyBag interface
ms.assetid: a3332a60-8cd6-43fa-9ecf-e1e54e71fef7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9d60c963231f61684cc58187d40bc23141ff1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355298"
---
# <a name="configuring-native-pipeline-components"></a><span data-ttu-id="2d4a1-102">配置本地管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-102">Configuring Native Pipeline Components</span></span>
<span data-ttu-id="2d4a1-103">管道组件可以在设计时公开自己的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="2d4a1-103">Pipeline components can expose their own custom properties at design time.</span></span> <span data-ttu-id="2d4a1-104">在组件中定义的任何公共属性将呈现在管道设计器中的读取和写入存取方法，实现属性。</span><span class="sxs-lookup"><span data-stu-id="2d4a1-104">Any public property defined in the component will be rendered in Pipeline Designer providing that read and write accessors for that property are implemented.</span></span> <span data-ttu-id="2d4a1-105">管道设计器将显示其声明; 根据组件属性例如，如果属性声明为只读的它将显示这种情况下在管道设计器中。</span><span class="sxs-lookup"><span data-stu-id="2d4a1-105">Pipeline Designer will display the component properties in accordance with their declaration; for example, if the property is declared as read-only, it will be displayed as such in Pipeline Designer.</span></span>  
  
 <span data-ttu-id="2d4a1-106">自定义管道组件必须实现**IPersistPropertyBag**接口，以使这些自定义属性创建。</span><span class="sxs-lookup"><span data-stu-id="2d4a1-106">Custom pipeline components must implement the **IPersistPropertyBag** interface to enable the creation of these custom properties.</span></span> <span data-ttu-id="2d4a1-107">使用创建的属性**IPersistPropertyBag**接口可以在 Microsoft 的属性窗口中设置[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，就像本地管道组件的所有属性。</span><span class="sxs-lookup"><span data-stu-id="2d4a1-107">Properties created with the **IPersistPropertyBag** interface can be set in the Properties window of Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], just like all the properties of the native pipeline components.</span></span> <span data-ttu-id="2d4a1-108">本部分包含配置的每个包含的管道组件的过程。</span><span class="sxs-lookup"><span data-stu-id="2d4a1-108">This section contains procedures for configuring each of the included pipeline components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d4a1-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="2d4a1-109">In This Section</span></span>  
  
-   [<span data-ttu-id="2d4a1-110">如何配置本地管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-110">How to Configure Native Pipeline Components</span></span>](../core/how-to-configure-native-pipeline-components.md)  
  
-   [<span data-ttu-id="2d4a1-111">如何配置 BizTalk 框架组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-111">How to Configure the BizTalk Framework Assembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-112">如何配置 BizTalk 框架拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-112">How to Configure the BizTalk Framework Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-113">BizTalk 框架架构和属性</span><span class="sxs-lookup"><span data-stu-id="2d4a1-113">BizTalk Framework Schema and Properties</span></span>](../core/biztalk-framework-schema-and-properties.md)  
  
-   [<span data-ttu-id="2d4a1-114">如何配置平面文件组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-114">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-115">如何配置平面文件拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-115">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-116">如何配置 MIME-SMIME 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-116">How to Configure the MIME-SMIME Decoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-117">如何配置 MIME-SMIME 编码器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-117">How to Configure the MIME-SMIME Encoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-118">MIME-SMIME 属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="2d4a1-118">MIME-SMIME Property Schema and Properties</span></span>](../core/mime-smime-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="2d4a1-119">如何配置参与方解析管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-119">How to Configure the Party Resolution Pipeline Component</span></span>](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-120">如何配置 XML 组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-120">How to Configure the XML Assembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-121">如何配置 XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-121">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2d4a1-122">XML 和平面文件属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="2d4a1-122">XML and Flat File Property Schema and Properties</span></span>](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="2d4a1-123">如何配置 XML 验证器管道组件</span><span class="sxs-lookup"><span data-stu-id="2d4a1-123">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)