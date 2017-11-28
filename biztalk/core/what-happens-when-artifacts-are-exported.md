---
title: "导出项目时，会发生什么情况 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exporting, artifacts
- artifacts, exporting
ms.assetid: accc9a81-01fb-4da7-a5a5-167835d393a2
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92a65889ea642706ae5c51849748fd8ad085a02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-when-artifacts-are-exported"></a><span data-ttu-id="40cfa-102">导出项目时发生的情况</span><span class="sxs-lookup"><span data-stu-id="40cfa-102">What Happens When Artifacts Are Exported</span></span>
<span data-ttu-id="40cfa-103">本主题介绍导出项目时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="40cfa-103">This topic describes what happens when you export artifacts.</span></span> <span data-ttu-id="40cfa-104">可以通过本主题介绍的三种方式导出项目：</span><span class="sxs-lookup"><span data-stu-id="40cfa-104">There are three ways to export artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="40cfa-105">将 BizTalk 应用程序及其项目导出到 BizTalk .msi (Windows Installer) 文件中</span><span class="sxs-lookup"><span data-stu-id="40cfa-105">Exporting a BizTalk application and its artifacts into a BizTalk .msi (Windows Installer) file</span></span>  
  
-   <span data-ttu-id="40cfa-106">将策略导出到 .xml 文件中</span><span class="sxs-lookup"><span data-stu-id="40cfa-106">Exporting a policy into an .xml file</span></span>  
  
-   <span data-ttu-id="40cfa-107">将绑定导出到 .xml 文件中</span><span class="sxs-lookup"><span data-stu-id="40cfa-107">Exporting bindings into an .xml file</span></span>  
  
## <a name="exporting-a-biztalk-application"></a><span data-ttu-id="40cfa-108">导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="40cfa-108">Exporting a BizTalk application</span></span>  
 <span data-ttu-id="40cfa-109">在导出某一 BizTalk 应用程序以及它所包含的项目时，应用程序配置信息和项目数据将导出到 BizTalk .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="40cfa-109">When you export a BizTalk application and the artifacts it contains, application configuration information and artifact data is exported into a BizTalk .msi file.</span></span> <span data-ttu-id="40cfa-110">大多数项目数据都会从 BizTalk 管理数据库导出，但存在以下例外：</span><span class="sxs-lookup"><span data-stu-id="40cfa-110">Most artifact data is exported from the BizTalk Management database, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="40cfa-111">策略数据从组的规则引擎数据库中导出。</span><span class="sxs-lookup"><span data-stu-id="40cfa-111">Policy data is exported from the Rule Engine database for the group.</span></span>  
  
-   <span data-ttu-id="40cfa-112">虚拟目录数据从 Internet 信息服务 (IIS) 元数据库导出（如果在管理数据库中不存在这些数据）。</span><span class="sxs-lookup"><span data-stu-id="40cfa-112">Virtual directory data is exported from the Internet Information Services (IIS) metabase if it does not exist in the Management database.</span></span> <span data-ttu-id="40cfa-113">这将出现这种情况的虚拟目录尚未显式添加到应用程序 (如中所述[如何将虚拟目录添加到应用程序](../core/how-to-add-a-virtual-directory-to-an-application.md)) 或应用程序已不导入此组从.msi 文件从另一个 BizTalk 组导出。</span><span class="sxs-lookup"><span data-stu-id="40cfa-113">This will be the case when the virtual directory has not been explicitly added to the application (as described in [How to Add a Virtual Directory to an Application](../core/how-to-add-a-virtual-directory-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span>  
  
-   <span data-ttu-id="40cfa-114">证书数据从本地计算机上的其他人证书存储导出（如果在管理数据库中不存在证书数据）。</span><span class="sxs-lookup"><span data-stu-id="40cfa-114">Certificate data is exported from the Other People certificate store on the local computer, if it does not exist in the Management database.</span></span> <span data-ttu-id="40cfa-115">证书尚未显式添加到应用程序时，会遇到这种情况 (如中所述[如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)) 或应用程序已不导入从.msi 文件的此组从另一个 BizTalk 组导出。</span><span class="sxs-lookup"><span data-stu-id="40cfa-115">This will be the case when the certificate has not been explicitly added to the application (as described in [How to Add a Certificate to an Application](../core/how-to-add-a-certificate-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span> <span data-ttu-id="40cfa-116">在应用程序与证书与之关联的接收端口一起导出时，将导出证书。</span><span class="sxs-lookup"><span data-stu-id="40cfa-116">Certificates are exported when you export an application with a receive port that has a certificate associated with it.</span></span> <span data-ttu-id="40cfa-117">在导出时私钥将会从证书中删除。</span><span class="sxs-lookup"><span data-stu-id="40cfa-117">Private keys are removed from certificates on export.</span></span>  
  
 <span data-ttu-id="40cfa-118">您可以使用此 .msi 文件将应用程序的项目（包括其所有数据）导入到其他 BizTalk 组的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="40cfa-118">You can use this .msi file to import the application's artifacts, including all of their data, into an application in another BizTalk group.</span></span> <span data-ttu-id="40cfa-119">您还可以使用此 .msi 文件在计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="40cfa-119">You can also use this .msi file to install the application on a computer.</span></span>  
  
## <a name="exporting-a-policy"></a><span data-ttu-id="40cfa-120">导出策略</span><span class="sxs-lookup"><span data-stu-id="40cfa-120">Exporting a policy</span></span>  
 <span data-ttu-id="40cfa-121">在您使用管理控制台导出某一 BizTalk 组或应用程序的策略时，它将生成包含该策略信息的一个 .xml 策略文件。</span><span class="sxs-lookup"><span data-stu-id="40cfa-121">When you use the administration console to export a policy for either a BizTalk group or application, it generates an .xml policy file containing the policy information.</span></span> <span data-ttu-id="40cfa-122">您可以将该策略文件导入到其他 BizTalk 组中以在那里创建策略，以便该组中的应用程序可以使用该策略。</span><span class="sxs-lookup"><span data-stu-id="40cfa-122">You can import this policy file into another BizTalk group to create the policy there, so that applications in the group can use it.</span></span> <span data-ttu-id="40cfa-123">您还可以通过使用 BTSTask 导出应用程序的策略信息。</span><span class="sxs-lookup"><span data-stu-id="40cfa-123">You can also export policy information for an application by using BTSTask.</span></span> <span data-ttu-id="40cfa-124">但是，BTSTask 不具有用于导出策略 .xml 文件的命令。</span><span class="sxs-lookup"><span data-stu-id="40cfa-124">BTSTask, however, does not have a command to export a policy .xml file.</span></span> <span data-ttu-id="40cfa-125">您而是可以导出只包含该策略的应用程序 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="40cfa-125">Instead, you can export an application .msi file that contains only the policy.</span></span> <span data-ttu-id="40cfa-126">然后，可以将该 .msi 文件导入到另一个组的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="40cfa-126">You can then import the .msi file into an application in another group.</span></span>  
  
## <a name="exporting-bindings"></a><span data-ttu-id="40cfa-127">导出绑定</span><span class="sxs-lookup"><span data-stu-id="40cfa-127">Exporting bindings</span></span>  
 <span data-ttu-id="40cfa-128">您可以使用管理控制台或 BTSTask 为 BizTalk 组、应用程序或程序集导出绑定。</span><span class="sxs-lookup"><span data-stu-id="40cfa-128">You can use either the administration console or BTSTask to export bindings for a BizTalk group, application, or assembly.</span></span> <span data-ttu-id="40cfa-129">这样做了之后，BizTalk Server 将生成一个 .xml 文件，包含该组、应用程序或程序集的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="40cfa-129">When you do this, BizTalk Server generates an .xml file containing the binding information for the group, application, or assembly.</span></span> <span data-ttu-id="40cfa-130">在您导出绑定时，还可以导出该组的全局参与方信息。</span><span class="sxs-lookup"><span data-stu-id="40cfa-130">When you export bindings, you can also export global party information for the group.</span></span> <span data-ttu-id="40cfa-131">然后，您可以将此绑定文件添加到某一应用程序中，或将它导入到某一 BizTalk 组或应用程序中。</span><span class="sxs-lookup"><span data-stu-id="40cfa-131">You can then either add this binding file to an application or import it into a BizTalk group or application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cfa-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40cfa-132">See Also</span></span>  
 <span data-ttu-id="40cfa-133">[会发生什么情况项目在应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="40cfa-133">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="40cfa-134">[导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="40cfa-134">[Exporting BizTalk Applications, Bindings, and Policies](../core/exporting-biztalk-applications-bindings-and-policies.md) </span></span>  
 <span data-ttu-id="40cfa-135">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="40cfa-135">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="40cfa-136">如何将绑定文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="40cfa-136">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)