---
title: 在路线设计器中工作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06742cb8-f6d6-46e2-adc0-6be9a3d6a447
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf474c68d91b7648f7f0efcfe4e85e7531e4aa1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976779"
---
# <a name="working-in-itinerary-designer"></a><span data-ttu-id="ac5af-102">在路线设计器中工作</span><span class="sxs-lookup"><span data-stu-id="ac5af-102">Working in Itinerary Designer</span></span>
<span data-ttu-id="ac5af-103">创建一个 Microsoft Visual C# 项目后，可以创建新的路线模型，并将现有路线添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ac5af-103">After you create a Microsoft Visual C# project, you can create new itinerary models and add existing itineraries to the project.</span></span> <span data-ttu-id="ac5af-104">以下步骤介绍如何创建新路线、 添加现有路线模型，或更改一条路线的名称。</span><span class="sxs-lookup"><span data-stu-id="ac5af-104">The following steps describe how to create a new itinerary, add an existing itinerary model, or change the name of an itinerary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac5af-105">在使用路线设计器之前, 中，你必须安装 Microsoft.Practices.ESB.CORE Windows Installer （.msi 文件） 从[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="ac5af-105">Before working with the Itinerary Designer, you must install the Microsoft.Practices.ESB.CORE Windows Installer (.msi file) from the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] install folder.</span></span> <span data-ttu-id="ac5af-106">此步骤将所需的运行时程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="ac5af-106">This step installs the required run-time assemblies to the global assembly cache.</span></span>  
  
## <a name="basic-operations"></a><span data-ttu-id="ac5af-107">基本操作</span><span class="sxs-lookup"><span data-stu-id="ac5af-107">Basic Operations</span></span>  

#### <a name="create-an-itinerary"></a><span data-ttu-id="ac5af-108">创建一条路线</span><span class="sxs-lookup"><span data-stu-id="ac5af-108">Create an itinerary</span></span>  
  
1.  <span data-ttu-id="ac5af-109">在解决方案资源管理器，右键单击 C# 项目名称，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-109">In Solution Explorer, right-click the C# project name, point to **Add**, and then click **New Itinerary**.</span></span>  
  
2.  <span data-ttu-id="ac5af-110">在**名称**底部的对话框框中，键入路线的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-110">In the **Name** box at the bottom of the dialog box, type the name for the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac5af-111">创建新的路线并将其显示在路线设计器中，并创建相应的.itinerary 文件并将其显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="ac5af-111">The new itinerary is created and displayed in Itinerary Designer, and a corresponding .itinerary file is created and displayed in Solution Explorer.</span></span>  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a><span data-ttu-id="ac5af-112">将现有路线添加到项目</span><span class="sxs-lookup"><span data-stu-id="ac5af-112">Add an existing itinerary to the project</span></span>
  
1.  <span data-ttu-id="ac5af-113">在解决方案资源管理器，右键单击 C# 项目名称，指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-113">In Solution explorer, right click the C# project name, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="ac5af-114">在**添加现有项**对话框中，导航到的目录中包含路线，单击路线，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-114">In the **Add Existing Item** dialog box, navigate to the directory that contains the itinerary, click the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac5af-115">路线添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ac5af-115">The itinerary is added to the project.</span></span>  
  
#### <a name="change-the-name-of-an-itinerary"></a><span data-ttu-id="ac5af-116">更改一条路线的名称</span><span class="sxs-lookup"><span data-stu-id="ac5af-116">Change the name of an itinerary</span></span>  
  
1.  <span data-ttu-id="ac5af-117">在解决方案资源管理器，右键单击你想要重命名，然后单击.itinerary 文件**重命名**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-117">In Solution Explorer, right-click the .itinerary file you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="ac5af-118">键入新的文件名称，，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="ac5af-118">Type the new file name, and then press ENTER.</span></span>  
  
#### <a name="save-an-itinerary"></a><span data-ttu-id="ac5af-119">保存一条路线</span><span class="sxs-lookup"><span data-stu-id="ac5af-119">Save an itinerary</span></span>  
  
<span data-ttu-id="ac5af-120">上**文件**菜单上，单击**保存\<路线名称\>**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-120">On the **File** menu, click **Save \<itinerary name\>**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac5af-121">路线文件将保存为相应的 XML 格式的 DSL 模型。</span><span class="sxs-lookup"><span data-stu-id="ac5af-121">Itinerary files are saved as DSL models in corresponding XML format.</span></span>  
  
#### <a name="set-itinerary-export-properties"></a><span data-ttu-id="ac5af-122">设置路线导出属性</span><span class="sxs-lookup"><span data-stu-id="ac5af-122">Set itinerary export properties</span></span>  
  
1.  <span data-ttu-id="ac5af-123">在属性窗口中，键入**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="ac5af-123">In the Properties window, type a **Name** property.</span></span>  
  
2.  <span data-ttu-id="ac5af-124">在属性窗口中，键入**版本**属性。</span><span class="sxs-lookup"><span data-stu-id="ac5af-124">In the Properties window, type a **Version** property.</span></span>  
  
3.  <span data-ttu-id="ac5af-125">在属性窗口中，指定**是请求响应**使用下拉列表的属性。</span><span class="sxs-lookup"><span data-stu-id="ac5af-125">In the Properties window, specify the **Is Request Response** property using the drop-down list.</span></span> <span data-ttu-id="ac5af-126">将此属性设置为**true**如果[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]客户端应用程序与入口通信使用请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="ac5af-126">Set this property to **true** if the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] client application communicates with an on-ramp using request-response message exchange pattern.</span></span>  
  
4.  <span data-ttu-id="ac5af-127">在属性窗口中，设置**导出模式**属性**默认**或**Strict**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-127">In the Properties window, set the **Export Mode** property to **Default** or **Strict**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac5af-128">在创建时[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线使用路线设计器中，**导出模式**属性可以用于定义该服务将在其中执行。</span><span class="sxs-lookup"><span data-stu-id="ac5af-128">When creating [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries using the Itinerary Designer, the **Export Mode** property can be used to define where the service will execute.</span></span> <span data-ttu-id="ac5af-129">设置**导出模式**属性**Strict**路线可确保服务在其规定的容器执行; 在这种情况下，XML 行程中的每个路线服务具有阶段属性，指定服务在其中执行的管道。</span><span class="sxs-lookup"><span data-stu-id="ac5af-129">Setting the **Export Mode** property to **Strict** ensures that the itinerary service executes in its prescribed container; in this case, each itinerary service in the XML itinerary has a stage property that specifies the pipeline in which the service executes.</span></span> <span data-ttu-id="ac5af-130">如果此属性设置为**默认**、 创建与 Microsoft ESB 兼容路线后，指定，没有阶段和路线服务执行顺序规定，但不是一定是所需的管道阶段。</span><span class="sxs-lookup"><span data-stu-id="ac5af-130">If this property is set to **Default**, an itinerary compatible with Microsoft ESB is created, with no stage specified, and the itinerary service executes in the order prescribed, but not necessarily in the pipeline stage desired.</span></span>  
  
#### <a name="export-an-itinerary-to-a-file"></a><span data-ttu-id="ac5af-131">将一条路线导出到文件</span><span class="sxs-lookup"><span data-stu-id="ac5af-131">Export an itinerary to a file</span></span>  
  
1.  <span data-ttu-id="ac5af-132">在属性窗口中，单击**XML 路线导出程序**中**模型导出程序**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ac5af-132">In the Properties window, click **XML Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="ac5af-133">在属性窗口中，设置**路线 XML 文件**属性的新值。</span><span class="sxs-lookup"><span data-stu-id="ac5af-133">In the Properties window, set the **Itinerary XML file** property to a new value.</span></span>  
  
#### <a name="export-an-itinerary-to-a-database"></a><span data-ttu-id="ac5af-134">将一条路线导出到数据库</span><span class="sxs-lookup"><span data-stu-id="ac5af-134">Export an itinerary to a database</span></span>  
  
1.  <span data-ttu-id="ac5af-135">在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ac5af-135">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="ac5af-136">在属性窗口中，设置**路线数据库**属性连接字符串以指向路线的数据库。</span><span class="sxs-lookup"><span data-stu-id="ac5af-136">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
3.  <span data-ttu-id="ac5af-137">在属性窗口中，设置**路线状态**属性**已发布**或**已部署**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-137">In the Properties window, set the **Itinerary Status** property to **Published** or **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac5af-138">当一条路线导出的数据库具有**路线状态**设置为**已发布**、 不生效的路线将[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]后的属性设置为运行花时间**部署**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-138">When an itinerary is exported to a database with **Itinerary Status** set to **Published**, the itinerary will not become effective for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run time until after the property is set to **Deployed**.</span></span>  
  
## <a name="security-operations"></a><span data-ttu-id="ac5af-139">安全操作</span><span class="sxs-lookup"><span data-stu-id="ac5af-139">Security Operations</span></span>  
 <span data-ttu-id="ac5af-140">通过使用路线设计器，你可以保护敏感信息，如密码和其他凭据存储在[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线，使用 X.509 证书的此信息进行加密。</span><span class="sxs-lookup"><span data-stu-id="ac5af-140">By using the Itinerary Designer, you can protect sensitive information, such as passwords and other credentials stored in a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary, by encrypting this information using X.509 certificates.</span></span>  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a><span data-ttu-id="ac5af-141">选择一条路线的 X.509 证书</span><span class="sxs-lookup"><span data-stu-id="ac5af-141">Select the X.509 certificate for an itinerary</span></span>  
  
1.  <span data-ttu-id="ac5af-142">在路线设计器属性窗口中，展开**加密证书**属性，，然后单击**存储位置**下拉列表，然后选择**CurrentUser**或**LocalMachine**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-142">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then click the **Store Location** drop-down list, and select the **CurrentUser** or **LocalMachine**.</span></span> <span data-ttu-id="ac5af-143">这将与当前用户或本地计算机关联的 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ac5af-143">This associates the X.509 certificate store with the current user or the local computer.</span></span>  
  
2.  <span data-ttu-id="ac5af-144">在属性窗口中，单击**存储名称**下拉列表，然后选择对应于你的证书存储的值。</span><span class="sxs-lookup"><span data-stu-id="ac5af-144">In the Properties window, click the **Store Name** drop-down list and select the value which corresponds to your certificate store.</span></span>  
  
3.  <span data-ttu-id="ac5af-145">在属性窗口中，单击加密证书属性旁边的省略号按钮 （…），然后选择**X.509 证书**中**选择证书**对话框。</span><span class="sxs-lookup"><span data-stu-id="ac5af-145">In the Properties window, click the ellipsis button (...) next to the Encryption Certificate property, and then select the **X.509 certificate** in the **Select Certificate** dialog box.</span></span>  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a><span data-ttu-id="ac5af-146">删除一条路线的 X.509 证书</span><span class="sxs-lookup"><span data-stu-id="ac5af-146">Remove the X.509 certificate from an itinerary</span></span>  
  
-   <span data-ttu-id="ac5af-147">在路线设计器属性窗口中，展开**加密证书**属性，且然后将其设置**存储位置**为不同的值的属性。</span><span class="sxs-lookup"><span data-stu-id="ac5af-147">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then set the **Store Location** property to a different value.</span></span> <span data-ttu-id="ac5af-148">这解除关联的旧证书[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线模型。</span><span class="sxs-lookup"><span data-stu-id="ac5af-148">This disassociates the old certificate with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary model.</span></span>  
  
#### <a name="disable-the-x509-certificate-validation"></a><span data-ttu-id="ac5af-149">禁用 X.509 证书验证</span><span class="sxs-lookup"><span data-stu-id="ac5af-149">Disable the X.509 certificate validation</span></span>  
  
<span data-ttu-id="ac5af-150">在注册表编辑器中，转到子项**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**，然后设置**RequireX509Certificate**属性值设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-150">In the Registry Editor, go to the subkey **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**, and then set the **RequireX509Certificate** property value to **false**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac5af-151">如果你安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]子项是 64 位支持的操作系统上, **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**。</span><span class="sxs-lookup"><span data-stu-id="ac5af-151">If you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] on an operating system that has 64-bit support, the subkey is **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**.</span></span>