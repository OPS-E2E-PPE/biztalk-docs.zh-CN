---
title: "如何删除其他文件和 BizTalk 应用程序设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], deleting settings
- managing [applications], deleting files
- undeploying, settings
- applications, undeploying
- undeploying, files
ms.assetid: b947831a-c988-435c-92ec-45f3fd6967de
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9ad98e0f0fc1e65281a1d8195be4f4a708d004f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-other-files-and-settings-for-a-biztalk-application"></a><span data-ttu-id="ad887-102">如何删除 BizTalk 应用程序的其他文件和设置</span><span class="sxs-lookup"><span data-stu-id="ad887-102">How to Remove Other Files and Settings for a BizTalk Application</span></span>
<span data-ttu-id="ad887-103">本主题描述如何删除在卸载应用程序时不能删除 BizTalk 应用程序的文件和设置 (中所述[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md))。</span><span class="sxs-lookup"><span data-stu-id="ad887-103">This topic describes how to remove files and settings for a BizTalk application that may not be removed when you uninstall the application (which is described in [How to Uninstall a BizTalk Application](../core/how-to-uninstall-a-biztalk-application.md)).</span></span> <span data-ttu-id="ad887-104">例如，证书、COM 和 COM+ 注册表条目以及 COM 文件就不会删除，除非该应用程序包括在卸载时会删除它们的后处理脚本。</span><span class="sxs-lookup"><span data-stu-id="ad887-104">For example, certificates, COM and COM+ registry entries, and COM files are not removed unless the application included a post-processing script that removed them on uninstallation.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ad887-105">在删除任何共享项之前，请确保没有其他应用程序在使用它们，否则应用程序将不会正常工作。</span><span class="sxs-lookup"><span data-stu-id="ad887-105">Before removing any shared items, make certain that no other applications are using them, or the applications will not function correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad887-106">我们建议您通过使用后处理脚本，令这一删除自动化。</span><span class="sxs-lookup"><span data-stu-id="ad887-106">We recommend that you automate this removal by using a post-processing script.</span></span> <span data-ttu-id="ad887-107">有关详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="ad887-107">For more information, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
-   <span data-ttu-id="ad887-108">**删除证书。**</span><span class="sxs-lookup"><span data-stu-id="ad887-108">**Delete Certificates.**</span></span> <span data-ttu-id="ad887-109">可通过两种方式从证书存储中删除证书：使用证书管理器 (certmgr.exe) 命令行工具或证书管理单元。</span><span class="sxs-lookup"><span data-stu-id="ad887-109">There are two ways to delete certificates from the certificate store: by using the Certificate Manager (certmgr.exe) command-line tool or the Certificates snap-in.</span></span> <span data-ttu-id="ad887-110">Certmgr.exe 安装使用.NET SDK，这是一个的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装系统必备组件。</span><span class="sxs-lookup"><span data-stu-id="ad887-110">Certmgr.exe is installed with the .NET SDK, which is one of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation prerequisites.</span></span> <span data-ttu-id="ad887-111">您可以手动运行 certmgr.exe，也可以通过后处理脚本自动运行该文件。</span><span class="sxs-lookup"><span data-stu-id="ad887-111">You can run certmgr.exe manually, or you can run it from a post-processing script.</span></span> <span data-ttu-id="ad887-112">有关使用 certmgr.exe 的详细信息，请参阅[证书管理器工具 (certmgr.exe)](http://go.microsoft.com/fwlink/?LinkId=56198)在 Microsoft Web 站点。</span><span class="sxs-lookup"><span data-stu-id="ad887-112">For more information about using certmgr.exe, see [Certificate Manager Tool (certmgr.exe)](http://go.microsoft.com/fwlink/?LinkId=56198) at the Microsoft Web site.</span></span>  
  
     <span data-ttu-id="ad887-113">Windows Server 2008 和 Windows Vista 中均包括证书管理单元。</span><span class="sxs-lookup"><span data-stu-id="ad887-113">The Certificates snap-in is included in both Windows Server 2008 and Windows Vista.</span></span> <span data-ttu-id="ad887-114">若要删除某一证书，请根据操作系统帮助文件中“启动证书管理单元”的说明打开该管理单元，然后根据证书帮助中“删除证书”的说明删除该证书。</span><span class="sxs-lookup"><span data-stu-id="ad887-114">To delete a certificate, open the snap-in, as described in "Starting the Certificates snap-in" in Help for your operating system, and then delete the certificate as described in "Delete a certificate" in Certificates Help.</span></span>  
  
-   <span data-ttu-id="ad887-115">**从 Windows 注册表中移除程序集。**</span><span class="sxs-lookup"><span data-stu-id="ad887-115">**Remove assemblies from the Windows Registry.**</span></span> <span data-ttu-id="ad887-116">若要从 Windows 注册表中删除 .NET 和 BizTalk 程序集，请使用 .NET SDK 所附带的 regsvcs 或 regasm，.NET SDK 是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装的先决条件之一。</span><span class="sxs-lookup"><span data-stu-id="ad887-116">To remove .NET and BizTalk assemblies from the Windows registry, use regsvcs or regasm, which are included with the .NET SDK, which is one of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation prerequisites.</span></span> <span data-ttu-id="ad887-117">有关引用信息，请参阅[.NET 服务安装工具 (Regsvcs.exe)](http://go.microsoft.com/fwlink/?LinkId=56199)和[程序集注册工具 (Regasm.exe)](http://go.microsoft.com/fwlink/?LinkId=56200)在 Microsoft Web 站点。</span><span class="sxs-lookup"><span data-stu-id="ad887-117">For reference information, see [.NET Services Installation Tool (Regsvcs.exe)](http://go.microsoft.com/fwlink/?LinkId=56199) and [Assembly Registration Tool (Regasm.exe)](http://go.microsoft.com/fwlink/?LinkId=56200) at the Microsoft Web site.</span></span>  
  
-   <span data-ttu-id="ad887-118">**从 Windows 注册表中删除 COM 组件。**</span><span class="sxs-lookup"><span data-stu-id="ad887-118">**Remove COM components from the Windows Registry.**</span></span> <span data-ttu-id="ad887-119">若要从 Windows 注册表删除 COM 组件，请使用 regsvr32。</span><span class="sxs-lookup"><span data-stu-id="ad887-119">To remove COM components from the Windows Registry, use regsvr32.</span></span> <span data-ttu-id="ad887-120">有关参考信息，请参阅操作系统帮助中的“Regsvr32”。</span><span class="sxs-lookup"><span data-stu-id="ad887-120">For reference information, see "Regsvr32" in Help for your operating system.</span></span> <span data-ttu-id="ad887-121">Windows Server 2008 和 Windows Vista Professional 中均包括此工具。</span><span class="sxs-lookup"><span data-stu-id="ad887-121">This tool is included in both Windows Server 2008 and Windows Vista Professional.</span></span>  
  
-   <span data-ttu-id="ad887-122">**从全局程序集缓存 (GAC) 中卸载程序集。**</span><span class="sxs-lookup"><span data-stu-id="ad887-122">**Uninstall assemblies from the global assembly cache (GAC).**</span></span> <span data-ttu-id="ad887-123">程序集不从 GAC 中自动卸载。</span><span class="sxs-lookup"><span data-stu-id="ad887-123">Assemblies are not automatically uninstalled from the GAC.</span></span> <span data-ttu-id="ad887-124">您可以从 GAC 手动卸载程序集，或者使用脚本进行卸载。</span><span class="sxs-lookup"><span data-stu-id="ad887-124">You can uninstall an assembly from the GAC manually or by using a script.</span></span> <span data-ttu-id="ad887-125">有关详细信息，请参阅[如何从 GAC 中卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。</span><span class="sxs-lookup"><span data-stu-id="ad887-125">For more information, see [How to Uninstall an Assembly from the GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ad887-126">先决条件</span><span class="sxs-lookup"><span data-stu-id="ad887-126">Prerequisites</span></span>  
 <span data-ttu-id="ad887-127">若要删除本主题中描述的文件和设置，则根据您要删除的内容，您登录时所采用的身份必须对 Windows 注册表、GAC 或证书存储具有写权限。</span><span class="sxs-lookup"><span data-stu-id="ad887-127">To remove the files and settings described in this topic, you must be logged on with Write permissions on the Windows Registry, the GAC, or the certificate store, depending on what you want to remove.</span></span> <span data-ttu-id="ad887-128">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ad887-128">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad887-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad887-129">See Also</span></span>  
 <span data-ttu-id="ad887-130">[正在取消部署的 BizTalk 应用程序](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ad887-130">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="ad887-131">如何卸载 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ad887-131">How to Uninstall a BizTalk Application</span></span>](../core/how-to-uninstall-a-biztalk-application.md)