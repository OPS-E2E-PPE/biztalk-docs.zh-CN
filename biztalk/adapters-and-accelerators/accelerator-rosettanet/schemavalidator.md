---
title: SchemaValidator |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bf31f22cc2b79e6dded22e04500655110f242ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973870"
---
# <a name="schemavalidator"></a><span data-ttu-id="6416a-102">SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="6416a-102">SchemaValidator</span></span>
<span data-ttu-id="6416a-103">使用 SchemaValidator 实用工具可以排除消息实例中的故障。</span><span class="sxs-lookup"><span data-stu-id="6416a-103">You use the SchemaValidator utility to troubleshoot problems with a message instance.</span></span> <span data-ttu-id="6416a-104">如果所收到的消息验证失败，则可以运行 SchemaValidator 实用工具来确定失败的根源。</span><span class="sxs-lookup"><span data-stu-id="6416a-104">If you receive a message that fails validation, you can run the SchemaValidator utility to determine the source of the failure.</span></span>  
  
 <span data-ttu-id="6416a-105">如果你使用的是包含架构 .dll 文件的程序集并且没有架构 .xsd 文件，则可以使用此实用工具。</span><span class="sxs-lookup"><span data-stu-id="6416a-105">You use this utility if you are using an assembly that includes a schema .dll file, and you do not have a schema .xsd file.</span></span> <span data-ttu-id="6416a-106">通过 SchemaValidator 实用工具，可以使用架构 .dll 文件进行验证。</span><span class="sxs-lookup"><span data-stu-id="6416a-106">The SchemaValidator utility lets you validate using the schema .dll file.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="6416a-107">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="6416a-107">Location in SDK</span></span>  
 <span data-ttu-id="6416a-108">\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="6416a-108">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator</span></span>  
  
## <a name="building-and-running-schemavalidator"></a><span data-ttu-id="6416a-109">生成和运行 SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="6416a-109">Building and Running SchemaValidator</span></span>  
  
#### <a name="to-build-the-schemavalidator-utility"></a><span data-ttu-id="6416a-110">生成 SchemaValidator 实用工具</span><span class="sxs-lookup"><span data-stu-id="6416a-110">To build the SchemaValidator utility</span></span>  
  
1. <span data-ttu-id="6416a-111">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6416a-111">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="6416a-112">将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator。</span><span class="sxs-lookup"><span data-stu-id="6416a-112">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
3. <span data-ttu-id="6416a-113">在命令提示符处，键入**sn-k SchemaValidator.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="6416a-113">At the command prompt, type **sn -k SchemaValidator.snk**, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="6416a-114">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="6416a-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5. <span data-ttu-id="6416a-115">上**文件**菜单，依次指向**打开**，然后单击**打开的解决方案**。</span><span class="sxs-lookup"><span data-stu-id="6416a-115">On the **File** menu, point to **Open**, and then click **Open Solution**.</span></span>  
  
6. <span data-ttu-id="6416a-116">将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator，选择**SchemaValidator.sln**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="6416a-116">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator, select **SchemaValidator.sln**, and then click **Open**.</span></span>  
  
7. <span data-ttu-id="6416a-117">在解决方案资源管理器中右键单击**SchemaValidator**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6416a-117">In Solution Explorer, right-click **SchemaValidator**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="6416a-118">在中**MessageInspector 属性**页上，单击**签名**选项卡，然后依次**程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="6416a-118">In the **MessageInspector Property**  page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span> <span data-ttu-id="6416a-119">选择**SchemaValidator.snk**中**选择一个强名称密钥文件**。</span><span class="sxs-lookup"><span data-stu-id="6416a-119">Select **SchemaValidator.snk** in **Choose a strong name key file**.</span></span>  
  
9. <span data-ttu-id="6416a-120">单击**SchemaValidator.cs**。</span><span class="sxs-lookup"><span data-stu-id="6416a-120">Click **SchemaValidator.cs**.</span></span>  
  
10. <span data-ttu-id="6416a-121">将相应的消息实例路径键入 `Main` 中原有的以下代码行：</span><span class="sxs-lookup"><span data-stu-id="6416a-121">Type the appropriate message instance path in the following existing line of code in `Main`:</span></span>  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. <span data-ttu-id="6416a-122">用对 RNPIP 程序集的引用替换 `Main` 中原有的以下代码行，然后选择相应的架构：</span><span class="sxs-lookup"><span data-stu-id="6416a-122">Replace the following existing line of code in `Main` with a reference to the RNPIPs assembly, and then select the appropriate schema:</span></span>  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. <span data-ttu-id="6416a-123">右键单击**SchemaValidator**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="6416a-123">Right-click **SchemaValidator**, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="6416a-124">修改消息实例到你想要通过删除测试\< \!DOCTYPE...\>标记来指定从 XML 实例的标头的 DTD 文件。</span><span class="sxs-lookup"><span data-stu-id="6416a-124">Modify the message instance to you want to test by removing the \<\!DOCTYPE …\> tag specifying the DTD file from the header of the XML instance.</span></span>  
  
14. <span data-ttu-id="6416a-125">在消息实例的根节点下，添加要对其进行验证的架构的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="6416a-125">In the root node of the message instance, add an XML namespace of the schema that you will validate against.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6416a-126">准备好可由 SchemaValidator 实用工具进行验证的架构的示例，请参阅中的 Sample3A4.xml \<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator。</span><span class="sxs-lookup"><span data-stu-id="6416a-126">For an example of a schema ready to be validated by the SchemaValidator utility, see Sample3A4.xml in \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
15. <span data-ttu-id="6416a-127">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**SchemaValidator.cs**，然后按 CTRL 和 F5 以运行此实用工具。</span><span class="sxs-lookup"><span data-stu-id="6416a-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **SchemaValidator.cs**, and then press CTRL and F5 to run the utility.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6416a-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="6416a-128">Remarks</span></span>  
 <span data-ttu-id="6416a-129">由于 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包含 SchemaValidator 代码，因此可以向该实用工具添加逻辑。</span><span class="sxs-lookup"><span data-stu-id="6416a-129">Because the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes the SchemaValidator code, you can add logic to the utility.</span></span> <span data-ttu-id="6416a-130">例如，可以将其做成命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="6416a-130">For example, you can make it a command-line utility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6416a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="6416a-131">See Also</span></span>  
 [<span data-ttu-id="6416a-132">实用工具</span><span class="sxs-lookup"><span data-stu-id="6416a-132">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
