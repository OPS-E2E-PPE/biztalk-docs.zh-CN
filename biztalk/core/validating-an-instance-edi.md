---
title: "验证实例 (EDI) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0fe4e87-5ab4-41e4-8ceb-8f6cf40cae0b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cceea8afe67f7e69b3ee842198d9a5373a972d04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-an-instance-edi"></a><span data-ttu-id="767b6-102">验证实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="767b6-102">Validating an Instance (EDI)</span></span>
<span data-ttu-id="767b6-103">你可以在设计时验证对照其 EDI 架构实例。</span><span class="sxs-lookup"><span data-stu-id="767b6-103">You can validate an instance against its EDI schema at design time.</span></span> <span data-ttu-id="767b6-104">为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。</span><span class="sxs-lookup"><span data-stu-id="767b6-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="767b6-105">你验证该实例可以使用单个事务集 （具有交换和组标题） 的交换或使用多个事务集 （具有完成批处理的交换单个事务设置 （而无需交换和组标头）交换标题和组标题）。</span><span class="sxs-lookup"><span data-stu-id="767b6-105">The instance that you validate can be a single transaction set (without interchange and group headers), an interchange with a single transaction set (with interchange and group headers), or a complete batched interchange with multiple transaction sets (with interchange and group headers).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="767b6-106">不支持验证的 XML 保留交换。</span><span class="sxs-lookup"><span data-stu-id="767b6-106">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="767b6-107">但是，支持的保留交换 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="767b6-107">However, validation of an EDI preserved interchange is supported.</span></span>  
  
 <span data-ttu-id="767b6-108">验证实例操作执行 EDI 和 XSD 验证。</span><span class="sxs-lookup"><span data-stu-id="767b6-108">The validate-instance operation performs both EDI and XSD validation.</span></span>  
  
 <span data-ttu-id="767b6-109">在验证实例时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会显示一个对话框，可在其中指定该实例中要验证的配置，包括分隔符和语法标识符。</span><span class="sxs-lookup"><span data-stu-id="767b6-109">When you validate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration to be validated in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="767b6-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="767b6-110">Prerequisites</span></span>  
 <span data-ttu-id="767b6-111">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="767b6-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-an-instance-against-its-schema"></a><span data-ttu-id="767b6-112">若要验证对照其架构实例</span><span class="sxs-lookup"><span data-stu-id="767b6-112">To validate an instance against its schema</span></span>  
  
1.  <span data-ttu-id="767b6-113">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="767b6-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span>  
  
2.  <span data-ttu-id="767b6-114">在解决方案资源管理器向项目中添加所需的消息实例的所有架构。</span><span class="sxs-lookup"><span data-stu-id="767b6-114">In Solution Explorer, add to the project all schemas required for the message instance.</span></span>  
  
    1.  <span data-ttu-id="767b6-115">如果您要验证设置而无需交换和组标头单个事务，将添加为该事务集的文档架构。</span><span class="sxs-lookup"><span data-stu-id="767b6-115">If you are validating a single transaction set without interchange and group headers, add the document schema for that transaction set.</span></span>  
  
    2.  <span data-ttu-id="767b6-116">如果验证的是包含一个事务集的交换，则向项目添加该事务的架构和消息使用的编码类型的批架构（即 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 中的 Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd）。</span><span class="sxs-lookup"><span data-stu-id="767b6-116">If you are validating an interchange with a single transaction set, add to the project the schema for the transaction and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="767b6-117">要验证的信封中实例，需使用批处理架构。</span><span class="sxs-lookup"><span data-stu-id="767b6-117">The batch schema is required to validate the envelope of the instance.</span></span> <span data-ttu-id="767b6-118">如果你是使用仅的消息架构，将不验证信封。</span><span class="sxs-lookup"><span data-stu-id="767b6-118">If you were to use only the message schema, the envelope would not be validated.</span></span>  
  
    3.  <span data-ttu-id="767b6-119">如果验证的是包含多个事务集的批处理交换，则向项目添加消息实例中各事务集组的架构和消息使用的编码类型的批架构（即 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 中的 Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd）。</span><span class="sxs-lookup"><span data-stu-id="767b6-119">If you are validating a batched interchange with multiple transaction sets, add to the project the schemas for each transaction set group in the message instance, and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="767b6-120">如果你已自定义服务架构，你将必须包括在 BizTalk 项目中，自定义服务架构此外到的文档 （事务集） 架构和必要时，批处理架构。</span><span class="sxs-lookup"><span data-stu-id="767b6-120">If you have customized the service schema, you will have to include the custom service schema in the BizTalk project, in addition to the document (transaction set) schema(s) and if necessary, the batch schema.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="767b6-121">无需生成项目，以验证实例。</span><span class="sxs-lookup"><span data-stu-id="767b6-121">You do not have to build the project to validate an instance.</span></span>  
  
3.  <span data-ttu-id="767b6-122">在解决方案资源管理器，显示架构的属性页，如下所示：</span><span class="sxs-lookup"><span data-stu-id="767b6-122">Display the property page for the schema in Solution Explorer, as follows:</span></span>  
  
    1.  <span data-ttu-id="767b6-123">如果您要验证单个事务集，右键单击该组事务的文档架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="767b6-123">If you are validating a single transaction set, right-click the document schema for that transaction set, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="767b6-124">如果您要验证使用单个事务集的交换或使用多个事务集批处理的交换，右键单击批处理架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 架构），然后单击**属性**.</span><span class="sxs-lookup"><span data-stu-id="767b6-124">If you are validating an interchange with a single transaction set or a batched interchange with multiple transaction sets, right-click the batch schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd schema), and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="767b6-125">对于架构，属性窗口中为**输入实例 Filename**输入的名称和你想要验证，或浏览到文件，选择它，，然后单击消息实例的路径**确定**。</span><span class="sxs-lookup"><span data-stu-id="767b6-125">In Properties window for the schema, for **Input Instance Filename** enter the name and path of the message instance that you want to validate, or browse to the file, select it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="767b6-126">有关**验证实例输入类型**，输入要将验证的文件类型：**本机**EDI 文件或**XML**有关 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="767b6-126">For **Validate Instance Input Type**, enter the type of the file to be validate: **Native** for a EDI file or **XML** for an XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="767b6-127">不支持验证的 XML 保留交换。</span><span class="sxs-lookup"><span data-stu-id="767b6-127">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="767b6-128">如果你选择 XML for**验证实例输入类型**属性验证保留的交换时，操作将失败，并且将返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="767b6-128">If you select XML for the **Validate Instance Input Type** property when validating a preserved interchange, the operation will fail and nothing will be returned.</span></span> <span data-ttu-id="767b6-129">但是，如果你选择**本机**为**验证实例输入类型**时验证保留的交换，操作将成功。</span><span class="sxs-lookup"><span data-stu-id="767b6-129">However, if you select **Native** for the **Validate Instance Input Type** when validating a preserved interchange, the operation will succeed.</span></span>  
  
6.  <span data-ttu-id="767b6-130">右键单击消息架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 如果验证使用单个事务集的交换或批处理的交换），然后单击**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="767b6-130">Right-click the message schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd if validating an interchange with a single transaction set or a batched interchange) and then click **Validate Instance**.</span></span>  
  
7.  <span data-ttu-id="767b6-131">在**EDI 实例属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="767b6-131">In the **EDI Instance Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="767b6-132">如果你的实例应使用重复分隔符，则选择**重复分隔符**。</span><span class="sxs-lookup"><span data-stu-id="767b6-132">If your instance should use a repetition separator, select **Repetition separator**.</span></span>  
  
    2.  <span data-ttu-id="767b6-133">如果你的实例应使用尾随分隔符，则选择**是**为**尾随分隔符的使用**。</span><span class="sxs-lookup"><span data-stu-id="767b6-133">If your instance should use trailing delimiters, select **Yes** for **Use trailing delimiters**.</span></span>  
  
    3.  <span data-ttu-id="767b6-134">如果你的实例应使用的字符集以外**基本**，选择**扩展**或**Unicode**中**语法标识符**。</span><span class="sxs-lookup"><span data-stu-id="767b6-134">If your instance should use a character set other than **Basic**, select **Extended** or **Unicode** in **Syntax identifier**.</span></span>  
  
    4.  <span data-ttu-id="767b6-135">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="767b6-135">Click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="767b6-136">**EDI 实例属性**可能会出现第二次后单击了对话框**确定**。</span><span class="sxs-lookup"><span data-stu-id="767b6-136">The **EDI Instance Properties** dialog box might appear a second time after you have clicked **OK**.</span></span> <span data-ttu-id="767b6-137">如果是这样，则单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="767b6-137">If so, click **OK** again.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="767b6-138">**EDI 实例属性**对话框中将使用相同的值已运行的最后一个验证实例操作中使用的同一个登录的用户进行填充。</span><span class="sxs-lookup"><span data-stu-id="767b6-138">The **EDI Instance Properties** dialog box will be populated with the same values used in the last validate-instance operation that was run for the same logged-in user.</span></span>  
  
8.  <span data-ttu-id="767b6-139">验证是否有一条消息采用**输出**窗口，该值指示该操作成功。</span><span class="sxs-lookup"><span data-stu-id="767b6-139">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767b6-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="767b6-140">See Also</span></span>  
 <span data-ttu-id="767b6-141">[通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="767b6-141">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="767b6-142">生成实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="767b6-142">Generating an Instance (EDI)</span></span>](../core/generating-an-instance-edi.md)