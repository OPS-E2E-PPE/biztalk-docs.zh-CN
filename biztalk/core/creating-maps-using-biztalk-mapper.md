---
title: 创建使用 BizTalk 映射程序图 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- maps, creating
- orchestrations, maps
- translations [maps]
- maps, about maps
- transformations [maps]
- maps
ms.assetid: 265e61d8-8cff-44c9-a717-8e895cb4b9bf
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12da6732729052119bfcc7841424db6d0dcaff9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238333"
---
# <a name="creating-maps-using-biztalk-mapper"></a><span data-ttu-id="6c48b-102">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="6c48b-102">Creating Maps Using BizTalk Mapper</span></span>
<span data-ttu-id="6c48b-103">BizTalk 映射程序是一个工具，在 Microsoft 内运行[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="6c48b-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="6c48b-104">BizTalk 映射程序可用来创建和编辑映射，用于将转换或转换 xml 消息。</span><span class="sxs-lookup"><span data-stu-id="6c48b-104">BizTalk Mapper can be used to create and edit maps, which are used for translating or transforming xml messages.</span></span> <span data-ttu-id="6c48b-105">下图建议，并还可以用于处理在接收端口收到的消息和然后转换通过发送的消息将发送端口业务流程，用于映射。</span><span class="sxs-lookup"><span data-stu-id="6c48b-105">Maps are used in orchestrations, as the following figure suggest, and can also be used for processing messages received at a receive port, and then transforming the message to be sent via send port(s).</span></span>  
  
 <span data-ttu-id="6c48b-106">![使用映射业务处理关系图。](../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")</span><span class="sxs-lookup"><span data-stu-id="6c48b-106">![Business processing diagram with maps.](../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")</span></span>  
<span data-ttu-id="6c48b-107">业务处理中的映射</span><span class="sxs-lookup"><span data-stu-id="6c48b-107">Maps in Business Processing</span></span>  
  
 <span data-ttu-id="6c48b-108">使用映射可以翻译和转换消息。</span><span class="sxs-lookup"><span data-stu-id="6c48b-108">Maps enable you to translate and to transform messages.</span></span> <span data-ttu-id="6c48b-109">翻译是将消息从一种格式转换为另一种格式的过程，例如，将平面文件转换为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="6c48b-109">Translation is the process of converting a message from one format to another format, such as converting a flat file into an XML file.</span></span> <span data-ttu-id="6c48b-110">转换是从一个消息中获取信息并将获取的信息插入另一个消息的过程。</span><span class="sxs-lookup"><span data-stu-id="6c48b-110">Transformation is the process of taking information from one message and inserting it in another message.</span></span> <span data-ttu-id="6c48b-111">例如，您可以从采购订单中获取发运地址和帐单邮寄地址，再将这些地址插入发票文档。</span><span class="sxs-lookup"><span data-stu-id="6c48b-111">For example, you might take shipping and billing addresses from a purchase order and insert them in an invoice document.</span></span>  
  
 <span data-ttu-id="6c48b-112">BizTalk 映射器使用其自己的图标和链接图形系统来表示输入实例消息翻译和转换为输出实例消息的过程。</span><span class="sxs-lookup"><span data-stu-id="6c48b-112">BizTalk Mapper uses its own graphical system of icons and links to represent the translation and transformation of input instance messages to output instance messages.</span></span> <span data-ttu-id="6c48b-113">映射器与 BizTalk 编辑器使用相同的图形表示架构。</span><span class="sxs-lookup"><span data-stu-id="6c48b-113">Mapper uses the same graphical representation of schemas as BizTalk Editor.</span></span> <span data-ttu-id="6c48b-114">BizTalk 映射器以可扩展样式表语言转换 (XSLT) 样式表的形式存储其映射。</span><span class="sxs-lookup"><span data-stu-id="6c48b-114">BizTalk Mapper stores its maps as Extensible Stylesheet Language Transformations (XSLT) stylesheets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c48b-115">BizTalk 映射器支持 XSLT 1.0。</span><span class="sxs-lookup"><span data-stu-id="6c48b-115">BizTalk Mapper supports XSLT 1.0.</span></span> <span data-ttu-id="6c48b-116">不支持在 BizTalk 映射器中使用 XSLT 2.0。</span><span class="sxs-lookup"><span data-stu-id="6c48b-116">Using XSLT 2.0 in BizTalk Mapper is not supported.</span></span>  
  
 <span data-ttu-id="6c48b-117">有关创建架构的信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="6c48b-117">For information about creating schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span> <span data-ttu-id="6c48b-118">有关使用业务流程中的映射的信息，请参阅[创建业务流程使用 Orchestration 设计器](../core/creating-orchestrations-using-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="6c48b-118">For information about using maps within orchestrations, see [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c48b-119">映射的性能取决于映射的数量和类型的 functoid、 输入和输出的架构的大小、 输入的消息，以及你的硬件大小的复杂性。</span><span class="sxs-lookup"><span data-stu-id="6c48b-119">The performance of a map depends on the complexity of the map - the number and type of functoids, size of input and output schemas, the size of the input message, and your hardware.</span></span>  
  
 <span data-ttu-id="6c48b-120">有关为 BizTalk 映射程序使用的键盘快捷方式的信息，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="6c48b-120">For information about using the keyboard shortcuts for BizTalk Mapper, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c48b-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="6c48b-121">In This Section</span></span>  
  
-   [<span data-ttu-id="6c48b-122">计划创建地图</span><span class="sxs-lookup"><span data-stu-id="6c48b-122">Planning to Create Maps</span></span>](../core/planning-to-create-maps.md)  
  
-   [<span data-ttu-id="6c48b-123">有关映射</span><span class="sxs-lookup"><span data-stu-id="6c48b-123">About Maps</span></span>](../core/about-maps.md)  
  
-   [<span data-ttu-id="6c48b-124">使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="6c48b-124">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)  
  
-   [<span data-ttu-id="6c48b-125">创建映射</span><span class="sxs-lookup"><span data-stu-id="6c48b-125">Creating Maps</span></span>](../core/creating-maps.md)  
  
-   [<span data-ttu-id="6c48b-126">编译和测试映射</span><span class="sxs-lookup"><span data-stu-id="6c48b-126">Compiling and Testing Maps</span></span>](../core/compiling-and-testing-maps.md)  
  
-   [<span data-ttu-id="6c48b-127">排除地图故障</span><span class="sxs-lookup"><span data-stu-id="6c48b-127">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)