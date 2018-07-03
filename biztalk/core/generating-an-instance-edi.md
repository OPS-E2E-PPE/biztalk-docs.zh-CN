---
title: 生成实例 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362b9803-4d4a-4d17-9ad6-439ec4c7d8aa
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82674b175ad1c408b6ddb9f7823427a550288e96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999294"
---
# <a name="generating-an-instance-edi"></a><span data-ttu-id="46050-102">生成实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="46050-102">Generating an Instance (EDI)</span></span>
<span data-ttu-id="46050-103">在设计阶段，可以从 EDI 架构生成消息实例。</span><span class="sxs-lookup"><span data-stu-id="46050-103">You can generate a message instance from an EDI schema at design time.</span></span> <span data-ttu-id="46050-104">为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。</span><span class="sxs-lookup"><span data-stu-id="46050-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span>  
  
 <span data-ttu-id="46050-105">可以生成完整的批交换（带有交换和组标头）或者事务集（没有交换和组标头）。</span><span class="sxs-lookup"><span data-stu-id="46050-105">You can generate either a complete batched interchange (with interchange and group headers) or a transaction set (without interchange and group headers).</span></span> <span data-ttu-id="46050-106">如果执行生成完整交换的操作，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将生成具有一个交换标头的文件，并且为每个架构生成一个组，为每个架构的每个组生成三个相同的事务集。</span><span class="sxs-lookup"><span data-stu-id="46050-106">If you execute the operation to generate a complete interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with one interchange header, a group for each schema, and three identical transaction sets per group for each schema.</span></span> <span data-ttu-id="46050-107">如果执行生成事务集的操作，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将生成具有单个事务集的文件。</span><span class="sxs-lookup"><span data-stu-id="46050-107">If you execute the operation to generate a transaction set, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with a single transaction set.</span></span>  
  
 <span data-ttu-id="46050-108">要生成一个完整的批交换，可对批架构执行生成实例命令。</span><span class="sxs-lookup"><span data-stu-id="46050-108">To generate a complete batched interchange, you execute the generate-instance command on the batch schema.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="46050-109"> 将检测项目中的消息架构，并且将自动包括这些架构的事务集。</span><span class="sxs-lookup"><span data-stu-id="46050-109"> will detect the message schemas in the project, and will automatically include transaction sets for those schemas.</span></span>  
  
 <span data-ttu-id="46050-110">要生成单个事务集，可以对消息架构执行生成实例命令。</span><span class="sxs-lookup"><span data-stu-id="46050-110">To generate a single transaction set, you execute the generate-instance command on a message schema.</span></span> <span data-ttu-id="46050-111">在此情况下，不需要将批架构添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="46050-111">In this case, the batch schema does not need to be added to the project.</span></span> <span data-ttu-id="46050-112">但是，生成的实例将不包括交换或组标头，因此，您必须手动添加以获得能够工作的 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="46050-112">The generated instance will not include an interchange or group header, however, so you will have to add those manually to have a functional EDI interchange.</span></span>  
  
 <span data-ttu-id="46050-113">在生成实例时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会显示一个对话框，可在其中指定该实例中使用的配置，包括分隔符和语法标识符。</span><span class="sxs-lookup"><span data-stu-id="46050-113">When you generate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration used in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="46050-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="46050-114">Prerequisites</span></span>  
 <span data-ttu-id="46050-115">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="46050-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a><span data-ttu-id="46050-116">若要生成的批处理交换实例</span><span class="sxs-lookup"><span data-stu-id="46050-116">To generate an instance of a batched interchange</span></span>  
  
1. <span data-ttu-id="46050-117">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="46050-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="46050-118">在解决方案资源管理器中，针对要在消息实例中包括的每种类型的事务集向项目添加消息架构。</span><span class="sxs-lookup"><span data-stu-id="46050-118">Add a message schema to the project in Solution Explorer for each type of transaction set that you want in the message instance.</span></span> <span data-ttu-id="46050-119">添加的项目到编码类型的批架构： Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd。</span><span class="sxs-lookup"><span data-stu-id="46050-119">Add the batch schema for the type of encoding to the project: either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46050-120">批处理架构位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="46050-120">The batch schemas are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="46050-121">您不需要生成项目来生成实例。</span><span class="sxs-lookup"><span data-stu-id="46050-121">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="46050-122">右键单击解决方案资源管理器中的批架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="46050-122">Right-click the batch schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="46050-123">在中**属性**窗口中，将**生成实例输出类型**到**本机**或者**XML**。</span><span class="sxs-lookup"><span data-stu-id="46050-123">In the **Properties** window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="46050-124">选择**本机**会提示将生成具有.txt 扩展名的平面文件。</span><span class="sxs-lookup"><span data-stu-id="46050-124">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="46050-125">选择**XML**会提示将生成的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="46050-125">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="46050-126">有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。</span><span class="sxs-lookup"><span data-stu-id="46050-126">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46050-127">如果没有为输出实例文件名输入一个值，系统将为您选择一个文件名。</span><span class="sxs-lookup"><span data-stu-id="46050-127">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="46050-128">该文件名将显示在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“输出”窗口中。</span><span class="sxs-lookup"><span data-stu-id="46050-128">The filename will be displayed in the Output window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="46050-129">如果选择了某个现有文件，将使用此操作生成的内容替换现有文件的内容。</span><span class="sxs-lookup"><span data-stu-id="46050-129">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="46050-130">右键单击批架构，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="46050-130">Right-click the batch schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="46050-131">在中**EDI 实例属性**对话框中，选择分隔符、 标识符和其他配置选项以使用在该实例中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46050-131">In the **EDI Instance Properties** dialog box, select the separators, identifiers, and other configuration options to be used in that instance, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="46050-132">验证操作起作用**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="46050-132">Verify that the operation worked in the **Output** window.</span></span>  
  
8. <span data-ttu-id="46050-133">若要查看该文件，请按**控制**并单击中的链接**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="46050-133">To view the file, press **Control** and click the link in the **Output** window.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="46050-134"> 在 BizTalk 编辑器窗口中将显示该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="46050-134"> will display the contents of the file in the BizTalk Editor window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46050-135">在生成一个包含 837I、 837 D 或 837p 的实例时，GS08 的值将错误地设置为 00401。</span><span class="sxs-lookup"><span data-stu-id="46050-135">When generating an instance that contains an 837I, 837D, or 837P, the value of GS08 will be incorrectly set to 00401.</span></span> <span data-ttu-id="46050-136">有关详细信息，请参阅[的已知问题与 EDI 解决方案一起使用的 XML 工具](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="46050-136">For more information, see [Known Issues with XML Tools Used with EDI Solutions](../core/known-issues-with-xml-tools-used-with-edi-solutions.md).</span></span>  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a><span data-ttu-id="46050-137">若要生成事务集的实例</span><span class="sxs-lookup"><span data-stu-id="46050-137">To generate an instance of a transaction set</span></span>  
  
1. <span data-ttu-id="46050-138">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="46050-138">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="46050-139">添加要为其生成实例的事务集类型的架构。</span><span class="sxs-lookup"><span data-stu-id="46050-139">Add the schema for the type of transaction set that you want to generate an instance for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46050-140">无需将批架构添加到项目即可生成事务集的实例。</span><span class="sxs-lookup"><span data-stu-id="46050-140">You do not have to add the batch schema to the project to generate an instance of a transaction set.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46050-141">您不需要生成项目来生成实例。</span><span class="sxs-lookup"><span data-stu-id="46050-141">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="46050-142">右键单击解决方案资源管理器中的消息架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="46050-142">Right-click the message schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="46050-143">在属性窗口中设置**生成实例输出类型**到**本机**或**XML**。</span><span class="sxs-lookup"><span data-stu-id="46050-143">In the Properties window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="46050-144">选择**本机**会提示将生成具有.txt 扩展名的平面文件。</span><span class="sxs-lookup"><span data-stu-id="46050-144">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="46050-145">选择**XML**会提示将生成的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="46050-145">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="46050-146">有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。</span><span class="sxs-lookup"><span data-stu-id="46050-146">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46050-147">如果没有为输出实例文件名输入一个值，系统将为您选择一个文件名。</span><span class="sxs-lookup"><span data-stu-id="46050-147">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="46050-148">该文件名将显示在**输出**窗口中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="46050-148">The filename will be displayed in the **Output** window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="46050-149">如果选择了某个现有文件，将使用此操作生成的内容替换现有文件的内容。</span><span class="sxs-lookup"><span data-stu-id="46050-149">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="46050-150">右键单击消息架构，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="46050-150">Right-click the message schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="46050-151">在中**EDI 实例属性**对话框中，选择的配置选项，您想要，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46050-151">In the **EDI Instance Properties** dialog box, select the configuration options that you want, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="46050-152">验证是否在一条消息**输出**窗口中，该值指示操作成功。</span><span class="sxs-lookup"><span data-stu-id="46050-152">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
8. <span data-ttu-id="46050-153">若要查看该文件，请按**控制**并单击输出窗口中的链接。</span><span class="sxs-lookup"><span data-stu-id="46050-153">To view the file, press **Control** and click the link in the Output window.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="46050-154"> 在 BizTalk 编辑器窗口中将显示该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="46050-154"> will display the contents of the file in the BizTalk Editor window.</span></span>  
  
9. <span data-ttu-id="46050-155">若要生成可工作的 EDI 消息，请在文本编辑器中将交换和组标头添加到消息中。</span><span class="sxs-lookup"><span data-stu-id="46050-155">To make a functional EDI message, add the interchange and group headers to the message in a text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46050-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="46050-156">See Also</span></span>  
 <span data-ttu-id="46050-157">[通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="46050-157">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="46050-158">验证实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="46050-158">Validating an Instance (EDI)</span></span>](../core/validating-an-instance-edi.md)