---
title: "如何更新使用的并行版本控制的映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b0e377f-92ab-483e-9f3c-222c7b5ac0b1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d463823a7038e1ead7e2de323da97eda372db76
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-update-a-map-using-side-by-side-versioning"></a><span data-ttu-id="56c9e-102">如何更新使用的并行版本控制的映射</span><span class="sxs-lookup"><span data-stu-id="56c9e-102">How to Update a Map Using Side-by-Side Versioning</span></span>
<span data-ttu-id="56c9e-103">某些 BizTalk 项目，比如地图，选择通过完全限定的强名称 (FQSN)，在这种情况下的绑定包括使用的版本。</span><span class="sxs-lookup"><span data-stu-id="56c9e-103">Some BizTalk artifacts, such as maps, are chosen by fully-qualified strong name (FQSN), in which case the bindings include the version used.</span></span> <span data-ttu-id="56c9e-104">这允许两个或多个图并排放置在共存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="56c9e-104">This allows two or more maps to coexist side by side in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="56c9e-105">因此，可以发送端口属性中选择其中一个接收位置属性中的入站的映射或出站映射映射。</span><span class="sxs-lookup"><span data-stu-id="56c9e-105">As a result, you can select one of the maps for inbound mapping in the receive location properties or outbound mapping in the send port properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="56c9e-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="56c9e-106">Prerequisites</span></span>  
 <span data-ttu-id="56c9e-107">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="56c9e-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-second-map-side-by-side-to-an-existing-map"></a><span data-ttu-id="56c9e-108">若要将第二个图并排显示添加到现有代码图</span><span class="sxs-lookup"><span data-stu-id="56c9e-108">To add a second map side by side to an existing map</span></span>  
  
1.  <span data-ttu-id="56c9e-109">打开 Visual Studio，然后打开包含映射的项目。</span><span class="sxs-lookup"><span data-stu-id="56c9e-109">Open Visual Studio, and then open the project containing the map.</span></span>  
  
2.  <span data-ttu-id="56c9e-110">在程序集中，打开该映射和进行代码更改到映射。</span><span class="sxs-lookup"><span data-stu-id="56c9e-110">Open the map in the assembly, and make a code change to the map.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56c9e-111">如果从业务流程，调用地图和地图引用是硬编码时，你可能需要对业务流程本身进行代码更改。</span><span class="sxs-lookup"><span data-stu-id="56c9e-111">If you call a map from an orchestration, and the map reference is hard-coded, you may need to make code changes to the orchestration itself.</span></span>  
  
3.  <span data-ttu-id="56c9e-112">更改程序集的版本号：</span><span class="sxs-lookup"><span data-stu-id="56c9e-112">Change the version number of the assembly:</span></span>  
  
    1.  <span data-ttu-id="56c9e-113">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="56c9e-113">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="56c9e-114">在**项目设计器**，单击**应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="56c9e-114">In the **Project Designer**, click the **Application** tab.</span></span>  
  
    3.  <span data-ttu-id="56c9e-115">在右窗格中，单击**程序集信息**。</span><span class="sxs-lookup"><span data-stu-id="56c9e-115">In the right pane, click **Assembly Information**.</span></span>  
  
    4.  <span data-ttu-id="56c9e-116">在**程序集信息**对话框框中，为指定值**程序集版本**字段以更改程序集版本号。</span><span class="sxs-lookup"><span data-stu-id="56c9e-116">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to change the assembly version number.</span></span> <span data-ttu-id="56c9e-117">您应更改仅主要或次要版本号。</span><span class="sxs-lookup"><span data-stu-id="56c9e-117">You should change only the major or minor version number.</span></span> <span data-ttu-id="56c9e-118">主版本号是序列中的第一个数字 (***n***.0.0.0); 的次版本号是序列中的第二个数字 (0。***n*** .0.0)。</span><span class="sxs-lookup"><span data-stu-id="56c9e-118">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span>  
  
    5.  <span data-ttu-id="56c9e-119">单击 **确定** 关闭 **程序集信息** 对话框。</span><span class="sxs-lookup"><span data-stu-id="56c9e-119">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
4.  <span data-ttu-id="56c9e-120">编译的程序集。</span><span class="sxs-lookup"><span data-stu-id="56c9e-120">Compile the assembly.</span></span>  
  
5.  <span data-ttu-id="56c9e-121">将程序集部署到组 （以及所有计算机）。</span><span class="sxs-lookup"><span data-stu-id="56c9e-121">Deploy the assembly to the group (and all computers).</span></span>  
  
## <a name="modifying-a-map-to-reflect-updated-version-numbers"></a><span data-ttu-id="56c9e-122">修改映射以反映更新版本号</span><span class="sxs-lookup"><span data-stu-id="56c9e-122">Modifying a Map to Reflect Updated Version Numbers</span></span>  
 <span data-ttu-id="56c9e-123">使用 脚本 functoid 可以在映射内调用 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="56c9e-123">.NET assemblies can be invoked from within a map by using the Scripting functoid.</span></span> <span data-ttu-id="56c9e-124">这样做非常灵活，并可以使开发者能够解决很多不同的自定义映射问题。</span><span class="sxs-lookup"><span data-stu-id="56c9e-124">This provides a great deal of flexibility and enables the developer to solve many different custom mapping problems.</span></span> <span data-ttu-id="56c9e-125">它同时也施加在地图上的唯一约束-它必须内部引用的程序集类型名称不仅也正在调用的完整的程序集版本号。</span><span class="sxs-lookup"><span data-stu-id="56c9e-125">It also imposes a unique constraint on the map—it must internally reference not only the assembly type name but also the full assembly version number being invoked.</span></span> <span data-ttu-id="56c9e-126">因此，如果更改了映射所调用的程序集版本号，则所有引用该程序集的链接都将中断。</span><span class="sxs-lookup"><span data-stu-id="56c9e-126">As a consequence, if the version number of the assembly called by the map changes, all of the links that reference the assembly will break.</span></span>  
  
 <span data-ttu-id="56c9e-127">若要避免此问题，我们建议，如果需要从映射调用程序集，则特定的程序集创建用于保存仅映射功能，并且固定此程序集的程序集版本号。</span><span class="sxs-lookup"><span data-stu-id="56c9e-127">To avoid this issue we recommend that if assemblies are required to be called from a map, a specific assembly is created to hold only map functionality and that the assembly version number of this assembly is fixed.</span></span> <span data-ttu-id="56c9e-128">这样，其他帮助器函数可以更新程序集的版本，而不会中断映射。</span><span class="sxs-lookup"><span data-stu-id="56c9e-128">In this way, other helper functions can have the assembly version updated without breaking the maps.</span></span>  
  
 <span data-ttu-id="56c9e-129">如果映射开发完成后更改了通过该映射引用的某个程序集，则应考虑在映射编辑器外更新该映射文件，使之反映已更新的版本号。</span><span class="sxs-lookup"><span data-stu-id="56c9e-129">If an assembly referenced from a map is changed after map development then consider updating the map file outside of the Map Editor to reflect the updated version numbers.</span></span>  
  
#### <a name="to-modify-a-map-file-to-reflect-updated-version-numbers"></a><span data-ttu-id="56c9e-130">若要修改图文件，以反映更新的版本的数字</span><span class="sxs-lookup"><span data-stu-id="56c9e-130">To modify a map file to reflect updated version numbers</span></span>  
  
1.  <span data-ttu-id="56c9e-131">使用**启动**菜单上，打开**记事本**。</span><span class="sxs-lookup"><span data-stu-id="56c9e-131">Using the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="56c9e-132">在**记事本**上**文件**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="56c9e-132">In **Notepad**, on the **File** menu, click **Open**.</span></span> <span data-ttu-id="56c9e-133">在 **打开** 对话框中，选择代码图文件您想要修改，然后单击 **打开**。</span><span class="sxs-lookup"><span data-stu-id="56c9e-133">In the **Open** dialog box, select the map file you want to modify, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="56c9e-134">在 **“编辑”** 菜单中，单击 **“查找”**。</span><span class="sxs-lookup"><span data-stu-id="56c9e-134">On the **Edit** menu, click **Find**.</span></span> <span data-ttu-id="56c9e-135">在 **查找** 对话框框中，输入 **程序集 =**, ，然后单击 **查找下一个**。</span><span class="sxs-lookup"><span data-stu-id="56c9e-135">In the **Find** dialog box, enter **Assembly=**, and then click **Find Next**.</span></span>  
  
4.  <span data-ttu-id="56c9e-136">如果存在对外部程序集的脚本引用，则记事本应该找到一个类似如下所示的 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="56c9e-136">If there is a script reference to an external assembly, Notepad should find an XML element like the following:</span></span>  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=  
    <token>  
    " Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
5.  <span data-ttu-id="56c9e-137">更新版本号。</span><span class="sxs-lookup"><span data-stu-id="56c9e-137">Update the version number.</span></span> <span data-ttu-id="56c9e-138">如果有多个实例，使用 **替换** 上 **编辑** 菜单。</span><span class="sxs-lookup"><span data-stu-id="56c9e-138">If there are multiple instances, use **Replace** on the **Edit** menu.</span></span>  
  
6.  <span data-ttu-id="56c9e-139">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="56c9e-139">Save the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56c9e-140">现在即可以用映射编辑器打开该映射。</span><span class="sxs-lookup"><span data-stu-id="56c9e-140">You can now open the map using the Map Editor.</span></span>