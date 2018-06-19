---
title: 如何导出为.msi 文件的应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7179e86-aa55-426b-a0db-19229ca5625a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600118718585401d9ba6c3158b6510af55c53e74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297765"
---
# <a name="how-to-export-an-application-to-an-msi-file"></a><span data-ttu-id="cded9-102">如何导出为.msi 文件的应用程序</span><span class="sxs-lookup"><span data-stu-id="cded9-102">How to Export an Application to an .msi File</span></span>
<span data-ttu-id="cded9-103">可以使用导出 MSI 文件向导或 BTSTask 将导出到.msi 文件将用于将应用程序导入新的 BizTalk 组的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="cded9-103">You can use the Export MSI File Wizard or BTSTask to export the application artifacts into an .msi file that you will use to import the application into a new BizTalk group.</span></span> <span data-ttu-id="cded9-104">此过程还会将运行它的计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="cded9-104">This process will also install the application on the computers that will run it.</span></span>  
  
## <a name="exporting-application-bindings-in-an-msi-file"></a><span data-ttu-id="cded9-105">导出程序.msi 文件中的应用程序绑定</span><span class="sxs-lookup"><span data-stu-id="cded9-105">Exporting Application Bindings in an .msi File</span></span>  
 <span data-ttu-id="cded9-106">在导出到.msi 文件的应用程序时，你选择要导出哪些资源。</span><span class="sxs-lookup"><span data-stu-id="cded9-106">When you export an application into an .msi file, you select which resources to export.</span></span> <span data-ttu-id="cded9-107">这些资源可以包括所有数据或已部署的程序集的子集或绑定所提供的导出。</span><span class="sxs-lookup"><span data-stu-id="cded9-107">These resources can include all or a subset of the deployed assemblies or bindings that are available for export.</span></span>  
  
 <span data-ttu-id="cded9-108">若要更加轻松地恢复到你的开发环境的应用程序导入一次更高版本进行更改或添加内容，你可能想要导出每个应用程序的绑定，然后将其添加回应用程序。</span><span class="sxs-lookup"><span data-stu-id="cded9-108">To make it easier to import the applications back into your development environment at a later time to make changes or additions, you may want to export the bindings for each application and then add them back into the applications.</span></span> <span data-ttu-id="cded9-109">当设置为"BiztalkBinding"的资源类型时，你可以将其他绑定文件添加到.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="cded9-109">When you set the Resource type to "BiztalkBinding," you can add additional binding files to an .msi file.</span></span> <span data-ttu-id="cded9-110">对于你添加每个绑定文件，必须指定绑定应该应用到的环境名称 （文本字段）。</span><span class="sxs-lookup"><span data-stu-id="cded9-110">For each binding file that you add, you must specify the environment name (text field) that the bindings should be applied to.</span></span> <span data-ttu-id="cded9-111">然后在导入时，你将需要选择目前导环境名称。</span><span class="sxs-lookup"><span data-stu-id="cded9-111">Then on import, you will be asked to select the environment name to which you are presently importing.</span></span> <span data-ttu-id="cded9-112">如果这些内容匹配，则绑定文件将应用到目标组。</span><span class="sxs-lookup"><span data-stu-id="cded9-112">If these match, then the binding file is applied to the target group.</span></span> <span data-ttu-id="cded9-113">你还可以指定添加的绑定文件，这将导致绑定无条件地应用于所有环境的集没有环境名称。</span><span class="sxs-lookup"><span data-stu-id="cded9-113">You can also specify no environment name for the added binding file, which will cause the set of bindings to be applied to all environments unconditionally.</span></span>  
  
 <span data-ttu-id="cded9-114">使用.msi 文件自动执行什么可以否则大设置的手动任务。</span><span class="sxs-lookup"><span data-stu-id="cded9-114">Using an .msi file automates what can otherwise be a substantial set of manual tasks.</span></span> <span data-ttu-id="cded9-115">在生产环境中，你可以更加轻松地部署到多个 BizTalk 组程序集的传输以及程序集的程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="cded9-115">In a production environment, you can make it easier to deploy an assembly into multiple BizTalk groups by transporting the bindings for the assembly along with the assembly.</span></span> <span data-ttu-id="cded9-116">如果你的应用程序包含大量的项目，你可以将某些项目导出到一个 Windows Installer 包和某些为一个或多个其他 Windows Installer 包。</span><span class="sxs-lookup"><span data-stu-id="cded9-116">If your application contains a significant number of artifacts, you can export some of the artifacts into one Windows Installer package and some into one or more other Windows Installer packages.</span></span>  
  
 <span data-ttu-id="cded9-117">导出应用程序，时应考虑一些要点。</span><span class="sxs-lookup"><span data-stu-id="cded9-117">While exporting the application, you should consider some important points.</span></span> <span data-ttu-id="cded9-118">例如，您可能会将导出所有应用程序中的项目或你想要添加或更新项目。</span><span class="sxs-lookup"><span data-stu-id="cded9-118">For example, you may either export all of the artifacts in the application or only the artifacts that you want to add or update.</span></span> <span data-ttu-id="cded9-119">如果导出文件项目，请确保它是你想要在应用程序中使用的版本。</span><span class="sxs-lookup"><span data-stu-id="cded9-119">If you export a file artifact, make sure that it is the version that you want to use in the application.</span></span> <span data-ttu-id="cded9-120">多这样的点以及有关导出到.msi 文件 BizTalk 应用程序的详细信息，请参阅[how to Export BizTalk 应用程序如何](http://go.microsoft.com/fwlink/?LinkID=154848)(http://go.microsoft.com/fwlink/?LinkID=154848)。</span><span class="sxs-lookup"><span data-stu-id="cded9-120">For more such points and for more information about exporting a BizTalk application into an .msi file, see [How to Export a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154848) (http://go.microsoft.com/fwlink/?LinkID=154848).</span></span>