---
title: 重复使用 SAP 适配器绑定 |Microsoft Docs
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
ms.assetid: 5748c22f-20a2-4eb9-ad45-a1bef7290802
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32fa550d51067cae20451651674ad57144acce02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373005"
---
# <a name="reuse-sap-adapter-bindings"></a><span data-ttu-id="ff5a0-102">重复使用 SAP 适配器绑定</span><span class="sxs-lookup"><span data-stu-id="ff5a0-102">Reuse SAP adapter bindings</span></span>
<span data-ttu-id="ff5a0-103">绑定创建一个逻辑终结点 （例如业务流程端口或角色链接） 和物理终结点之间的映射 (如发送和接收端口)。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="ff5a0-104">这样，BizTalk 业务解决方案的不同组件之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="ff5a0-105">可以使用 BizTalk Server 管理控制台来创建绑定。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="ff5a0-106">什么是绑定文件？</span><span class="sxs-lookup"><span data-stu-id="ff5a0-106">What is a Binding File?</span></span>  
 <span data-ttu-id="ff5a0-107">绑定文件是一个包含作用域中每个 BizTalk 业务流程的 BizTalk 程序集、 应用程序或组的绑定信息的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="ff5a0-108">绑定文件描述：</span><span class="sxs-lookup"><span data-stu-id="ff5a0-108">The binding file describes:</span></span>  
  
- <span data-ttu-id="ff5a0-109">每个业务流程绑定到主机</span><span class="sxs-lookup"><span data-stu-id="ff5a0-109">The host to which each orchestration is bound</span></span>
  
- <span data-ttu-id="ff5a0-110">主机的信任级别</span><span class="sxs-lookup"><span data-stu-id="ff5a0-110">The trust level of the host</span></span>
  
- <span data-ttu-id="ff5a0-111">每个设置发送端口、 接收端口、 接收位置，且已配置的参与方</span><span class="sxs-lookup"><span data-stu-id="ff5a0-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
  <span data-ttu-id="ff5a0-112">您可以生成绑定文件，并将它们包含的绑定应用到程序集、 应用程序或组。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-112">You can generate binding files and then apply the bindings they contain to an assembly, application, or group.</span></span> <span data-ttu-id="ff5a0-113">这避免了必须在不同的部署环境中手动配置绑定，并加快应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
<span data-ttu-id="ff5a0-114">绑定文件不自动生成 BizTalk 程序集、 应用程序，或组。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="ff5a0-115">但是，您可以生成绑定文件导出的绑定。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="ff5a0-116">然后可以将绑定文件导入的应用程序或组。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-116">You can then import the binding file into an application or group.</span></span>  
  
<span data-ttu-id="ff5a0-117">有关绑定和绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="ff5a0-118">先决条件</span><span class="sxs-lookup"><span data-stu-id="ff5a0-118">Prerequisites</span></span>  
<span data-ttu-id="ff5a0-119">是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-119">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="ff5a0-120">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-120">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>
 
## <a name="export-bindings"></a><span data-ttu-id="ff5a0-121">导出绑定</span><span class="sxs-lookup"><span data-stu-id="ff5a0-121">Export bindings</span></span>
<span data-ttu-id="ff5a0-122">本部分介绍如何导出到 XML 文件的 BizTalk 应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-122">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="ff5a0-123">您然后可以从 XML 文件到另一个 BizTalk 应用程序来导入绑定。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-123">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="ff5a0-124">导入绑定将覆盖相同名称的应用程序中的所有现有绑定。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-124">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="ff5a0-125">此外可以将绑定添加到应用程序，不会覆盖现有绑定。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-125">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="ff5a0-126">导入应用程序添加的绑定会生效。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-126">The bindings that you add do not take effect until you import the application.</span></span>  
  
1. <span data-ttu-id="ff5a0-127">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-127">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="ff5a0-128">展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-128">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="ff5a0-129">右键单击你想要导出，其的绑定选择应用程序**导出**，然后选择**绑定**。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-129">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="ff5a0-130">上**导出绑定**页上，在**导出到文件**，键入要导出绑定到 XML 文件的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-130">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="ff5a0-131">例如，输入 `C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="ff5a0-131">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5. <span data-ttu-id="ff5a0-132">确认**导出当前应用程序中的所有绑定**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-132">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6. <span data-ttu-id="ff5a0-133">若要导出组的所有参与方信息，请选择**导出全局参与方信息**复选框。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-133">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7. <span data-ttu-id="ff5a0-134">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-134">Select **OK**.</span></span> <span data-ttu-id="ff5a0-135">绑定被导出到 XML 文件中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-135">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="ff5a0-136">导入绑定</span><span class="sxs-lookup"><span data-stu-id="ff5a0-136">Import bindings</span></span>
<span data-ttu-id="ff5a0-137">导入绑定使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-137">Import bindings using the BizTalk Server Administration console.</span></span>
  
1. <span data-ttu-id="ff5a0-138">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-138">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="ff5a0-139">展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-139">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="ff5a0-140">右键单击您要向其中导入绑定中，选择应用的程序**导入**，然后选择**绑定**。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-140">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="ff5a0-141">选择绑定文件，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-141">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="ff5a0-142">绑定文件中的项目将写入到应用程序。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-142">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="ff5a0-143">它们显示在应用程序的相应文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-143">They display in appropriate folders of the application.</span></span> <span data-ttu-id="ff5a0-144">例如，发送端口导入的绑定显示在下一部分**发送端口**文件夹。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-144">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="ff5a0-145">不会保留密码</span><span class="sxs-lookup"><span data-stu-id="ff5a0-145">Passwords are removed</span></span>  
<span data-ttu-id="ff5a0-146">出于安全原因，当您导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]会从文件删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-146">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="ff5a0-147">导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-147">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="ff5a0-148">在的传输属性对话框中配置密码[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台为发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-148">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="ff5a0-149">有关指定用户名和密码的信息，请参阅[配置为 SAP 系统的凭据登录](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="ff5a0-149">For information about specifying user name and passwords, see [Configure the sign in credentials for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff5a0-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff5a0-150">See also</span></span>
[<span data-ttu-id="ff5a0-151">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="ff5a0-151">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)