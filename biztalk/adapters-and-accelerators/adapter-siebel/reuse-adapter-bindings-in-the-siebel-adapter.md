---
title: 重用适配器绑定在 Siebel 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding file, definition
- adapter bindings, reusing
ms.assetid: 1dc17b7a-5397-43f4-b19e-9c50fb0e97ff
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bff4d1f4566f758b7cc6d1d37efcb30f651d9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222749"
---
# <a name="reuse-adapter-bindings-in-the-siebel-adapter"></a><span data-ttu-id="f4966-102">重用适配器绑定在 Siebel 适配器中</span><span class="sxs-lookup"><span data-stu-id="f4966-102">Reuse adapter bindings in the Siebel adapter</span></span>
<span data-ttu-id="f4966-103">绑定可以在逻辑终结点（如业务流程端口或角色链接）与物理终结点（如发送/接收端口或参与方）之间创建映射。</span><span class="sxs-lookup"><span data-stu-id="f4966-103">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="f4966-104">这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="f4966-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="f4966-105">使用 BizTalk Server 管理控制台可以创建绑定。</span><span class="sxs-lookup"><span data-stu-id="f4966-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="f4966-106">什么是绑定文件？</span><span class="sxs-lookup"><span data-stu-id="f4966-106">What is a binding file?</span></span>  
<span data-ttu-id="f4966-107">绑定文件是一个包含每个 BizTalk 业务流程的作用域中的 BizTalk 程序集、 应用程序或组的绑定信息的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f4966-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="f4966-108">绑定文件描述：</span><span class="sxs-lookup"><span data-stu-id="f4966-108">The binding file describes:</span></span>  
  
-   <span data-ttu-id="f4966-109">每个业务流程绑定到主机</span><span class="sxs-lookup"><span data-stu-id="f4966-109">The host to which each orchestration is bound</span></span>
  
-   <span data-ttu-id="f4966-110">主机的信任级别</span><span class="sxs-lookup"><span data-stu-id="f4966-110">The trust level of the host</span></span>
  
-   <span data-ttu-id="f4966-111">每个设置发送端口、 接收端口、 接收方已配置和位置，</span><span class="sxs-lookup"><span data-stu-id="f4966-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
 <span data-ttu-id="f4966-112">你可以生成绑定文件，并将它们包含的绑定应用于一个程序集，应用程序或组。</span><span class="sxs-lookup"><span data-stu-id="f4966-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="f4966-113">这样可以防止无需在不同的部署环境中手动配置绑定，加快应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="f4966-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
 <span data-ttu-id="f4966-114">BizTalk 程序集，应用程序，或组不自动生成一个绑定文件。</span><span class="sxs-lookup"><span data-stu-id="f4966-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="f4966-115">但是，你可以通过导出绑定生成绑定文件。</span><span class="sxs-lookup"><span data-stu-id="f4966-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="f4966-116">你然后可以绑定文件导入的应用程序或组中。</span><span class="sxs-lookup"><span data-stu-id="f4966-116">You can then import the binding file into an application or group.</span></span>  
  
 <span data-ttu-id="f4966-117">有关绑定和绑定文件有关的详细信息，请参阅[绑定文件和应用程序部署](../../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="f4966-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>
 
 > [!NOTE]
 >  <span data-ttu-id="f4966-118">BizTalk 程序集，应用程序，或组不自动生成一个绑定文件。</span><span class="sxs-lookup"><span data-stu-id="f4966-118">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="f4966-119">但是，你可以通过导出绑定生成绑定文件。</span><span class="sxs-lookup"><span data-stu-id="f4966-119">But you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="f4966-120">你然后可以绑定文件导入的应用程序或组中。</span><span class="sxs-lookup"><span data-stu-id="f4966-120">You can then import the binding file into an application or group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4966-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="f4966-121">Prerequisites</span></span>  
<span data-ttu-id="f4966-122">是的成员的帐户登录第 i 个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="f4966-122">Sign in ith an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="f4966-123">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f4966-123">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>

 
## <a name="export-bindings"></a><span data-ttu-id="f4966-124">导出绑定</span><span class="sxs-lookup"><span data-stu-id="f4966-124">Export bindings</span></span>
<span data-ttu-id="f4966-125">本部分介绍如何导出到 XML 文件的 BizTalk 应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="f4966-125">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="f4966-126">您然后可以从 XML 文件到另一个 BizTalk 应用程序来导入绑定。</span><span class="sxs-lookup"><span data-stu-id="f4966-126">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="f4966-127">导入绑定将覆盖任何现有的应用程序中相同的名称绑定。</span><span class="sxs-lookup"><span data-stu-id="f4966-127">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="f4966-128">你还可以向应用程序，不会覆盖现有绑定添加绑定。</span><span class="sxs-lookup"><span data-stu-id="f4966-128">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="f4966-129">在导入应用程序之前，你添加的绑定不会生效。</span><span class="sxs-lookup"><span data-stu-id="f4966-129">The bindings that you add do not take effect until you import the application.</span></span>  
  
1.  <span data-ttu-id="f4966-130">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f4966-130">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f4966-131">展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f4966-131">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="f4966-132">右键单击你想要导出，其的绑定选择的应用**导出**，然后选择**绑定**。</span><span class="sxs-lookup"><span data-stu-id="f4966-132">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="f4966-133">上**导出绑定**页上，在**导出到文件**，键入要导出绑定到 XML 文件的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="f4966-133">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="f4966-134">例如，输入`C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="f4966-134">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5.  <span data-ttu-id="f4966-135">确认**导出当前应用程序中的所有绑定**选择。</span><span class="sxs-lookup"><span data-stu-id="f4966-135">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6.  <span data-ttu-id="f4966-136">若要导出的组的所有方信息，请选择**都导出全局方信息**复选框。</span><span class="sxs-lookup"><span data-stu-id="f4966-136">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7.  <span data-ttu-id="f4966-137">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="f4966-137">Select **OK**.</span></span> <span data-ttu-id="f4966-138">绑定将导出到 XML 文件中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="f4966-138">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="f4966-139">导入的绑定</span><span class="sxs-lookup"><span data-stu-id="f4966-139">Import bindings</span></span>
<span data-ttu-id="f4966-140">导入使用 BizTalk Server 管理控制台的绑定。</span><span class="sxs-lookup"><span data-stu-id="f4966-140">Import bindings using the BizTalk Server Administration console.</span></span>
  
1.  <span data-ttu-id="f4966-141">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f4966-141">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f4966-142">展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f4966-142">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="f4966-143">右键单击你要向其中导入的绑定中，选择应用的程序**导入**，然后选择**绑定**。</span><span class="sxs-lookup"><span data-stu-id="f4966-143">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="f4966-144">选择绑定文件，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="f4966-144">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="f4966-145">绑定文件中的项目将写入该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="f4966-145">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="f4966-146">这些项目显示在该应用程序的相应文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f4966-146">They display in appropriate folders of the application.</span></span> <span data-ttu-id="f4966-147">例如，发送端口导入的绑定显示在下一部分**发送端口**文件夹。</span><span class="sxs-lookup"><span data-stu-id="f4966-147">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="f4966-148">不会保留密码</span><span class="sxs-lookup"><span data-stu-id="f4966-148">Passwords are removed</span></span>  
<span data-ttu-id="f4966-149">出于安全原因，当导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="f4966-149">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="f4966-150">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="f4966-150">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="f4966-151">传输属性对话框中配置密码[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台为发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="f4966-151">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="f4966-152">有关指定用户名和密码的信息，请参阅[配置登录凭据用于 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="f4966-152">For information about specifying user name and passwords, see [Configure the sign in credentials for the Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4966-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4966-153">See also</span></span>
[<span data-ttu-id="f4966-154">构建基块创建带有 Siebel 适配器 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="f4966-154">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)