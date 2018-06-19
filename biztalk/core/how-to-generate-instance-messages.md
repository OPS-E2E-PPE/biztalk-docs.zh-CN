---
title: 如何生成实例消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff74c67a-7e73-4153-9ec4-e6e50464ee92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a911e4b0f1167e8ec200dad65b8dacb94bb08be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254397"
---
# <a name="how-to-generate-instance-messages"></a><span data-ttu-id="f21c1-102">如何生成实例消息</span><span class="sxs-lookup"><span data-stu-id="f21c1-102">How to Generate Instance Messages</span></span>
<span data-ttu-id="f21c1-103">构造架构之后，有一种检查工作的方法是从该架构生成一个实例消息示例。</span><span class="sxs-lookup"><span data-stu-id="f21c1-103">After you have constructed a schema, one way to check your work is to generate a sample instance message from the schema.</span></span> <span data-ttu-id="f21c1-104">在很多方法中，查看实例消息都比查看架构树或架构的 XML 架构定义 (XSD) 语言表示形式直接的多。</span><span class="sxs-lookup"><span data-stu-id="f21c1-104">In many ways, looking at an instance message is much more straightforward than looking at either the schema tree or the XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="f21c1-105">这是因为架构需要描述相应实例消息的所有可能变体，而特定的实例消息只需通过使用由架构指定的格式来传送某些数据。</span><span class="sxs-lookup"><span data-stu-id="f21c1-105">This is because the schema needs to describe all of the possible variations of the corresponding instance messages, and a specific instance message just needs to convey some data by using the format specified by the schema.</span></span> <span data-ttu-id="f21c1-106">生成的实例消息是一个示例，可能无法显示由相应架构定义的所有结构。</span><span class="sxs-lookup"><span data-stu-id="f21c1-106">The generated instance message is a sample and may not show all of the structures defined by the corresponding schema.</span></span>  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a><span data-ttu-id="f21c1-107">显式指定文件以包含生成的实例消息</span><span class="sxs-lookup"><span data-stu-id="f21c1-107">To explicitly specify a file to contain the generated instance message</span></span>  
  
1.  <span data-ttu-id="f21c1-108">在解决方案资源管理器，右键单击你要为其生成实例消息，并依次的架构**属性**。</span><span class="sxs-lookup"><span data-stu-id="f21c1-108">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f21c1-109">如有必要，在属性窗口中，展开**常规**部分**常规**选项卡上通过单击其加号 （+） 图标。</span><span class="sxs-lookup"><span data-stu-id="f21c1-109">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="f21c1-110">在**输出实例文件名**属性值字段中，键入文件的名称，或者使用省略号 (**...**) 值字段来浏览的文件生成的实例消息将放置到其中，然后单击右侧的按钮**保存**。</span><span class="sxs-lookup"><span data-stu-id="f21c1-110">In the **Output Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file into which generated instance messages will be placed, and then click **Save**.</span></span>  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a><span data-ttu-id="f21c1-111">指定生成的实例消息的类型</span><span class="sxs-lookup"><span data-stu-id="f21c1-111">To specify the type of the generated instance message</span></span>  
  
1.  <span data-ttu-id="f21c1-112">在解决方案资源管理器，右键单击你要为其生成实例消息，并依次的架构**属性**。</span><span class="sxs-lookup"><span data-stu-id="f21c1-112">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f21c1-113">如有必要，在属性窗口中，展开**常规**部分**常规**选项卡上通过单击其加号 （+） 图标。</span><span class="sxs-lookup"><span data-stu-id="f21c1-113">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="f21c1-114">在**生成实例输出类型**属性值字段中，使用下拉列表中选择**XML**或**本机**作为实例消息生成的类型。</span><span class="sxs-lookup"><span data-stu-id="f21c1-114">In the **Generate Instance Output Type** property value field, use the drop-down list to select either **XML** or **Native** as the type of the instance message to be generated.</span></span>  
  
     <span data-ttu-id="f21c1-115">**XML**是默认值。</span><span class="sxs-lookup"><span data-stu-id="f21c1-115">**XML** is the default value.</span></span>  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a><span data-ttu-id="f21c1-116">生成架构的实例消息示例</span><span class="sxs-lookup"><span data-stu-id="f21c1-116">To generate a sample instance message for a schema</span></span>  
  
1.  <span data-ttu-id="f21c1-117">在解决方案资源管理器，右键单击你要为其生成实例消息，并依次的架构**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="f21c1-117">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Generate Instance**.</span></span>  
  
2.  <span data-ttu-id="f21c1-118">在“输出”窗口中，查看结果。</span><span class="sxs-lookup"><span data-stu-id="f21c1-118">In the Output window, view the results.</span></span> <span data-ttu-id="f21c1-119">此窗口中将显示成功消息和错误消息。</span><span class="sxs-lookup"><span data-stu-id="f21c1-119">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f21c1-120">如果“输出”窗口和/或“任务列表”窗口并未打开与显示与实例生成成败与否相关的信息，则可以手动打开。</span><span class="sxs-lookup"><span data-stu-id="f21c1-120">If the Output window and/or the Task List window did not open and display information about whether the instance generation succeeded or failed, you can open them manually.</span></span> <span data-ttu-id="f21c1-121">有关管理这些窗口的详细信息，请参阅[管理其他 Visual Studio 窗口](../core/how-to-manage-other-visual-studio-windows.md)。</span><span class="sxs-lookup"><span data-stu-id="f21c1-121">For more information about managing these windows, see [Managing Other Visual Studio Windows](../core/how-to-manage-other-visual-studio-windows.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f21c1-122">如果未指定的值**根引用**属性，BizTalk 编辑器在架构中生成的第一个根节点的示例实例消息。</span><span class="sxs-lookup"><span data-stu-id="f21c1-122">If you do not specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for the first root node in the schema.</span></span> <span data-ttu-id="f21c1-123">如果指定的值**根引用**属性，BizTalk 编辑器生成该根的示例实例消息。</span><span class="sxs-lookup"><span data-stu-id="f21c1-123">If you specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for that root.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f21c1-124">在某些情况下，由特定架构生成的实例消息可能无法通过使用同一架构进行的验证。</span><span class="sxs-lookup"><span data-stu-id="f21c1-124">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="f21c1-125">有关这种情况下的详细信息，请参阅[已知架构生成和验证问题](../core/known-issues-with-schema-generation-and-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="f21c1-125">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="f21c1-126">通常情况下，你想要编辑生成的实例消息并更改它所包含，使其更真实地表示你的方案的数据。</span><span class="sxs-lookup"><span data-stu-id="f21c1-126">Generally, you want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="f21c1-127">然后使用此修改的实例消息来验证您的架构。</span><span class="sxs-lookup"><span data-stu-id="f21c1-127">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21c1-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f21c1-128">See Also</span></span>  
 <span data-ttu-id="f21c1-129">[测试架构](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="f21c1-129">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="f21c1-130">[架构验证](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="f21c1-130">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="f21c1-131">实例消息生成和验证</span><span class="sxs-lookup"><span data-stu-id="f21c1-131">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)