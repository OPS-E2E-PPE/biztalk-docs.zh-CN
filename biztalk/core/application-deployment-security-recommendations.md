---
title: 应用程序部署的安全建议 |Microsoft Docs
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
ms.openlocfilehash: 0ea901fdc44887d92d221af6e737aa133943b14d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359071"
---
# <a name="application-deployment-security-recommendations"></a><span data-ttu-id="06658-102">应用程序部署的安全建议</span><span class="sxs-lookup"><span data-stu-id="06658-102">Application Deployment Security Recommendations</span></span>
<span data-ttu-id="06658-103">以下是部署在环境中的 BizTalk 应用程序的准则：</span><span class="sxs-lookup"><span data-stu-id="06658-103">The following are guidelines for deploying BizTalk applications in your environment:</span></span>  
  
-   <span data-ttu-id="06658-104">应用程序导出到.msi 文件时，将从文件和文件夹中删除所有随机访问控制列表 (Dacl)。</span><span class="sxs-lookup"><span data-stu-id="06658-104">All discretionary access control lists (DACLs) are removed from files and folders when an application is exported into an .msi file.</span></span> <span data-ttu-id="06658-105">从.msi 文件安装应用程序之后, 必须重新配置的文件和文件夹上的所有安全设置。</span><span class="sxs-lookup"><span data-stu-id="06658-105">After installing an application from the .msi file, you must reconfigure all security settings on the files and folders.</span></span>  
  
-   <span data-ttu-id="06658-106">出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。</span><span class="sxs-lookup"><span data-stu-id="06658-106">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="06658-107">导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。</span><span class="sxs-lookup"><span data-stu-id="06658-107">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="06658-108">发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。</span><span class="sxs-lookup"><span data-stu-id="06658-108">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="06658-109">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="06658-109">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="06658-110">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="06658-110">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span> <span data-ttu-id="06658-111">有关绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="06658-111">For more information about binding files, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
-   <span data-ttu-id="06658-112">部署或取消部署属性架构可能暴露敏感数据，并随后暴露在跟踪的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="06658-112">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="06658-113">每当部署或已取消部署包含属性架构的程序集时，事件查看器记录的事件在 Windows 应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="06658-113">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="06658-114">应检查这些消息，以确保所有程序集部署活动均符合你的策略的任何敏感数据在事件日志。</span><span class="sxs-lookup"><span data-stu-id="06658-114">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span>  
  
     <span data-ttu-id="06658-115">部署的事件日志中生成的消息为：</span><span class="sxs-lookup"><span data-stu-id="06658-115">The message generated to the Event Log for deployment is:</span></span>  
  
     <span data-ttu-id="06658-116">**用户"{1}"已部署程序集"{0}"包含属性架构。**</span><span class="sxs-lookup"><span data-stu-id="06658-116">**The user "{1}" deployed the assembly "{0}" containing property schemas.**</span></span>  
  
     <span data-ttu-id="06658-117">取消部署事件日志中生成的消息为：</span><span class="sxs-lookup"><span data-stu-id="06658-117">The message generated to the Event Log for undeployment is:</span></span>  
  
     <span data-ttu-id="06658-118">**用户"{1}"已取消部署程序集"{0}"包含属性架构。**</span><span class="sxs-lookup"><span data-stu-id="06658-118">**The user "{1}" undeployed the assembly "{0}" containing property schemas.**</span></span>  
  
-   <span data-ttu-id="06658-119">如果应用程序中包括虚拟目录，请注意，虚拟目录上的安全设置是生效时的那些应用程序导出期间生成.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="06658-119">If the application includes a virtual directory, be aware that the security settings on the virtual directory are those in effect when the .msi file is generated during application export.</span></span> <span data-ttu-id="06658-120">如果要部署到生产环境中，应用程序，然后导出该应用程序，则应验证设置满足安全要求。</span><span class="sxs-lookup"><span data-stu-id="06658-120">If you are deploying an application into a production environment, before exporting the application, you should verify that the settings meet your security requirements.</span></span>  
  
     <span data-ttu-id="06658-121">如果，但是，部署的应用程序中包括虚拟目录，并在目标环境中，已存在虚拟目录上的现有虚拟目录的安全设置将生效。</span><span class="sxs-lookup"><span data-stu-id="06658-121">If, however, you deploy an application that includes a virtual directory, and the virtual directory already exists in the destination environment, the security settings on the existing virtual directory will be in effect.</span></span> <span data-ttu-id="06658-122">它们不会更改以匹配您要部署的虚拟目录上。</span><span class="sxs-lookup"><span data-stu-id="06658-122">They are not changed to match those on the virtual directory you are deploying.</span></span> <span data-ttu-id="06658-123">您应该验证现有虚拟目录上的安全设置满足你的要求。</span><span class="sxs-lookup"><span data-stu-id="06658-123">You should verify that the security settings on the existing virtual directory meet your requirements.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="06658-124">如果虚拟目录使用 HTTPS （超文本传输协议通过安全套接字层） 协议，在导出期间，不保留其安全设置和导入它时，虚拟目录将继承根的安全设置。</span><span class="sxs-lookup"><span data-stu-id="06658-124">If the virtual directory uses the HTTPS (Hypertext Transfer Protocol over Secure Socket Layer) protocol, its security settings are not preserved during export, and when it is imported, the virtual directory will inherit the security settings of the root.</span></span> <span data-ttu-id="06658-125">应验证的安全设置满足你的要求。</span><span class="sxs-lookup"><span data-stu-id="06658-125">You should verify that the security settings meet your requirements.</span></span>  
  
-   <span data-ttu-id="06658-126">如果指定的 Web 服务的应用程序池不存在时导入应用程序，则使用默认应用程序池。</span><span class="sxs-lookup"><span data-stu-id="06658-126">If the application pool specified for a Web service does not exist when you import an application, the default application pool is used.</span></span> <span data-ttu-id="06658-127">默认应用程序池上的安全设置可能不适合你的要求。</span><span class="sxs-lookup"><span data-stu-id="06658-127">The security settings on the default application pool may not be appropriate for your requirements.</span></span> <span data-ttu-id="06658-128">因此，我们建议你创建的应用程序池并导入应用程序之前配置适当的安全设置，或验证默认应用程序池上的设置适用。</span><span class="sxs-lookup"><span data-stu-id="06658-128">We therefore recommend that you either create the application pool and configure the appropriate security settings before importing the application, or verify that the settings on the default application pool are appropriate.</span></span>  
  
-   <span data-ttu-id="06658-129">请确保您信任的 Windows Installer (.msi) 文件的部署以避免可能由恶意.msi 文件创建者造成的安全问题源。</span><span class="sxs-lookup"><span data-stu-id="06658-129">Ensure that you trust the source of the Windows Installer (.msi) files that you deploy to avoid security issues that can be created by malicious .msi file creators.</span></span> <span data-ttu-id="06658-130">有关详细信息，请参阅[安全性和 Windows 安装程序](../core/security-and-windows-installer.md)。</span><span class="sxs-lookup"><span data-stu-id="06658-130">For more information, see [Security and Windows Installer](../core/security-and-windows-installer.md).</span></span>  
  
-   <span data-ttu-id="06658-131">请确保您有权部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="06658-131">Ensure you have the permissions to deploy applications.</span></span> <span data-ttu-id="06658-132">有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="06658-132">For more information, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="06658-133">确保只有 BizTalk 管理员才有权访问程序集、 绑定文件和策略文件，因为它们可能包含连接和配置信息之类的关键业务数据。</span><span class="sxs-lookup"><span data-stu-id="06658-133">Ensure that only BizTalk administrators have access to the assemblies, binding files, and policy files, as they may contain critical business data such as connectivity and configuration information.</span></span> <span data-ttu-id="06658-134">如果你部署应用程序通过网络共享，配置网络共享上的自由访问控制列表 (DACL)，以便只有 BizTalk 管理员可以查看其内容。</span><span class="sxs-lookup"><span data-stu-id="06658-134">If you deploy applications through a network share, configure the discretionary access control list (DACL) on the network share so that only BizTalk administrators can view its contents.</span></span> <span data-ttu-id="06658-135">有关组和用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="06658-135">For more information about group and user accounts, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="06658-136">在执行部署操作时，BizTalk Server 与 BizTalk 管理数据库通信。</span><span class="sxs-lookup"><span data-stu-id="06658-136">When you perform deployment operations, BizTalk Server communicates with the BizTalk Management database.</span></span> <span data-ttu-id="06658-137">如果它们之间存在防火墙，则必须打开处理、 服务和数据域之间的防火墙上相应的端口。</span><span class="sxs-lookup"><span data-stu-id="06658-137">If a firewall exists between them, you must open the appropriate ports on the firewall between the processing, services, and data domains.</span></span> <span data-ttu-id="06658-138">有关详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="06658-138">For more information, see [Required Ports for BizTalk Server](../core/required-ports-for-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="06658-139">如果您指向远程位置的程序集、 绑定文件或其他资源文件，可能包含敏感数据，则应考虑源计算机和运行部署的计算机之间的网络安全。</span><span class="sxs-lookup"><span data-stu-id="06658-139">If you point to a remote location for an assembly, binding file, or other resource file that may contain sensitive data, you should consider network security between source computer and the computer from which you are running deployment.</span></span> <span data-ttu-id="06658-140">如果这两台计算机之间的网络不是与潜在攻击者完全隔离的应将目标文件复制到可移动介质，并以物理方式将其传输到运行部署的计算机。</span><span class="sxs-lookup"><span data-stu-id="06658-140">If the network between these two computers is not fully isolated from potential attackers, you should copy the target file to removable media and physically transport it to the computer where you run deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06658-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="06658-141">See Also</span></span>  
 [<span data-ttu-id="06658-142">应用程序部署的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="06658-142">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)