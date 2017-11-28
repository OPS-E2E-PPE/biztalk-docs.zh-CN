---
title: "部署应用程序的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09970e43bd53306a6394eeffc4c2e642a8333dbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-deploying-an-application"></a><span data-ttu-id="5cd31-102">部署应用程序的已知的问题</span><span class="sxs-lookup"><span data-stu-id="5cd31-102">Known Issues with Deploying an Application</span></span>
## <a name="deploying-a-biztalk-application"></a><span data-ttu-id="5cd31-103">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5cd31-103">Deploying a BizTalk Application</span></span>  
 <span data-ttu-id="5cd31-104">**部署更新的应用程序需要更正的引用**</span><span class="sxs-lookup"><span data-stu-id="5cd31-104">**Deploying an updated application requires correcting references**</span></span>  
  
 <span data-ttu-id="5cd31-105">如果要部署一个全新的应用程序以替换现有的应用程序，必须更正其他应用程序与要替换的应用程序之间的所有引用。</span><span class="sxs-lookup"><span data-stu-id="5cd31-105">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
 <span data-ttu-id="5cd31-106">**使用 Visual Studio 部署应用程序可以停止应用程序**</span><span class="sxs-lookup"><span data-stu-id="5cd31-106">**Using Visual Studio to deploy an application can stop applications**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cd31-107">我们建议你避免使用 Visual Studio 部署到生产环境的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5cd31-107">We recommend that you avoid using Visual Studio to deploy an application into a production environment.</span></span>  
  
 <span data-ttu-id="5cd31-108">如果你使用 Visual Studio 部署到生产环境的应用程序并且重新启动主机实例选项部署应用程序，包括那些不与相关联时，则设置为 True 在项目属性中，所有主机实例将重新启动此应用程序。</span><span class="sxs-lookup"><span data-stu-id="5cd31-108">If you use Visual Studio to deploy an application into a production environment and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="5cd31-109">这样会停止在本地计算机的任何主机实例上运行的所有其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="5cd31-109">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a><span data-ttu-id="5cd31-110">将项目添加到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5cd31-110">Adding Artifacts to a BizTalk Application</span></span>  
 <span data-ttu-id="5cd31-111">**移动项目可以移动依赖关系**</span><span class="sxs-lookup"><span data-stu-id="5cd31-111">**Moving an artifact can move dependencies**</span></span>  
  
 <span data-ttu-id="5cd31-112">当你将项目移到新的应用程序时，它在其具有依赖关系的任何其他项目也被移动，除非新的应用程序具有对包含已移动的项目取决于项目的应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="5cd31-112">When you move an artifact to a new application, any other artifacts on which it has dependencies are also moved unless the new application has a reference to the application(s) containing the artifacts that the moved artifact depends upon.</span></span> <span data-ttu-id="5cd31-113">同样，与移动项目有依存关系的所有项目也会被移动，除非包含这些项目的应用程序具有对新应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="5cd31-113">Also, any artifacts that have dependencies on the moved artifact also will be moved unless the application(s) containing them have a reference to the new application.</span></span> <span data-ttu-id="5cd31-114">移动项目时，系统会显示一起移动的其他项目的列表。</span><span class="sxs-lookup"><span data-stu-id="5cd31-114">When moving an artifact, you will be shown the list of other artifacts that will also be moved.</span></span> <span data-ttu-id="5cd31-115">有关移动项目的说明，请参阅[如何将项目移到不同的应用程序](http://go.microsoft.com/fwlink/?LinkId=154999)(http://go.microsoft.com/fwlink/?LinkId=154999)。</span><span class="sxs-lookup"><span data-stu-id="5cd31-115">For instructions on moving an artifact, see [How to Move an Artifact to a Different Application](http://go.microsoft.com/fwlink/?LinkId=154999) (http://go.microsoft.com/fwlink/?LinkId=154999).</span></span>  
  
## <a name="exporting-a-biztalk-application"></a><span data-ttu-id="5cd31-116">导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5cd31-116">Exporting a BizTalk Application</span></span>  
 <span data-ttu-id="5cd31-117">**安装 Windows Vista 上的.msi 文件时，可以显示不正确错误**</span><span class="sxs-lookup"><span data-stu-id="5cd31-117">**An incorrect error can be displayed when installing an .msi file on Windows Vista**</span></span>  
  
 <span data-ttu-id="5cd31-118">当安装.msi 程序包导出使用[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]上[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Windows Vista® 上运行，你可能会收到以下不正确的错误，"安装程序遇到意外的错误安装此包。</span><span class="sxs-lookup"><span data-stu-id="5cd31-118">When installing an .msi package exported using [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] on [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] running on Windows Vista®, you may receive the following incorrect error, "The installer has encountered an unexpected error installing this package.</span></span> <span data-ttu-id="5cd31-119">这可能表示此程序包有问题。</span><span class="sxs-lookup"><span data-stu-id="5cd31-119">This may indicate a problem with this package.</span></span> <span data-ttu-id="5cd31-120">错误代码为 2869。”</span><span class="sxs-lookup"><span data-stu-id="5cd31-120">The error code is 2869."</span></span> <span data-ttu-id="5cd31-121">若要更正此错误，首次导入包使用[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]和重新导出和安装该程序包。</span><span class="sxs-lookup"><span data-stu-id="5cd31-121">To correct this error, first import the package using [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and then re-export and install the package.</span></span>  
  
## <a name="importing-a-biztalk-application"></a><span data-ttu-id="5cd31-122">导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5cd31-122">Importing a BizTalk Application</span></span>  
 <span data-ttu-id="5cd31-123">**密码不会从绑定添加到应用程序的文件**</span><span class="sxs-lookup"><span data-stu-id="5cd31-123">**Passwords are not removed from binding files added to an application**</span></span>  
  
 <span data-ttu-id="5cd31-124">为安全起见，在导出应用程序的过程中，密码从应用程序绑定中删除。</span><span class="sxs-lookup"><span data-stu-id="5cd31-124">For security reasons, during application export, passwords are removed from application bindings.</span></span> <span data-ttu-id="5cd31-125">不过，密码并未从已添加到应用程序的绑定文件中删除。</span><span class="sxs-lookup"><span data-stu-id="5cd31-125">They are not, however, removed from any binding files that were added to the application.</span></span> <span data-ttu-id="5cd31-126">在导入应用程序后，您需要重新配置密码，以便应用程序可以正常运行。</span><span class="sxs-lookup"><span data-stu-id="5cd31-126">After importing the application, you will need to reconfigure the passwords in order for the application to function.</span></span> <span data-ttu-id="5cd31-127">可以通过编辑绑定文件或通过使用管理控制台执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5cd31-127">You can do this by editing the binding file or by using the Administration console.</span></span> <span data-ttu-id="5cd31-128">有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkId=155000)(http://go.microsoft.com/fwlink/?LinkId=155000)。</span><span class="sxs-lookup"><span data-stu-id="5cd31-128">For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkId=155000) (http://go.microsoft.com/fwlink/?LinkId=155000).</span></span> <span data-ttu-id="5cd31-129">有关配置的适配器的安全性的详细信息，请参阅[使用适配器](http://go.microsoft.com/fwlink/?LinkId=155001)(http://go.microsoft.com/fwlink/?LinkId=155001)。</span><span class="sxs-lookup"><span data-stu-id="5cd31-129">For more information about configuring security for adapters, see [Using Adapters](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001).</span></span>  
  
 <span data-ttu-id="5cd31-130">**BizTalk Server 不会回滚已编写脚本的导入或安装**</span><span class="sxs-lookup"><span data-stu-id="5cd31-130">**BizTalk Server does not roll back scripted imports or installs**</span></span>  
  
 <span data-ttu-id="5cd31-131">如果导入失败，则 BizTalk Server 将回滚所有导入操作（自定义脚本执行的所有操作除外）。</span><span class="sxs-lookup"><span data-stu-id="5cd31-131">If an import fails, BizTalk Server rolls back all import operations except for any actions performed by custom scripts.</span></span> <span data-ttu-id="5cd31-132">这也是如此安装和卸载操作。</span><span class="sxs-lookup"><span data-stu-id="5cd31-132">This is also true for install and uninstall operations.</span></span>  
  
 <span data-ttu-id="5cd31-133">**缺失的架构可能不会报告导入后**</span><span class="sxs-lookup"><span data-stu-id="5cd31-133">**A missing schema might not be reported after an import**</span></span>  
  
 <span data-ttu-id="5cd31-134">如果您在一个应用程序中为发送端口创建了筛选器，此应用程序使用另一个应用程序中的属性架构，然后将第一个应用程序导入到新 BizTalk 组中，则您将收到缺少架构的警告，并且在安装和启动该应用程序时筛选功能将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="5cd31-134">If you create a filter for a send port in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="5cd31-135">解决这个问题的方法是：先导入包含该架构的应用程序，然后再安装不包含该架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5cd31-135">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd31-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cd31-136">See Also</span></span>  
 [<span data-ttu-id="5cd31-137">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="5cd31-137">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)