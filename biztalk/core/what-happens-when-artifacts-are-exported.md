---
title: 导出项目时，会发生什么情况 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting, artifacts
- artifacts, exporting
ms.assetid: accc9a81-01fb-4da7-a5a5-167835d393a2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ab32fb2931f8a0294356e94d9f80f29b5b7c84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258508"
---
# <a name="what-happens-when-artifacts-are-exported"></a><span data-ttu-id="c37e6-102">导出项目时，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="c37e6-102">What Happens When Artifacts Are Exported</span></span>
<span data-ttu-id="c37e6-103">本主题介绍导出项目时，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="c37e6-103">This topic describes what happens when you export artifacts.</span></span> <span data-ttu-id="c37e6-104">有三种方法导出本主题中介绍的项目：</span><span class="sxs-lookup"><span data-stu-id="c37e6-104">There are three ways to export artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="c37e6-105">将 BizTalk 应用程序及其项目导出到 BizTalk.msi （Windows 安装程序） 文件</span><span class="sxs-lookup"><span data-stu-id="c37e6-105">Exporting a BizTalk application and its artifacts into a BizTalk .msi (Windows Installer) file</span></span>  
  
-   <span data-ttu-id="c37e6-106">将策略导出到.xml 文件</span><span class="sxs-lookup"><span data-stu-id="c37e6-106">Exporting a policy into an .xml file</span></span>  
  
-   <span data-ttu-id="c37e6-107">将绑定导出到.xml 文件</span><span class="sxs-lookup"><span data-stu-id="c37e6-107">Exporting bindings into an .xml file</span></span>  
  
## <a name="exporting-a-biztalk-application"></a><span data-ttu-id="c37e6-108">导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="c37e6-108">Exporting a BizTalk application</span></span>  
 <span data-ttu-id="c37e6-109">导出 BizTalk 应用程序和它包含的项目时，应用程序配置信息和项目数据导出到 BizTalk.msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="c37e6-109">When you export a BizTalk application and the artifacts it contains, application configuration information and artifact data is exported into a BizTalk .msi file.</span></span> <span data-ttu-id="c37e6-110">大多数项目数据导出从 BizTalk 管理数据库，但存在以下例外：</span><span class="sxs-lookup"><span data-stu-id="c37e6-110">Most artifact data is exported from the BizTalk Management database, with the following exceptions:</span></span>  
  
- <span data-ttu-id="c37e6-111">从组的规则引擎数据库导出策略的数据。</span><span class="sxs-lookup"><span data-stu-id="c37e6-111">Policy data is exported from the Rule Engine database for the group.</span></span>  
  
- <span data-ttu-id="c37e6-112">如果不存在管理数据库中，从 Internet 信息服务 (IIS) 元数据库导出虚拟目录的数据。</span><span class="sxs-lookup"><span data-stu-id="c37e6-112">Virtual directory data is exported from the Internet Information Services (IIS) metabase if it does not exist in the Management database.</span></span> <span data-ttu-id="c37e6-113">虚拟目录尚未显式添加到应用程序时，会遇到这种情况 (如中所述[如何向应用程序添加虚拟目录](../core/how-to-add-a-virtual-directory-to-an-application.md)) 或应用程序已不导入此组从某一.msi 文件从其他 BizTalk 组导出。</span><span class="sxs-lookup"><span data-stu-id="c37e6-113">This will be the case when the virtual directory has not been explicitly added to the application (as described in [How to Add a Virtual Directory to an Application](../core/how-to-add-a-virtual-directory-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span>  
  
- <span data-ttu-id="c37e6-114">如果不存在管理数据库中，从本地计算机上的其他人证书存储导出证书数据。</span><span class="sxs-lookup"><span data-stu-id="c37e6-114">Certificate data is exported from the Other People certificate store on the local computer, if it does not exist in the Management database.</span></span> <span data-ttu-id="c37e6-115">该证书尚未显式添加到应用程序时，会遇到这种情况 (如中所述[如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)) 或应用程序已不导入从.msi 文件时，此组从另一个 BizTalk 组中导出。</span><span class="sxs-lookup"><span data-stu-id="c37e6-115">This will be the case when the certificate has not been explicitly added to the application (as described in [How to Add a Certificate to an Application](../core/how-to-add-a-certificate-to-an-application.md)) or the application has not been imported into this group from an .msi file that was exported from another BizTalk group.</span></span> <span data-ttu-id="c37e6-116">导出具有与之关联的证书的接收端口的应用程序时，将导出的证书。</span><span class="sxs-lookup"><span data-stu-id="c37e6-116">Certificates are exported when you export an application with a receive port that has a certificate associated with it.</span></span> <span data-ttu-id="c37e6-117">从导出的证书删除私钥。</span><span class="sxs-lookup"><span data-stu-id="c37e6-117">Private keys are removed from certificates on export.</span></span>  
  
  <span data-ttu-id="c37e6-118">您可以使用此.msi 文件导入应用程序的项目，包括其所有数据，更改为另一个 BizTalk 组中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c37e6-118">You can use this .msi file to import the application's artifacts, including all of their data, into an application in another BizTalk group.</span></span> <span data-ttu-id="c37e6-119">此外可以使用此.msi 文件的计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="c37e6-119">You can also use this .msi file to install the application on a computer.</span></span>  
  
## <a name="exporting-a-policy"></a><span data-ttu-id="c37e6-120">导出策略</span><span class="sxs-lookup"><span data-stu-id="c37e6-120">Exporting a policy</span></span>  
 <span data-ttu-id="c37e6-121">当你使用管理控制台导出的 BizTalk 组或应用程序策略时，会生成包含策略信息的.xml 策略文件。</span><span class="sxs-lookup"><span data-stu-id="c37e6-121">When you use the administration console to export a policy for either a BizTalk group or application, it generates an .xml policy file containing the policy information.</span></span> <span data-ttu-id="c37e6-122">您可以导入此策略文件到另一个 BizTalk 组中创建的策略，以便组中的应用程序可以使用它。</span><span class="sxs-lookup"><span data-stu-id="c37e6-122">You can import this policy file into another BizTalk group to create the policy there, so that applications in the group can use it.</span></span> <span data-ttu-id="c37e6-123">此外可以通过使用 BTSTask 导出应用程序的策略信息。</span><span class="sxs-lookup"><span data-stu-id="c37e6-123">You can also export policy information for an application by using BTSTask.</span></span> <span data-ttu-id="c37e6-124">BTSTask，但是，没有要导出策略.xml 文件的命令。</span><span class="sxs-lookup"><span data-stu-id="c37e6-124">BTSTask, however, does not have a command to export a policy .xml file.</span></span> <span data-ttu-id="c37e6-125">相反，您可以导出只包含该策略的应用程序.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="c37e6-125">Instead, you can export an application .msi file that contains only the policy.</span></span> <span data-ttu-id="c37e6-126">您然后可以导入另一个组中的应用程序的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="c37e6-126">You can then import the .msi file into an application in another group.</span></span>  
  
## <a name="exporting-bindings"></a><span data-ttu-id="c37e6-127">导出绑定</span><span class="sxs-lookup"><span data-stu-id="c37e6-127">Exporting bindings</span></span>  
 <span data-ttu-id="c37e6-128">可以使用管理控制台或 BTSTask 导出 BizTalk 组、 应用程序或程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="c37e6-128">You can use either the administration console or BTSTask to export bindings for a BizTalk group, application, or assembly.</span></span> <span data-ttu-id="c37e6-129">当执行此操作时，BizTalk Server 将生成包含组、 应用程序或程序集的绑定信息的.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="c37e6-129">When you do this, BizTalk Server generates an .xml file containing the binding information for the group, application, or assembly.</span></span> <span data-ttu-id="c37e6-130">在导出绑定时，还可以导出全局参与方的组的信息。</span><span class="sxs-lookup"><span data-stu-id="c37e6-130">When you export bindings, you can also export global party information for the group.</span></span> <span data-ttu-id="c37e6-131">然后，您可以将此绑定文件添加到应用程序或将其导入 BizTalk 组或应用程序。</span><span class="sxs-lookup"><span data-stu-id="c37e6-131">You can then either add this binding file to an application or import it into a BizTalk group or application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37e6-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c37e6-132">See Also</span></span>  
 <span data-ttu-id="c37e6-133">[对项目采取的应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="c37e6-133">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="c37e6-134">[导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="c37e6-134">[Exporting BizTalk Applications, Bindings, and Policies](../core/exporting-biztalk-applications-bindings-and-policies.md) </span></span>  
 <span data-ttu-id="c37e6-135">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="c37e6-135">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="c37e6-136">如何将绑定文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="c37e6-136">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)