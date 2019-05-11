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
ms.openlocfilehash: 2be96f3d87cb0744ca4e823942f7265bf6b3fa3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281974"
---
# <a name="schemavalidator"></a><span data-ttu-id="8426f-102">SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="8426f-102">SchemaValidator</span></span>
<span data-ttu-id="8426f-103">使用 SchemaValidator 实用工具来排除与消息实例。</span><span class="sxs-lookup"><span data-stu-id="8426f-103">You use the SchemaValidator utility to troubleshoot problems with a message instance.</span></span> <span data-ttu-id="8426f-104">如果你收到一条消息，未通过验证，可以运行 SchemaValidator 实用工具来确定失败的原因。</span><span class="sxs-lookup"><span data-stu-id="8426f-104">If you receive a message that fails validation, you can run the SchemaValidator utility to determine the source of the failure.</span></span>  
  
 <span data-ttu-id="8426f-105">如果您使用的包含架构.dll 文件，程序集使用此实用程序和没有架构.xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="8426f-105">You use this utility if you are using an assembly that includes a schema .dll file, and you do not have a schema .xsd file.</span></span> <span data-ttu-id="8426f-106">SchemaValidator 实用工具，可以使用架构.dll 文件进行验证。</span><span class="sxs-lookup"><span data-stu-id="8426f-106">The SchemaValidator utility lets you validate using the schema .dll file.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="8426f-107">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="8426f-107">Location in SDK</span></span>  
 <span data-ttu-id="8426f-108">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="8426f-108">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator</span></span>  
  
## <a name="building-and-running-schemavalidator"></a><span data-ttu-id="8426f-109">生成和运行 SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="8426f-109">Building and Running SchemaValidator</span></span>  
  
#### <a name="to-build-the-schemavalidator-utility"></a><span data-ttu-id="8426f-110">生成 SchemaValidator 实用工具</span><span class="sxs-lookup"><span data-stu-id="8426f-110">To build the SchemaValidator utility</span></span>  
  
1. <span data-ttu-id="8426f-111">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="8426f-111">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="8426f-112">将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator。</span><span class="sxs-lookup"><span data-stu-id="8426f-112">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
3. <span data-ttu-id="8426f-113">在命令提示符处，键入**sn-k SchemaValidator.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="8426f-113">At the command prompt, type **sn -k SchemaValidator.snk**, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="8426f-114">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="8426f-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5. <span data-ttu-id="8426f-115">上**文件**菜单，依次指向**打开**，然后单击**打开的解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8426f-115">On the **File** menu, point to **Open**, and then click **Open Solution**.</span></span>  
  
6. <span data-ttu-id="8426f-116">将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator，选择**SchemaValidator.sln**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="8426f-116">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator, select **SchemaValidator.sln**, and then click **Open**.</span></span>  
  
7. <span data-ttu-id="8426f-117">在解决方案资源管理器中右键单击**SchemaValidator**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8426f-117">In Solution Explorer, right-click **SchemaValidator**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="8426f-118">在中**MessageInspector 属性**页上，单击**签名**选项卡，然后依次**程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="8426f-118">In the **MessageInspector Property**  page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span> <span data-ttu-id="8426f-119">选择**SchemaValidator.snk**中**选择一个强名称密钥文件**。</span><span class="sxs-lookup"><span data-stu-id="8426f-119">Select **SchemaValidator.snk** in **Choose a strong name key file**.</span></span>  
  
9. <span data-ttu-id="8426f-120">单击**SchemaValidator.cs**。</span><span class="sxs-lookup"><span data-stu-id="8426f-120">Click **SchemaValidator.cs**.</span></span>  
  
10. <span data-ttu-id="8426f-121">在代码中原有的以下行中键入相应的消息实例路径`Main`:</span><span class="sxs-lookup"><span data-stu-id="8426f-121">Type the appropriate message instance path in the following existing line of code in `Main`:</span></span>  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. <span data-ttu-id="8426f-122">替换原有的以下行中的代码`Main`到 Rnpip 程序集，然后选择相应的架构的引用：</span><span class="sxs-lookup"><span data-stu-id="8426f-122">Replace the following existing line of code in `Main` with a reference to the RNPIPs assembly, and then select the appropriate schema:</span></span>  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. <span data-ttu-id="8426f-123">右键单击**SchemaValidator**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="8426f-123">Right-click **SchemaValidator**, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="8426f-124">修改消息实例到你想要通过删除测试\< \!DOCTYPE...\>标记来指定从 XML 实例的标头的 DTD 文件。</span><span class="sxs-lookup"><span data-stu-id="8426f-124">Modify the message instance to you want to test by removing the \<\!DOCTYPE …\> tag specifying the DTD file from the header of the XML instance.</span></span>  
  
14. <span data-ttu-id="8426f-125">在消息实例的根节点，添加对其进行验证的架构的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="8426f-125">In the root node of the message instance, add an XML namespace of the schema that you will validate against.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8426f-126">准备好可由 SchemaValidator 实用工具进行验证的架构的示例，请参阅中的 Sample3A4.xml \<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\SchemaValidator。</span><span class="sxs-lookup"><span data-stu-id="8426f-126">For an example of a schema ready to be validated by the SchemaValidator utility, see Sample3A4.xml in \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
15. <span data-ttu-id="8426f-127">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**SchemaValidator.cs**，然后按 CTRL 和 F5 以运行此实用工具。</span><span class="sxs-lookup"><span data-stu-id="8426f-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **SchemaValidator.cs**, and then press CTRL and F5 to run the utility.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8426f-128">备注</span><span class="sxs-lookup"><span data-stu-id="8426f-128">Remarks</span></span>  
 <span data-ttu-id="8426f-129">因为[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 包含 SchemaValidator 代码，可以将逻辑添加到该实用工具。</span><span class="sxs-lookup"><span data-stu-id="8426f-129">Because the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes the SchemaValidator code, you can add logic to the utility.</span></span> <span data-ttu-id="8426f-130">例如，您可以使其提供一个命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="8426f-130">For example, you can make it a command-line utility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8426f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8426f-131">See Also</span></span>  
 [<span data-ttu-id="8426f-132">实用工具</span><span class="sxs-lookup"><span data-stu-id="8426f-132">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
