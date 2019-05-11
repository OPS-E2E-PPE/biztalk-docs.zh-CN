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
ms.openlocfilehash: 4eea6263fe104da17cfe9cea7f5cc7da8b08a2be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345240"
---
# <a name="generating-an-instance-edi"></a><span data-ttu-id="ef511-102">生成实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="ef511-102">Generating an Instance (EDI)</span></span>
<span data-ttu-id="ef511-103">在设计时，可以从 EDI 架构生成消息实例。</span><span class="sxs-lookup"><span data-stu-id="ef511-103">You can generate a message instance from an EDI schema at design time.</span></span> <span data-ttu-id="ef511-104">若要执行此操作，您使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="ef511-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span>  
  
 <span data-ttu-id="ef511-105">你可以生成完整的批处理的交换 （带有交换和组标头） 或事务集 （没有交换和组标头）。</span><span class="sxs-lookup"><span data-stu-id="ef511-105">You can generate either a complete batched interchange (with interchange and group headers) or a transaction set (without interchange and group headers).</span></span> <span data-ttu-id="ef511-106">如果您执行该操作来生成完整交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成包含一个交换标头，为每个架构的组和每个组的三个相同的事务集的每个架构文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-106">If you execute the operation to generate a complete interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with one interchange header, a group for each schema, and three identical transaction sets per group for each schema.</span></span> <span data-ttu-id="ef511-107">如果执行生成事务集的操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成具有单个事务集的文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-107">If you execute the operation to generate a transaction set, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a file with a single transaction set.</span></span>  
  
 <span data-ttu-id="ef511-108">若要生成完整的批的交换，请对批架构执行生成实例命令。</span><span class="sxs-lookup"><span data-stu-id="ef511-108">To generate a complete batched interchange, you execute the generate-instance command on the batch schema.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ef511-109">将在项目中，检测消息架构，并将自动包括这些架构的事务集。</span><span class="sxs-lookup"><span data-stu-id="ef511-109">will detect the message schemas in the project, and will automatically include transaction sets for those schemas.</span></span>  
  
 <span data-ttu-id="ef511-110">若要生成单个事务集，对消息架构执行生成实例命令。</span><span class="sxs-lookup"><span data-stu-id="ef511-110">To generate a single transaction set, you execute the generate-instance command on a message schema.</span></span> <span data-ttu-id="ef511-111">在这种情况下，批架构不必添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ef511-111">In this case, the batch schema does not need to be added to the project.</span></span> <span data-ttu-id="ef511-112">生成的实例将不包括交换或组的标头，但是，因此将需要手动添加以具有正常工作的 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="ef511-112">The generated instance will not include an interchange or group header, however, so you will have to add those manually to have a functional EDI interchange.</span></span>  
  
 <span data-ttu-id="ef511-113">当您生成一个实例，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]显示一个对话框，在其中指定该实例，包括分隔符和语法标识符中使用的配置。</span><span class="sxs-lookup"><span data-stu-id="ef511-113">When you generate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration used in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ef511-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="ef511-114">Prerequisites</span></span>  
 <span data-ttu-id="ef511-115">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="ef511-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a><span data-ttu-id="ef511-116">若要生成的批处理交换实例</span><span class="sxs-lookup"><span data-stu-id="ef511-116">To generate an instance of a batched interchange</span></span>  
  
1. <span data-ttu-id="ef511-117">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="ef511-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="ef511-118">将消息架构添加到每种类型的消息实例中所需的事务集的解决方案资源管理器中的项目。</span><span class="sxs-lookup"><span data-stu-id="ef511-118">Add a message schema to the project in Solution Explorer for each type of transaction set that you want in the message instance.</span></span> <span data-ttu-id="ef511-119">添加的项目到编码类型的批架构： Edifact_BatchSchema.xsd 或 X12_BatchSchema.xsd。</span><span class="sxs-lookup"><span data-stu-id="ef511-119">Add the batch schema for the type of encoding to the project: either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef511-120">批处理架构位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef511-120">The batch schemas are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ef511-121">无需生成项目以生成一个实例。</span><span class="sxs-lookup"><span data-stu-id="ef511-121">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="ef511-122">右键单击解决方案资源管理器中的批架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ef511-122">Right-click the batch schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="ef511-123">在中**属性**窗口中，将**生成实例输出类型**到**本机**或者**XML**。</span><span class="sxs-lookup"><span data-stu-id="ef511-123">In the **Properties** window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="ef511-124">选择**本机**会提示将生成具有.txt 扩展名的平面文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-124">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="ef511-125">选择**XML**会提示将生成的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-125">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="ef511-126">有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-126">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef511-127">如果不为输出实例文件名输入一个值，将为你选择一个。</span><span class="sxs-lookup"><span data-stu-id="ef511-127">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="ef511-128">该文件名将显示在输出窗口中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ef511-128">The filename will be displayed in the Output window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ef511-129">如果选择现有的文件，则现有文件的内容将替换此操作生成的内容。</span><span class="sxs-lookup"><span data-stu-id="ef511-129">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="ef511-130">右键单击批架构，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="ef511-130">Right-click the batch schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="ef511-131">在中**EDI 实例属性**对话框中，选择分隔符、 标识符和其他配置选项以使用在该实例中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ef511-131">In the **EDI Instance Properties** dialog box, select the separators, identifiers, and other configuration options to be used in that instance, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="ef511-132">验证操作起作用**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="ef511-132">Verify that the operation worked in the **Output** window.</span></span>  
  
8. <span data-ttu-id="ef511-133">若要查看该文件，请按**控制**并单击中的链接**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="ef511-133">To view the file, press **Control** and click the link in the **Output** window.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="ef511-134">在 BizTalk 编辑器窗口中将显示该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="ef511-134">will display the contents of the file in the BizTalk Editor window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef511-135">在生成一个包含 837I、 837 D 或 837p 的实例时，GS08 的值将错误地设置为 00401。</span><span class="sxs-lookup"><span data-stu-id="ef511-135">When generating an instance that contains an 837I, 837D, or 837P, the value of GS08 will be incorrectly set to 00401.</span></span> <span data-ttu-id="ef511-136">有关详细信息，请参阅[的已知问题与 EDI 解决方案一起使用的 XML 工具](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="ef511-136">For more information, see [Known Issues with XML Tools Used with EDI Solutions](../core/known-issues-with-xml-tools-used-with-edi-solutions.md).</span></span>  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a><span data-ttu-id="ef511-137">若要生成事务集的实例</span><span class="sxs-lookup"><span data-stu-id="ef511-137">To generate an instance of a transaction set</span></span>  
  
1. <span data-ttu-id="ef511-138">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="ef511-138">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="ef511-139">添加你想要生成的实例集的事务类型的架构。</span><span class="sxs-lookup"><span data-stu-id="ef511-139">Add the schema for the type of transaction set that you want to generate an instance for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef511-140">无需将批架构添加到此项目以生成事务集的实例。</span><span class="sxs-lookup"><span data-stu-id="ef511-140">You do not have to add the batch schema to the project to generate an instance of a transaction set.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef511-141">无需生成项目以生成一个实例。</span><span class="sxs-lookup"><span data-stu-id="ef511-141">You do not have to build the project to generate an instance.</span></span>  
  
2. <span data-ttu-id="ef511-142">右键单击解决方案资源管理器中的消息架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ef511-142">Right-click the message schema in Solution Explorer, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="ef511-143">在属性窗口中设置**生成实例输出类型**到**本机**或**XML**。</span><span class="sxs-lookup"><span data-stu-id="ef511-143">In the Properties window, set **Generate Instance Output Type** to **Native** or **XML**.</span></span> <span data-ttu-id="ef511-144">选择**本机**会提示将生成具有.txt 扩展名的平面文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-144">Selecting **Native** will prompt generation of a flat file with a .txt extension.</span></span> <span data-ttu-id="ef511-145">选择**XML**会提示将生成的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-145">Selecting **XML** will prompt generation of an XML file.</span></span>  
  
4. <span data-ttu-id="ef511-146">有关**输出实例文件名**、 输入的名称或浏览到的文件和选择的文件。</span><span class="sxs-lookup"><span data-stu-id="ef511-146">For **Output Instance Filename**, enter a name or browse to a file and select the file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef511-147">如果不为输出实例文件名输入一个值，将为你选择一个。</span><span class="sxs-lookup"><span data-stu-id="ef511-147">If you do not enter a value for the output instance filename, one will be chosen for you.</span></span> <span data-ttu-id="ef511-148">该文件名将显示在**输出**窗口中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ef511-148">The filename will be displayed in the **Output** window of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ef511-149">如果选择现有的文件，则现有文件的内容将替换此操作生成的内容。</span><span class="sxs-lookup"><span data-stu-id="ef511-149">If you select an existing file, the contents of the existing file will be replaced with the content generated by this operation.</span></span>  
  
5. <span data-ttu-id="ef511-150">右键单击消息架构，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="ef511-150">Right-click the message schema and then click **Generate Instance**.</span></span>  
  
6. <span data-ttu-id="ef511-151">在中**EDI 实例属性**对话框中，选择的配置选项，您想要，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ef511-151">In the **EDI Instance Properties** dialog box, select the configuration options that you want, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="ef511-152">验证是否在一条消息**输出**窗口中，该值指示操作成功。</span><span class="sxs-lookup"><span data-stu-id="ef511-152">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
8. <span data-ttu-id="ef511-153">若要查看该文件，请按**控制**并单击输出窗口中的链接。</span><span class="sxs-lookup"><span data-stu-id="ef511-153">To view the file, press **Control** and click the link in the Output window.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ef511-154">在 BizTalk 编辑器窗口中将显示该文件的内容。</span><span class="sxs-lookup"><span data-stu-id="ef511-154">will display the contents of the file in the BizTalk Editor window.</span></span>  
  
9. <span data-ttu-id="ef511-155">若要使工作的 EDI 消息，将添加到文本编辑器中的消息的交换和组标头。</span><span class="sxs-lookup"><span data-stu-id="ef511-155">To make a functional EDI message, add the interchange and group headers to the message in a text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef511-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef511-156">See Also</span></span>  
 <span data-ttu-id="ef511-157">[通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ef511-157">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="ef511-158">验证实例 (EDI)</span><span class="sxs-lookup"><span data-stu-id="ef511-158">Validating an Instance (EDI)</span></span>](../core/validating-an-instance-edi.md)