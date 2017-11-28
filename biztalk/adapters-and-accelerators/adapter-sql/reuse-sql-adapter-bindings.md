---
title: "重用 SQL 适配器绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bc8140f-1d40-492c-bce1-b85e992b3567
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67868f20426228c71bad2ef1f1f35e2e49299929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reuse-sql-adapter-bindings"></a><span data-ttu-id="0a8a5-102">重用 SQL 适配器绑定</span><span class="sxs-lookup"><span data-stu-id="0a8a5-102">Reuse SQL adapter bindings</span></span>
<span data-ttu-id="0a8a5-103">绑定创建的逻辑终结点 （如业务流程端口或角色链接） 和物理终结点之间的映射 (如发送和接收端口)。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="0a8a5-104">这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="0a8a5-105">你可以通过使用创建绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-105">You can create bindings by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="0a8a5-106">什么是绑定文件？</span><span class="sxs-lookup"><span data-stu-id="0a8a5-106">What is a Binding File?</span></span>  
 <span data-ttu-id="0a8a5-107">绑定文件是一个包含每个 BizTalk 业务流程的作用域中的 BizTalk 程序集、 应用程序或组的绑定信息的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="0a8a5-108">绑定文件描述：</span><span class="sxs-lookup"><span data-stu-id="0a8a5-108">The binding file describes:</span></span>  
  
-   <span data-ttu-id="0a8a5-109">每个业务流程绑定到主机。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-109">The host to which each orchestration is bound.</span></span>  
  
-   <span data-ttu-id="0a8a5-110">主机的信任级别。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-110">The trust level of the host.</span></span>  
  
-   <span data-ttu-id="0a8a5-111">每个设置发送端口、 接收端口、 接收位置和已配置的当事方。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-111">The settings for each send port, receive port, receive location, and party that has been configured.</span></span>  
  
 <span data-ttu-id="0a8a5-112">你可以生成绑定文件，并将它们包含的绑定应用于一个程序集，应用程序或组。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="0a8a5-113">这样可以防止无需在不同的部署环境中手动配置绑定，加快应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
 <span data-ttu-id="0a8a5-114">BizTalk 程序集，应用程序，或组不自动生成一个绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="0a8a5-115">但是，你可以通过导出绑定生成绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="0a8a5-116">同样，然后可以导入的应用程序或组的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-116">Similarly, you can then import the binding file into an application or group.</span></span> <span data-ttu-id="0a8a5-117">本部分提供有关如何导入和导出绑定的说明。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-117">This section provides instructions on how to import and export bindings.</span></span>  
  
 <span data-ttu-id="0a8a5-118">有关绑定和绑定文件有关的详细信息，请参阅[绑定文件和应用程序部署](../../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-118">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a8a5-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="0a8a5-119">Prerequisites</span></span>  
<span data-ttu-id="0a8a5-120">使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-120">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="0a8a5-121">有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-121">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
 
## <a name="export-bindings"></a><span data-ttu-id="0a8a5-122">导出绑定</span><span class="sxs-lookup"><span data-stu-id="0a8a5-122">Export bindings</span></span>
<span data-ttu-id="0a8a5-123">本部分介绍如何导出到 XML 文件的 BizTalk 应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-123">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="0a8a5-124">您然后可以从 XML 文件到另一个 BizTalk 应用程序来导入绑定。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-124">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="0a8a5-125">导入绑定将覆盖任何现有的应用程序中相同的名称绑定。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-125">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="0a8a5-126">你还可以向应用程序，不会覆盖现有绑定添加绑定。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-126">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="0a8a5-127">在导入应用程序之前，你添加的绑定不会生效。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-127">The bindings that you add do not take effect until you import the application.</span></span>  
  
1.  <span data-ttu-id="0a8a5-128">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-128">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0a8a5-129">展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-129">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="0a8a5-130">右键单击你想要导出，其的绑定选择的应用**导出**，然后选择**绑定**。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-130">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="0a8a5-131">上**导出绑定**页上，在**导出到文件**，键入要导出绑定到 XML 文件的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-131">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="0a8a5-132">例如，输入`C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="0a8a5-132">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5.  <span data-ttu-id="0a8a5-133">确认**导出当前应用程序中的所有绑定**选择。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-133">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6.  <span data-ttu-id="0a8a5-134">若要导出的组的所有方信息，请选择**都导出全局方信息**复选框。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-134">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7.  <span data-ttu-id="0a8a5-135">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-135">Select **OK**.</span></span> <span data-ttu-id="0a8a5-136">绑定将导出到 XML 文件中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-136">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="0a8a5-137">导入的绑定</span><span class="sxs-lookup"><span data-stu-id="0a8a5-137">Import bindings</span></span>
<span data-ttu-id="0a8a5-138">导入使用 BizTalk Server 管理控制台的绑定。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-138">Import bindings using the BizTalk Server Administration console.</span></span>
  
1.  <span data-ttu-id="0a8a5-139">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-139">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0a8a5-140">展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-140">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="0a8a5-141">右键单击你要向其中导入的绑定中，选择应用的程序**导入**，然后选择**绑定**。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-141">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="0a8a5-142">选择绑定文件，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-142">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="0a8a5-143">绑定文件中的项目将写入该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-143">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="0a8a5-144">这些项目显示在该应用程序的相应文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-144">They display in appropriate folders of the application.</span></span> <span data-ttu-id="0a8a5-145">例如，发送端口导入的绑定显示在下一部分**发送端口**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-145">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="0a8a5-146">不会保留密码</span><span class="sxs-lookup"><span data-stu-id="0a8a5-146">Passwords are removed</span></span>  
<span data-ttu-id="0a8a5-147">出于安全原因，当导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-147">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="0a8a5-148">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-148">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="0a8a5-149">传输属性对话框中配置密码[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台为发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-149">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="0a8a5-150">有关指定用户名和密码的信息，请参阅[配置 SQL Server 的登录凭据](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8a5-150">For information about specifying user name and passwords, see [Configure the sign in credentials for the SQL Server](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0a8a5-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a8a5-151">See Also</span></span>  
[<span data-ttu-id="0a8a5-152">开发具有 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="0a8a5-152">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)