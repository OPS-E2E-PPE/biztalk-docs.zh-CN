---
title: "测试映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 265afd62-3c1d-4b9a-9f51-176b9b079241
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee4c59783dd72e94ee222c0ee165c7c8f90a32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="testing-a-map"></a><span data-ttu-id="53ed1-102">测试映射</span><span class="sxs-lookup"><span data-stu-id="53ed1-102">Testing a Map</span></span>
<span data-ttu-id="53ed1-103">在设计时，您可以在 EDI 项目中测试映射。</span><span class="sxs-lookup"><span data-stu-id="53ed1-103">You can test a map in an EDI project at design time.</span></span> <span data-ttu-id="53ed1-104">为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。</span><span class="sxs-lookup"><span data-stu-id="53ed1-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="53ed1-105">本主题介绍如何设置和使用**测试映射**的 XML 工具扩展的功能。</span><span class="sxs-lookup"><span data-stu-id="53ed1-105">This topic describes how to set up and use the **Test Map** feature of the XML Tool extension.</span></span>  
  
 <span data-ttu-id="53ed1-106">测试映射的方法是：指定一个源文档，并指定一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用于保存生成实例（具有虚构数据）的文件夹。</span><span class="sxs-lookup"><span data-stu-id="53ed1-106">You test a map by specifying a source document and specifying a folder where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will save a generated instance (with fictitious data).</span></span> <span data-ttu-id="53ed1-107">您还需要设置分隔符，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将使用该分隔符处理源文档，并根据 EDI 架构生成目标文档。</span><span class="sxs-lookup"><span data-stu-id="53ed1-107">You need to set the delimiters that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to process the source document and generate the destination document according to EDI schemas.</span></span> <span data-ttu-id="53ed1-108">这适用于所有值的**测试映射**输入映射的属性页中的属性：**生成实例**， **XML**，或**本机**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-108">This is true for all values of the **TestMap** input property in the map's property pages: **Generate Instance**, **XML**, or **Native**.</span></span> <span data-ttu-id="53ed1-109">它适用于**生成实例**因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要知道哪些分隔符来使用用于生成实例。</span><span class="sxs-lookup"><span data-stu-id="53ed1-109">It is true for **Generate Instance** because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] needs to know what delimiters to use to generate the instance.</span></span> <span data-ttu-id="53ed1-110">它适用于**XML**或**本机**因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要了解如何解释本机平面文件或 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="53ed1-110">It is true for **XML** or **Native** because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] needs to know how to interpret the native flat file or the XML file.</span></span> <span data-ttu-id="53ed1-111">您还需要设置生成输出文件时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将使用的分隔符。</span><span class="sxs-lookup"><span data-stu-id="53ed1-111">You also need to set the delimiters that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use when generating the output file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53ed1-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="53ed1-112">Prerequisites</span></span>  
 <span data-ttu-id="53ed1-113">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="53ed1-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-test-a-map"></a><span data-ttu-id="53ed1-114">测试映射</span><span class="sxs-lookup"><span data-stu-id="53ed1-114">To test a map</span></span>  
  
1.  <span data-ttu-id="53ed1-115">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，向项目添加要测试的映射，并向该项目添加该映射的源和目标架构。</span><span class="sxs-lookup"><span data-stu-id="53ed1-115">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], add the map that you want to test to a project, and add the source and destination schemas for that map to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53ed1-116">您不需要生成项目，以测试映射。</span><span class="sxs-lookup"><span data-stu-id="53ed1-116">You do not have to build the project to test the map.</span></span>  
  
2.  <span data-ttu-id="53ed1-117">右键单击代码图，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-117">Right-click the map and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="53ed1-118">在**属性**窗口中，设置**验证测试映射输入**到**True**如果你想要验证针对源架构的输入的文件。</span><span class="sxs-lookup"><span data-stu-id="53ed1-118">In the **Properties** window, set **Validate TestMap Input** to **True** if you want to validate the input file against the source schema.</span></span> <span data-ttu-id="53ed1-119">设置**验证测试映射输出**到**True**如果你想要将输出文件对照目标架构验证。</span><span class="sxs-lookup"><span data-stu-id="53ed1-119">Set **Validate TestMap Output** to **True** if you want to validate the output file against the destination schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53ed1-120">如果测试具有的映射**测试映射输入**属性设置为**本机**和**验证测试映射输入**和**验证测试映射输出**属性设置为**False**，仍将执行验证。</span><span class="sxs-lookup"><span data-stu-id="53ed1-120">If you test a map with the **TestMap Input** property set to **Native** and the **Validate TestMap Input** and **Validate TestMap Output** properties set to **False**, validation will still be performed.</span></span> <span data-ttu-id="53ed1-121">这是因为本机格式输入文件将被转换为 XML 格式，并且 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将针对架构验证 XML。</span><span class="sxs-lookup"><span data-stu-id="53ed1-121">This occurs because the native-formatted input file will be converted into XML format, and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will validate the XML against the schema.</span></span> <span data-ttu-id="53ed1-122">如果输入实例中不存在验证问题，验证机制将其发布错误，即使**验证测试映射输入**和**验证测试映射输出**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-122">If there are validation issues in the input instance, the validation mechanism will post errors, even though the **Validate TestMap Input** and **Validate TestMap Output** properties are set to **False**.</span></span>  
  
4.  <span data-ttu-id="53ed1-123">设置**测试映射输入**到**本机**.edi 扩展名的输入文件。</span><span class="sxs-lookup"><span data-stu-id="53ed1-123">Set **TestMap Input** to **Native** for an input file that has an .edi extension.</span></span> <span data-ttu-id="53ed1-124">将其设置为**XML**如果它具有.xml 扩展名。</span><span class="sxs-lookup"><span data-stu-id="53ed1-124">Set it to **XML** if it has an .xml extension.</span></span> <span data-ttu-id="53ed1-125">设置**测试映射输入**到**生成实例**能够[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成输入的实例，而不是你手动指定输入的实例。</span><span class="sxs-lookup"><span data-stu-id="53ed1-125">Set **TestMap Input** to **Generate Instance** to have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generate an input instance, rather than you designating an input instance manually.</span></span>  
  
5.  <span data-ttu-id="53ed1-126">设置**测试映射输出**到**本机**.edi 扩展名的输出文件。</span><span class="sxs-lookup"><span data-stu-id="53ed1-126">Set **TestMap Output** to **Native** for an output file that has an .edi extension.</span></span> <span data-ttu-id="53ed1-127">将其设置为**XML**如果它具有.xml 扩展名。</span><span class="sxs-lookup"><span data-stu-id="53ed1-127">Set it to **XML** if it has an .xml extension.</span></span>  
  
6.  <span data-ttu-id="53ed1-128">有关**测试映射输入实例**，浏览到你想要用于测试该映射，请选择它，输入实例，然后**打开**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-128">For **TestMap Input Instance**, browse to the input instance that you want to be used to test the map, select it, and then **Open**.</span></span> <span data-ttu-id="53ed1-129">如果你想要将此属性留空，设置**测试映射输入**到**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-129">If you want to leave this property blank, set **TestMap Input** to **Generate Instance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53ed1-130">你必须指定为输入的实例**测试映射输入实例**或设置**测试映射输入**到**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-130">You have to either designate an input instance for **TestMap Input Instance** or set **TestMap Input** to **Generate Instance**.</span></span> <span data-ttu-id="53ed1-131">否则，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="53ed1-131">If not, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate an error.</span></span>  
  
7.  <span data-ttu-id="53ed1-132">有关**测试映射输出实例**，浏览到你想要保存输出实例中的，输入输出实例的名称，然后单击的位置**保存**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-132">For **TestMap Output Instance**, browse to the location you want to save the output instance at, enter a name for the output instance, and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53ed1-133">如果未指定输出实例，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将创建一个输出文件，将该输出文件放置到一个文件夹中，并指明文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="53ed1-133">If you do not designate an output instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will create an output file, place the output file into a folder, and indicate the file name and path.</span></span>  
  
8.  <span data-ttu-id="53ed1-134">右键单击你要测试，，然后单击地图**测试映射**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-134">Right-click the map you are testing, and then click **Test Map**.</span></span>  
  
9. <span data-ttu-id="53ed1-135">在 X12 **EDI 实例属性**对话框框中，请确保所有属性都是与输入和输出实例的设置一致。</span><span class="sxs-lookup"><span data-stu-id="53ed1-135">In the X12 **EDI Instance Properties** dialog box, make sure that all properties are consistent with the settings for the input and output instances.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="53ed1-136">将显示**EDI 实例属性**对话框中，在测试映射过程中两次： 一次针对解释输入的消息实例，一次用于生成输出消息实例。</span><span class="sxs-lookup"><span data-stu-id="53ed1-136"> will display the **EDI Instance Properties** dialog box twice during the TestMap process: once for interpreting the input message instance and once for generating the output message instance.</span></span> <span data-ttu-id="53ed1-137">但是，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可能多次显示该对话框，并且可能针对非 EDI 架构显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="53ed1-137">However, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may display the dialog box more than just twice and may display the dialog box for non-EDI schema.</span></span> <span data-ttu-id="53ed1-138">如果是这样，则单击**确定**以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="53ed1-138">If so, click **OK** to close the dialog box.</span></span>  
  
10. <span data-ttu-id="53ed1-139">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="53ed1-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53ed1-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53ed1-140">See Also</span></span>  
 [<span data-ttu-id="53ed1-141">通过使用设计时 XML 工具</span><span class="sxs-lookup"><span data-stu-id="53ed1-141">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)