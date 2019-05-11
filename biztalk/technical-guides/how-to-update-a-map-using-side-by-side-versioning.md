---
title: 如何更新使用的并行版本控制的映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b0e377f-92ab-483e-9f3c-222c7b5ac0b1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ec209d2fb8b2900e27e6699afe722b75c72e0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400251"
---
# <a name="how-to-update-a-map-using-side-by-side-versioning"></a><span data-ttu-id="0bc49-102">如何更新使用的并行版本控制的映射</span><span class="sxs-lookup"><span data-stu-id="0bc49-102">How to Update a Map Using Side-by-Side Versioning</span></span>
<span data-ttu-id="0bc49-103">某些 BizTalk 项目，如映射，通过完全限定的强名称 (FQSN)，选择在这种情况下的绑定包括所使用的版本。</span><span class="sxs-lookup"><span data-stu-id="0bc49-103">Some BizTalk artifacts, such as maps, are chosen by fully-qualified strong name (FQSN), in which case the bindings include the version used.</span></span> <span data-ttu-id="0bc49-104">这允许两个或多个映射以并排放置在共存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0bc49-104">This allows two or more maps to coexist side by side in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="0bc49-105">因此，可以在发送端口属性中选择入站的映射的接收位置属性中或出站映射的映射之一。</span><span class="sxs-lookup"><span data-stu-id="0bc49-105">As a result, you can select one of the maps for inbound mapping in the receive location properties or outbound mapping in the send port properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0bc49-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="0bc49-106">Prerequisites</span></span>  
 <span data-ttu-id="0bc49-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="0bc49-107">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-second-map-side-by-side-to-an-existing-map"></a><span data-ttu-id="0bc49-108">向现有地图添加第二个图并排显示</span><span class="sxs-lookup"><span data-stu-id="0bc49-108">To add a second map side by side to an existing map</span></span>  
  
1.  <span data-ttu-id="0bc49-109">打开 Visual Studio，然后打开包含该映射的项目。</span><span class="sxs-lookup"><span data-stu-id="0bc49-109">Open Visual Studio, and then open the project containing the map.</span></span>  
  
2.  <span data-ttu-id="0bc49-110">在程序集中，打开代码图并进行代码更改到映射。</span><span class="sxs-lookup"><span data-stu-id="0bc49-110">Open the map in the assembly, and make a code change to the map.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0bc49-111">如果从业务流程调用映射和映射引用进行硬编码时，可能需要对业务流程本身进行代码更改。</span><span class="sxs-lookup"><span data-stu-id="0bc49-111">If you call a map from an orchestration, and the map reference is hard-coded, you may need to make code changes to the orchestration itself.</span></span>  
  
3.  <span data-ttu-id="0bc49-112">更改程序集的版本号：</span><span class="sxs-lookup"><span data-stu-id="0bc49-112">Change the version number of the assembly:</span></span>  
  
    1.  <span data-ttu-id="0bc49-113">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0bc49-113">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="0bc49-114">在中**项目设计器**，单击**应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0bc49-114">In the **Project Designer**, click the **Application** tab.</span></span>  
  
    3.  <span data-ttu-id="0bc49-115">在右窗格中，单击**程序集信息**。</span><span class="sxs-lookup"><span data-stu-id="0bc49-115">In the right pane, click **Assembly Information**.</span></span>  
  
    4.  <span data-ttu-id="0bc49-116">在中**程序集信息**对话框框中，为指定值**程序集版本**字段以更改程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="0bc49-116">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to change the assembly version number.</span></span> <span data-ttu-id="0bc49-117">应更改仅主要或次要版本号。</span><span class="sxs-lookup"><span data-stu-id="0bc49-117">You should change only the major or minor version number.</span></span> <span data-ttu-id="0bc49-118">主版本号是序列中的第一个数字 (***n***.0.0.0); 次版本号是序列中的第二个数字 (0。***n***.0.0)。</span><span class="sxs-lookup"><span data-stu-id="0bc49-118">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span>  
  
    5.  <span data-ttu-id="0bc49-119">单击**确定**以关闭**程序集信息**对话框。</span><span class="sxs-lookup"><span data-stu-id="0bc49-119">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
4.  <span data-ttu-id="0bc49-120">编译该程序集。</span><span class="sxs-lookup"><span data-stu-id="0bc49-120">Compile the assembly.</span></span>  
  
5.  <span data-ttu-id="0bc49-121">将程序集部署到组 （以及所有计算机）。</span><span class="sxs-lookup"><span data-stu-id="0bc49-121">Deploy the assembly to the group (and all computers).</span></span>  
  
## <a name="modifying-a-map-to-reflect-updated-version-numbers"></a><span data-ttu-id="0bc49-122">修改映射以反映更新的版本号</span><span class="sxs-lookup"><span data-stu-id="0bc49-122">Modifying a Map to Reflect Updated Version Numbers</span></span>  
 <span data-ttu-id="0bc49-123">.NET 程序集可以从调用在映射内使用脚本 functoid。</span><span class="sxs-lookup"><span data-stu-id="0bc49-123">.NET assemblies can be invoked from within a map by using the Scripting functoid.</span></span> <span data-ttu-id="0bc49-124">这提供了大量的灵活性，并使开发者能够解决很多不同的自定义映射问题。</span><span class="sxs-lookup"><span data-stu-id="0bc49-124">This provides a great deal of flexibility and enables the developer to solve many different custom mapping problems.</span></span> <span data-ttu-id="0bc49-125">它还规定了在地图上的唯一约束，它必须在内部引用程序集类型名称不仅还正在调用的完整的程序集版本号。</span><span class="sxs-lookup"><span data-stu-id="0bc49-125">It also imposes a unique constraint on the map—it must internally reference not only the assembly type name but also the full assembly version number being invoked.</span></span> <span data-ttu-id="0bc49-126">因此，如果更改了映射所调用的程序集的版本号，所有引用程序集的链接将中断。</span><span class="sxs-lookup"><span data-stu-id="0bc49-126">As a consequence, if the version number of the assembly called by the map changes, all of the links that reference the assembly will break.</span></span>  
  
 <span data-ttu-id="0bc49-127">若要避免此问题，我们建议，如果需要从映射调用程序集，特定的程序集创建来保存仅映射功能，并且固定此程序集的程序集版本号。</span><span class="sxs-lookup"><span data-stu-id="0bc49-127">To avoid this issue we recommend that if assemblies are required to be called from a map, a specific assembly is created to hold only map functionality and that the assembly version number of this assembly is fixed.</span></span> <span data-ttu-id="0bc49-128">这样一来，其他帮助器函数可以更新而无需中断映射的程序集版本。</span><span class="sxs-lookup"><span data-stu-id="0bc49-128">In this way, other helper functions can have the assembly version updated without breaking the maps.</span></span>  
  
 <span data-ttu-id="0bc49-129">如果通过该映射引用的程序集更改映射开发完成后请考虑更新以反映已更新的版本号在映射编辑器外映射文件。</span><span class="sxs-lookup"><span data-stu-id="0bc49-129">If an assembly referenced from a map is changed after map development then consider updating the map file outside of the Map Editor to reflect the updated version numbers.</span></span>  
  
#### <a name="to-modify-a-map-file-to-reflect-updated-version-numbers"></a><span data-ttu-id="0bc49-130">若要修改的映射文件以反映已更新的版本号</span><span class="sxs-lookup"><span data-stu-id="0bc49-130">To modify a map file to reflect updated version numbers</span></span>  
  
1.  <span data-ttu-id="0bc49-131">使用**启动**菜单中，打开**记事本**。</span><span class="sxs-lookup"><span data-stu-id="0bc49-131">Using the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="0bc49-132">在中**记事本**，然后在**文件**菜单中，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0bc49-132">In **Notepad**, on the **File** menu, click **Open**.</span></span> <span data-ttu-id="0bc49-133">在中**开放**对话框中，选择该映射文件您想要修改，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0bc49-133">In the **Open** dialog box, select the map file you want to modify, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="0bc49-134">在 **“编辑”** 菜单中，单击 **“查找”**。</span><span class="sxs-lookup"><span data-stu-id="0bc49-134">On the **Edit** menu, click **Find**.</span></span> <span data-ttu-id="0bc49-135">在中**查找**对话框框中，输入**程序集 =**，然后单击**查找下一个**。</span><span class="sxs-lookup"><span data-stu-id="0bc49-135">In the **Find** dialog box, enter **Assembly=**, and then click **Find Next**.</span></span>  
  
4.  <span data-ttu-id="0bc49-136">如果没有对外部程序集的脚本引用，记事本应该找到如下所示的 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="0bc49-136">If there is a script reference to an external assembly, Notepad should find an XML element like the following:</span></span>  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=  
    <token>  
    " Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
5.  <span data-ttu-id="0bc49-137">更新的版本号。</span><span class="sxs-lookup"><span data-stu-id="0bc49-137">Update the version number.</span></span> <span data-ttu-id="0bc49-138">如果有多个实例，使用**替换为**上**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="0bc49-138">If there are multiple instances, use **Replace** on the **Edit** menu.</span></span>  
  
6.  <span data-ttu-id="0bc49-139">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="0bc49-139">Save the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0bc49-140">现在可以打开用映射编辑器的映射。</span><span class="sxs-lookup"><span data-stu-id="0bc49-140">You can now open the map using the Map Editor.</span></span>