---
title: 验证实例 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0fe4e87-5ab4-41e4-8ceb-8f6cf40cae0b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58150705b504193a527be729028b00d4384325d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993934"
---
# <a name="validating-an-instance-edi"></a><span data-ttu-id="7e8d1-102">验证实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="7e8d1-102">Validating an Instance (EDI)</span></span>
<span data-ttu-id="7e8d1-103">您可以在设计时验证针对其 EDI 架构实例。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-103">You can validate an instance against its EDI schema at design time.</span></span> <span data-ttu-id="7e8d1-104">为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="7e8d1-105">验证的实例可以是单个事务集 （没有交换和组标头）、 是将单个事务集 （带有交换和组标头），包含的交换或具有多个事务集 （具有完整的批的交换交换和组标头）。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-105">The instance that you validate can be a single transaction set (without interchange and group headers), an interchange with a single transaction set (with interchange and group headers), or a complete batched interchange with multiple transaction sets (with interchange and group headers).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e8d1-106">不支持验证 xml 保留交换。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-106">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="7e8d1-107">但是，支持的保留的交换的 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-107">However, validation of an EDI preserved interchange is supported.</span></span>  
  
 <span data-ttu-id="7e8d1-108">验证实例操作的执行 EDI 和 XSD 验证。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-108">The validate-instance operation performs both EDI and XSD validation.</span></span>  
  
 <span data-ttu-id="7e8d1-109">在验证实例时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会显示一个对话框，可在其中指定该实例中要验证的配置，包括分隔符和语法标识符。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-109">When you validate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration to be validated in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7e8d1-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="7e8d1-110">Prerequisites</span></span>  
 <span data-ttu-id="7e8d1-111">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-an-instance-against-its-schema"></a><span data-ttu-id="7e8d1-112">若要验证针对其架构实例</span><span class="sxs-lookup"><span data-stu-id="7e8d1-112">To validate an instance against its schema</span></span>  
  
1. <span data-ttu-id="7e8d1-113">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span>  
  
2. <span data-ttu-id="7e8d1-114">在解决方案资源管理器，向项目添加所需的消息实例的所有架构。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-114">In Solution Explorer, add to the project all schemas required for the message instance.</span></span>  
  
   1. <span data-ttu-id="7e8d1-115">如果您要验证单个事务集没有交换和组标头，添加该事务集的文档架构。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-115">If you are validating a single transaction set without interchange and group headers, add the document schema for that transaction set.</span></span>  
  
   2. <span data-ttu-id="7e8d1-116">如果验证的是包含一个事务集的交换，则向项目添加该事务的架构和消息使用的编码类型的批架构（即 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 中的 Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd）。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-116">If you are validating an interchange with a single transaction set, add to the project the schema for the transaction and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="7e8d1-117">所需的批架构验证信封的实例。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-117">The batch schema is required to validate the envelope of the instance.</span></span> <span data-ttu-id="7e8d1-118">如果您打算使用仅在消息架构，将不验证信封。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-118">If you were to use only the message schema, the envelope would not be validated.</span></span>  
  
   3. <span data-ttu-id="7e8d1-119">如果验证的是包含多个事务集的批处理交换，则向项目添加消息实例中各事务集组的架构和消息使用的编码类型的批架构（即 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 中的 Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd）。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-119">If you are validating a batched interchange with multiple transaction sets, add to the project the schemas for each transaction set group in the message instance, and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="7e8d1-120">如果已自定义服务架构，必须文档 （事务集） 架构除了包括自定义服务架构在 BizTalk 项目中，并且如有必要，批架构。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-120">If you have customized the service schema, you will have to include the custom service schema in the BizTalk project, in addition to the document (transaction set) schema(s) and if necessary, the batch schema.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="7e8d1-121">无需生成项目以验证实例。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-121">You do not have to build the project to validate an instance.</span></span>  
  
3. <span data-ttu-id="7e8d1-122">在解决方案资源管理器中显示架构的属性页，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e8d1-122">Display the property page for the schema in Solution Explorer, as follows:</span></span>  
  
   1.  <span data-ttu-id="7e8d1-123">如果您要验证单个事务集，右键单击该事务集，该文档架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-123">If you are validating a single transaction set, right-click the document schema for that transaction set, and then click **Properties**.</span></span>  
  
   2.  <span data-ttu-id="7e8d1-124">如果您要验证是包含单个事务集的交换或包含多个事务集的批处理的交换，右键单击批架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 架构），然后单击**属性**.</span><span class="sxs-lookup"><span data-stu-id="7e8d1-124">If you are validating an interchange with a single transaction set or a batched interchange with multiple transaction sets, right-click the batch schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd schema), and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="7e8d1-125">在此架构中，属性窗口中的**输入实例文件名**输入名称和你想要验证，或浏览到该文件，选择它，，然后单击消息实例路径**确定**。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-125">In Properties window for the schema, for **Input Instance Filename** enter the name and path of the message instance that you want to validate, or browse to the file, select it, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="7e8d1-126">有关**验证实例输入类型**，输入要进行验证的文件类型：**本机**EDI 文件或**XML**的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-126">For **Validate Instance Input Type**, enter the type of the file to be validate: **Native** for a EDI file or **XML** for an XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7e8d1-127">不支持验证 xml 保留交换。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-127">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="7e8d1-128">如果您选择的 XML**验证实例输入类型**属性验证保留的交换时，该操作将失败，并且不会返回。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-128">If you select XML for the **Validate Instance Input Type** property when validating a preserved interchange, the operation will fail and nothing will be returned.</span></span> <span data-ttu-id="7e8d1-129">但是，如果您选择**本机**有关**验证实例输入类型**时验证保留的交换，操作将成功。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-129">However, if you select **Native** for the **Validate Instance Input Type** when validating a preserved interchange, the operation will succeed.</span></span>  
  
6. <span data-ttu-id="7e8d1-130">右键单击消息架构 （Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd 如果验证是包含单个事务集的交换或批处理的交换），然后单击**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-130">Right-click the message schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd if validating an interchange with a single transaction set or a batched interchange) and then click **Validate Instance**.</span></span>  
  
7. <span data-ttu-id="7e8d1-131">在中**EDI 实例属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7e8d1-131">In the **EDI Instance Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="7e8d1-132">如果实例应使用重复分隔符，则选择**重复分隔符**。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-132">If your instance should use a repetition separator, select **Repetition separator**.</span></span>  
  
   2.  <span data-ttu-id="7e8d1-133">如果实例应使用尾部分隔符，则选择**是**有关**使用尾部分隔符**。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-133">If your instance should use trailing delimiters, select **Yes** for **Use trailing delimiters**.</span></span>  
  
   3.  <span data-ttu-id="7e8d1-134">如果实例应使用字符集以外**基本**，选择**扩展**或**Unicode**中**语法标识符**。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-134">If your instance should use a character set other than **Basic**, select **Extended** or **Unicode** in **Syntax identifier**.</span></span>  
  
   4.  <span data-ttu-id="7e8d1-135">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-135">Click **OK**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="7e8d1-136">**EDI 实例属性**可能会出现第二次后单击了对话框**确定**。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-136">The **EDI Instance Properties** dialog box might appear a second time after you have clicked **OK**.</span></span> <span data-ttu-id="7e8d1-137">如果是这样，请单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-137">If so, click **OK** again.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="7e8d1-138">**EDI 实例属性**对话框将填充与针对同一登录的用户运行的最后一个验证实例操作中使用的相同值。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-138">The **EDI Instance Properties** dialog box will be populated with the same values used in the last validate-instance operation that was run for the same logged-in user.</span></span>  
  
8. <span data-ttu-id="7e8d1-139">验证是否在一条消息**输出**窗口中，该值指示操作成功。</span><span class="sxs-lookup"><span data-stu-id="7e8d1-139">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8d1-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e8d1-140">See Also</span></span>  
 <span data-ttu-id="7e8d1-141">[通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7e8d1-141">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="7e8d1-142">生成实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="7e8d1-142">Generating an Instance (EDI)</span></span>](../core/generating-an-instance-edi.md)