---
title: 应用程序部署安全建议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, applications
- best practices, applications
- best practices, security
- security, best practices
- applications, best practices
- applications, security
ms.assetid: 77902140-8b4c-437c-af4c-10a12b3bc950
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0402ef23de70150d541dfd672d2af7efe3a924
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231949"
---
# <a name="application-deployment-security-recommendations"></a><span data-ttu-id="7a55f-102">应用程序部署的安全建议</span><span class="sxs-lookup"><span data-stu-id="7a55f-102">Application Deployment Security Recommendations</span></span>
<span data-ttu-id="7a55f-103">下面是在您的环境中部署 BizTalk 应用程序时应遵守的一些准则：</span><span class="sxs-lookup"><span data-stu-id="7a55f-103">The following are guidelines for deploying BizTalk applications in your environment:</span></span>  
  
-   <span data-ttu-id="7a55f-104">将应用程序导出到某一 .msi 文件时，会从文件和文件夹中删除所有随机访问控制列表 (DACL)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-104">All discretionary access control lists (DACLs) are removed from files and folders when an application is exported into an .msi file.</span></span> <span data-ttu-id="7a55f-105">从该 .msi 文件安装应用程序后，必须对文件和文件夹重新配置所有的安全设置。</span><span class="sxs-lookup"><span data-stu-id="7a55f-105">After installing an application from the .msi file, you must reconfigure all security settings on the files and folders.</span></span>  
  
-   <span data-ttu-id="7a55f-106">出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="7a55f-106">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="7a55f-107">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="7a55f-107">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="7a55f-108">您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。</span><span class="sxs-lookup"><span data-stu-id="7a55f-108">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="7a55f-109">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-109">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="7a55f-110">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-110">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span> <span data-ttu-id="7a55f-111">有关绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-111">For more information about binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
-   <span data-ttu-id="7a55f-112">部署或取消部署属性架构可能会暴露敏感数据，进而在跟踪中暴露敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7a55f-112">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="7a55f-113">只要部署或取消部署包含属性架构的程序集，事件查看器就会在 Windows 应用程序事件日志中记录该事件。</span><span class="sxs-lookup"><span data-stu-id="7a55f-113">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="7a55f-114">您应该在事件日志中检查这些消息，以确保所有程序集部署活动均符合您的敏感数据策略。</span><span class="sxs-lookup"><span data-stu-id="7a55f-114">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span>  
  
     <span data-ttu-id="7a55f-115">事件日志中生成的部署消息为：</span><span class="sxs-lookup"><span data-stu-id="7a55f-115">The message generated to the Event Log for deployment is:</span></span>  
  
     <span data-ttu-id="7a55f-116">**用户"{1}"部署的程序集"{0}"包含属性的架构。**</span><span class="sxs-lookup"><span data-stu-id="7a55f-116">**The user "{1}" deployed the assembly "{0}" containing property schemas.**</span></span>  
  
     <span data-ttu-id="7a55f-117">事件日志中生成的取消部署消息为：</span><span class="sxs-lookup"><span data-stu-id="7a55f-117">The message generated to the Event Log for undeployment is:</span></span>  
  
     <span data-ttu-id="7a55f-118">**用户"{1}"已取消部署的程序集"{0}"包含属性的架构。**</span><span class="sxs-lookup"><span data-stu-id="7a55f-118">**The user "{1}" undeployed the assembly "{0}" containing property schemas.**</span></span>  
  
-   <span data-ttu-id="7a55f-119">如果应用程序包含虚拟目录则需要注意：虚拟目录的安全设置是在应用程序导出期间生成 .msi 文件时起作用的那些设置。</span><span class="sxs-lookup"><span data-stu-id="7a55f-119">If the application includes a virtual directory, be aware that the security settings on the virtual directory are those in effect when the .msi file is generated during application export.</span></span> <span data-ttu-id="7a55f-120">如果要向生产环境中部署应用程序，则在导出应用程序之前，应验证设置满足安全要求。</span><span class="sxs-lookup"><span data-stu-id="7a55f-120">If you are deploying an application into a production environment, before exporting the application, you should verify that the settings meet your security requirements.</span></span>  
  
     <span data-ttu-id="7a55f-121">不过，如果您部署包含某一虚拟目录的应用程序，并且目标环境中已经存在该虚拟目录，现有虚拟目录的安全设置将生效。</span><span class="sxs-lookup"><span data-stu-id="7a55f-121">If, however, you deploy an application that includes a virtual directory, and the virtual directory already exists in the destination environment, the security settings on the existing virtual directory will be in effect.</span></span> <span data-ttu-id="7a55f-122">它们不会被更改以匹配您部署的虚拟目录的安全设置。</span><span class="sxs-lookup"><span data-stu-id="7a55f-122">They are not changed to match those on the virtual directory you are deploying.</span></span> <span data-ttu-id="7a55f-123">您应该验证现有虚拟目录的安全设置是否满足您的要求。</span><span class="sxs-lookup"><span data-stu-id="7a55f-123">You should verify that the security settings on the existing virtual directory meet your requirements.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="7a55f-124">如果虚拟目录使用 HTTPS（安全超文本传输协议）协议，则在导出期间不会保留其安全设置，进行导入时，虚拟目录将继承根的安全设置。</span><span class="sxs-lookup"><span data-stu-id="7a55f-124">If the virtual directory uses the HTTPS (Hypertext Transfer Protocol over Secure Socket Layer) protocol, its security settings are not preserved during export, and when it is imported, the virtual directory will inherit the security settings of the root.</span></span> <span data-ttu-id="7a55f-125">您应该验证安全设置是否满足您的要求。</span><span class="sxs-lookup"><span data-stu-id="7a55f-125">You should verify that the security settings meet your requirements.</span></span>  
  
-   <span data-ttu-id="7a55f-126">如果为某一 Web Services 指定的应用程序池在您导入应用程序时不存在，则使用默认应用程序池。</span><span class="sxs-lookup"><span data-stu-id="7a55f-126">If the application pool specified for a Web service does not exist when you import an application, the default application pool is used.</span></span> <span data-ttu-id="7a55f-127">默认应用程序池上的安全设置可能不适合您的要求。</span><span class="sxs-lookup"><span data-stu-id="7a55f-127">The security settings on the default application pool may not be appropriate for your requirements.</span></span> <span data-ttu-id="7a55f-128">因此，我们建议您或者在导入应用程序前创建应用程序池并配置适当的安全设置，或者验证默认应用程序池上的设置是否适当。</span><span class="sxs-lookup"><span data-stu-id="7a55f-128">We therefore recommend that you either create the application pool and configure the appropriate security settings before importing the application, or verify that the settings on the default application pool are appropriate.</span></span>  
  
-   <span data-ttu-id="7a55f-129">请确保您信任所部署的 Windows Installer (.msi) 文件的来源，以便避免可能由恶意 .msi 文件创建者造成的安全问题。</span><span class="sxs-lookup"><span data-stu-id="7a55f-129">Ensure that you trust the source of the Windows Installer (.msi) files that you deploy to avoid security issues that can be created by malicious .msi file creators.</span></span> <span data-ttu-id="7a55f-130">有关详细信息，请参阅[安全和 Windows Installer](../core/security-and-windows-installer.md)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-130">For more information, see [Security and Windows Installer](../core/security-and-windows-installer.md).</span></span>  
  
-   <span data-ttu-id="7a55f-131">请确保您有权部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a55f-131">Ensure you have the permissions to deploy applications.</span></span> <span data-ttu-id="7a55f-132">有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-132">For more information, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="7a55f-133">请确保只有 BizTalk 管理员才能访问程序集、绑定文件和策略文件，因为它们可能包含连接和配置信息之类的重要业务数据。</span><span class="sxs-lookup"><span data-stu-id="7a55f-133">Ensure that only BizTalk administrators have access to the assemblies, binding files, and policy files, as they may contain critical business data such as connectivity and configuration information.</span></span> <span data-ttu-id="7a55f-134">如果您通过网络共享部署应用程序，则在网络共享上配置随机访问控制列表 (DACL)，以便只有 BizTalk 管理员才能查看其内容。</span><span class="sxs-lookup"><span data-stu-id="7a55f-134">If you deploy applications through a network share, configure the discretionary access control list (DACL) on the network share so that only BizTalk administrators can view its contents.</span></span> <span data-ttu-id="7a55f-135">有关组和用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-135">For more information about group and user accounts, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="7a55f-136">在您执行部署操作时，BizTalk Server 将与 BizTalk 管理数据库通信。</span><span class="sxs-lookup"><span data-stu-id="7a55f-136">When you perform deployment operations, BizTalk Server communicates with the BizTalk Management database.</span></span> <span data-ttu-id="7a55f-137">如果在它们之间存在某一防火墙，则必须打开处理、服务和数据域之间的防火墙上的适当端口。</span><span class="sxs-lookup"><span data-stu-id="7a55f-137">If a firewall exists between them, you must open the appropriate ports on the firewall between the processing, services, and data domains.</span></span> <span data-ttu-id="7a55f-138">有关详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7a55f-138">For more information, see [Required Ports for BizTalk Server](../core/required-ports-for-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="7a55f-139">如果您指向可能包含敏感数据的某一程序集、绑定文件或其他资源文件的远程位置，则应考虑源计算机和您从其执行部署的计算机之间的网络安全性。</span><span class="sxs-lookup"><span data-stu-id="7a55f-139">If you point to a remote location for an assembly, binding file, or other resource file that may contain sensitive data, you should consider network security between source computer and the computer from which you are running deployment.</span></span> <span data-ttu-id="7a55f-140">如果这两台计算机之间的网络没有完全与潜在的攻击者隔离，则您应将目标文件复制到可移动媒体上，并将其物理传输到您要执行部署的计算机上。</span><span class="sxs-lookup"><span data-stu-id="7a55f-140">If the network between these two computers is not fully isolated from potential attackers, you should copy the target file to removable media and physically transport it to the computer where you run deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a55f-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a55f-141">See Also</span></span>  
 [<span data-ttu-id="7a55f-142">应用程序部署的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="7a55f-142">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)