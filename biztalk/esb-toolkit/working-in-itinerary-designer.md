---
title: 使用路线设计器 |Microsoft Docs
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
ms.openlocfilehash: 747ce8a750f2b2c775deaa1123a1b6b1d387eafc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999398"
---
# <a name="working-in-itinerary-designer"></a><span data-ttu-id="f6eee-102">在路线设计器中工作</span><span class="sxs-lookup"><span data-stu-id="f6eee-102">Working in Itinerary Designer</span></span>
<span data-ttu-id="f6eee-103">创建 Microsoft Visual C# 项目后，可以创建新的路线模型并将现有路线添加到项目。</span><span class="sxs-lookup"><span data-stu-id="f6eee-103">After you create a Microsoft Visual C# project, you can create new itinerary models and add existing itineraries to the project.</span></span> <span data-ttu-id="f6eee-104">以下步骤介绍如何创建新的旅行计划中，添加一个现有的路线模型，或更改路线的名称。</span><span class="sxs-lookup"><span data-stu-id="f6eee-104">The following steps describe how to create a new itinerary, add an existing itinerary model, or change the name of an itinerary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6eee-105">使用路线设计器之前, 必须安装 Microsoft.Practices.ESB.CORE Windows Installer （.msi 文件） 从[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="f6eee-105">Before working with the Itinerary Designer, you must install the Microsoft.Practices.ESB.CORE Windows Installer (.msi file) from the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] install folder.</span></span> <span data-ttu-id="f6eee-106">此步骤中将所需的运行时程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="f6eee-106">This step installs the required run-time assemblies to the global assembly cache.</span></span>  
  
## <a name="basic-operations"></a><span data-ttu-id="f6eee-107">基本操作</span><span class="sxs-lookup"><span data-stu-id="f6eee-107">Basic Operations</span></span>  

#### <a name="create-an-itinerary"></a><span data-ttu-id="f6eee-108">创建路线</span><span class="sxs-lookup"><span data-stu-id="f6eee-108">Create an itinerary</span></span>  
  
1.  <span data-ttu-id="f6eee-109">在解决方案资源管理器中右键单击 C# 项目名称，指向**外**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-109">In Solution Explorer, right-click the C# project name, point to **Add**, and then click **New Itinerary**.</span></span>  
  
2.  <span data-ttu-id="f6eee-110">在中**名称**框底部的对话框中，键入路线的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-110">In the **Name** box at the bottom of the dialog box, type the name for the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6eee-111">创建新的路线并将其显示在路线设计器中，并创建相应的.itinerary 文件并将其显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="f6eee-111">The new itinerary is created and displayed in Itinerary Designer, and a corresponding .itinerary file is created and displayed in Solution Explorer.</span></span>  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a><span data-ttu-id="f6eee-112">向项目添加现有路线</span><span class="sxs-lookup"><span data-stu-id="f6eee-112">Add an existing itinerary to the project</span></span>
  
1.  <span data-ttu-id="f6eee-113">在解决方案资源管理器，右键单击 C# 项目名称，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-113">In Solution explorer, right click the C# project name, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="f6eee-114">在中**添加现有项**对话框中，导航到包含路线，单击目录路线，然后依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-114">In the **Add Existing Item** dialog box, navigate to the directory that contains the itinerary, click the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6eee-115">路线添加到项目。</span><span class="sxs-lookup"><span data-stu-id="f6eee-115">The itinerary is added to the project.</span></span>  
  
#### <a name="change-the-name-of-an-itinerary"></a><span data-ttu-id="f6eee-116">更改路线的名称</span><span class="sxs-lookup"><span data-stu-id="f6eee-116">Change the name of an itinerary</span></span>  
  
1.  <span data-ttu-id="f6eee-117">在解决方案资源管理器，右键单击你想要重命名，然后单击.itinerary 文件**重命名**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-117">In Solution Explorer, right-click the .itinerary file you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="f6eee-118">键入新文件名，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="f6eee-118">Type the new file name, and then press ENTER.</span></span>  
  
#### <a name="save-an-itinerary"></a><span data-ttu-id="f6eee-119">保存路线</span><span class="sxs-lookup"><span data-stu-id="f6eee-119">Save an itinerary</span></span>  
  
<span data-ttu-id="f6eee-120">上**文件**菜单上，单击**保存\<路线名称\>**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-120">On the **File** menu, click **Save \<itinerary name\>**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6eee-121">路线文件保存为 DSL 模型中相应的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="f6eee-121">Itinerary files are saved as DSL models in corresponding XML format.</span></span>  
  
#### <a name="set-itinerary-export-properties"></a><span data-ttu-id="f6eee-122">设置路线导出属性</span><span class="sxs-lookup"><span data-stu-id="f6eee-122">Set itinerary export properties</span></span>  
  
1. <span data-ttu-id="f6eee-123">在属性窗口中，键入**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="f6eee-123">In the Properties window, type a **Name** property.</span></span>  
  
2. <span data-ttu-id="f6eee-124">在属性窗口中，键入**版本**属性。</span><span class="sxs-lookup"><span data-stu-id="f6eee-124">In the Properties window, type a **Version** property.</span></span>  
  
3. <span data-ttu-id="f6eee-125">在属性窗口中，指定**是请求响应**使用下拉列表的属性。</span><span class="sxs-lookup"><span data-stu-id="f6eee-125">In the Properties window, specify the **Is Request Response** property using the drop-down list.</span></span> <span data-ttu-id="f6eee-126">将此属性设置为 **，则返回 true**如果[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]客户端应用程序的途径与通信使用请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="f6eee-126">Set this property to **true** if the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] client application communicates with an on-ramp using request-response message exchange pattern.</span></span>  
  
4. <span data-ttu-id="f6eee-127">在属性窗口中设置**导出模式**属性设置为**默认**或**Strict**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-127">In the Properties window, set the **Export Mode** property to **Default** or **Strict**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f6eee-128">创建时[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用路线设计器的路线**导出模式**属性可以用于定义该服务将执行的位置。</span><span class="sxs-lookup"><span data-stu-id="f6eee-128">When creating [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries using the Itinerary Designer, the **Export Mode** property can be used to define where the service will execute.</span></span> <span data-ttu-id="f6eee-129">设置**导出模式**属性设置为**Strict**路线可确保服务在其规定的容器执行; 在这种情况下，XML 路线中的每个路线服务都有阶段属性，指定执行该服务的管道。</span><span class="sxs-lookup"><span data-stu-id="f6eee-129">Setting the **Export Mode** property to **Strict** ensures that the itinerary service executes in its prescribed container; in this case, each itinerary service in the XML itinerary has a stage property that specifies the pipeline in which the service executes.</span></span> <span data-ttu-id="f6eee-130">如果此属性设置为**默认**、 创建符合 Microsoft ESB 路线时，指定，任何阶段和顺序规定，但不是一定是所需的管道阶段中执行该路线服务。</span><span class="sxs-lookup"><span data-stu-id="f6eee-130">If this property is set to **Default**, an itinerary compatible with Microsoft ESB is created, with no stage specified, and the itinerary service executes in the order prescribed, but not necessarily in the pipeline stage desired.</span></span>  
  
#### <a name="export-an-itinerary-to-a-file"></a><span data-ttu-id="f6eee-131">导出到文件的路线</span><span class="sxs-lookup"><span data-stu-id="f6eee-131">Export an itinerary to a file</span></span>  
  
1.  <span data-ttu-id="f6eee-132">在属性窗口中，单击**XML 路线导出程序**中**模型导出程序**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f6eee-132">In the Properties window, click **XML Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="f6eee-133">在属性窗口中设置**路线 XML 文件**属性的新值。</span><span class="sxs-lookup"><span data-stu-id="f6eee-133">In the Properties window, set the **Itinerary XML file** property to a new value.</span></span>  
  
#### <a name="export-an-itinerary-to-a-database"></a><span data-ttu-id="f6eee-134">导出到数据库的路线</span><span class="sxs-lookup"><span data-stu-id="f6eee-134">Export an itinerary to a database</span></span>  
  
1. <span data-ttu-id="f6eee-135">在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f6eee-135">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2. <span data-ttu-id="f6eee-136">在属性窗口中设置**行程数据库**属性以指向路线的数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="f6eee-136">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
3. <span data-ttu-id="f6eee-137">在属性窗口中设置**路线状态**属性设置为**已发布**或**已部署**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-137">In the Properties window, set the **Itinerary Status** property to **Published** or **Deployed**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f6eee-138">路线拥有的数据库的导出时**路线状态**设置为**已发布**，则不会生效的路线将[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]后的属性设置为运行之前的时间**部署**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-138">When an itinerary is exported to a database with **Itinerary Status** set to **Published**, the itinerary will not become effective for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run time until after the property is set to **Deployed**.</span></span>  
  
## <a name="security-operations"></a><span data-ttu-id="f6eee-139">安全操作</span><span class="sxs-lookup"><span data-stu-id="f6eee-139">Security Operations</span></span>  
 <span data-ttu-id="f6eee-140">使用路线设计器，你可以保护敏感信息，如密码和其他凭据存储在[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线，此使用 X.509 证书的信息进行加密。</span><span class="sxs-lookup"><span data-stu-id="f6eee-140">By using the Itinerary Designer, you can protect sensitive information, such as passwords and other credentials stored in a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary, by encrypting this information using X.509 certificates.</span></span>  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a><span data-ttu-id="f6eee-141">选择一条路线的 X.509 证书</span><span class="sxs-lookup"><span data-stu-id="f6eee-141">Select the X.509 certificate for an itinerary</span></span>  
  
1.  <span data-ttu-id="f6eee-142">在路线设计器属性窗口中，展开**加密证书**属性，，然后单击**存储区位置**下拉列表，然后选择**CurrentUser**或**LocalMachine**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-142">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then click the **Store Location** drop-down list, and select the **CurrentUser** or **LocalMachine**.</span></span> <span data-ttu-id="f6eee-143">这将与当前用户或本地计算机关联的 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="f6eee-143">This associates the X.509 certificate store with the current user or the local computer.</span></span>  
  
2.  <span data-ttu-id="f6eee-144">在属性窗口中，单击**存储名称**下拉列表，然后选择对应于你的证书存储的值。</span><span class="sxs-lookup"><span data-stu-id="f6eee-144">In the Properties window, click the **Store Name** drop-down list and select the value which corresponds to your certificate store.</span></span>  
  
3.  <span data-ttu-id="f6eee-145">在属性窗口中单击加密证书属性旁边的省略号按钮 （...），然后选择**X.509 证书**中**选择证书**对话框。</span><span class="sxs-lookup"><span data-stu-id="f6eee-145">In the Properties window, click the ellipsis button (...) next to the Encryption Certificate property, and then select the **X.509 certificate** in the **Select Certificate** dialog box.</span></span>  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a><span data-ttu-id="f6eee-146">从路线中删除的 X.509 证书</span><span class="sxs-lookup"><span data-stu-id="f6eee-146">Remove the X.509 certificate from an itinerary</span></span>  
  
- <span data-ttu-id="f6eee-147">在路线设计器属性窗口中，展开**加密证书**属性，且然后将设置**存储区位置**属性设置为不同的值。</span><span class="sxs-lookup"><span data-stu-id="f6eee-147">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then set the **Store Location** property to a different value.</span></span> <span data-ttu-id="f6eee-148">此取消关联的旧证书[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线模型。</span><span class="sxs-lookup"><span data-stu-id="f6eee-148">This disassociates the old certificate with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary model.</span></span>  
  
#### <a name="disable-the-x509-certificate-validation"></a><span data-ttu-id="f6eee-149">禁用 X.509 证书验证</span><span class="sxs-lookup"><span data-stu-id="f6eee-149">Disable the X.509 certificate validation</span></span>  
  
<span data-ttu-id="f6eee-150">在注册表编辑器中，转到子项**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**，然后设置**RequireX509Certificate**属性值设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-150">In the Registry Editor, go to the subkey **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**, and then set the **RequireX509Certificate** property value to **false**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6eee-151">如果您安装了[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]子项是具有 64 位支持的操作系统，在**HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**。</span><span class="sxs-lookup"><span data-stu-id="f6eee-151">If you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] on an operating system that has 64-bit support, the subkey is **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**.</span></span>