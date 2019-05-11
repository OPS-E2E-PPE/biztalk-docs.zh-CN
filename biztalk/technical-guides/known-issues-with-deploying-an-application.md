---
title: 部署应用程序的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4bc6f54ad0ce3c355d8d6aad9a09e24387ec7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395823"
---
# <a name="known-issues-with-deploying-an-application"></a><span data-ttu-id="86d71-102">部署应用程序的已知的问题</span><span class="sxs-lookup"><span data-stu-id="86d71-102">Known Issues with Deploying an Application</span></span>
## <a name="deploying-a-biztalk-application"></a><span data-ttu-id="86d71-103">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="86d71-103">Deploying a BizTalk Application</span></span>  
 <span data-ttu-id="86d71-104">**部署更新的应用程序需要更正的引用**</span><span class="sxs-lookup"><span data-stu-id="86d71-104">**Deploying an updated application requires correcting references**</span></span>  
  
 <span data-ttu-id="86d71-105">如果部署全新的应用程序以替换现有应用程序，你必须更正其他应用程序以及要替换的应用程序之间的所有引用。</span><span class="sxs-lookup"><span data-stu-id="86d71-105">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
 <span data-ttu-id="86d71-106">**使用 Visual Studio 部署应用程序，可以停止应用程序**</span><span class="sxs-lookup"><span data-stu-id="86d71-106">**Using Visual Studio to deploy an application can stop applications**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86d71-107">我们建议您避免使用 Visual Studio 部署到生产环境的应用程序。</span><span class="sxs-lookup"><span data-stu-id="86d71-107">We recommend that you avoid using Visual Studio to deploy an application into a production environment.</span></span>  
  
 <span data-ttu-id="86d71-108">如果你使用 Visual Studio 部署到生产环境的应用程序并重新启动主机实例选项设置为在项目属性中，所有主机实例，则返回 True 部署包括那些不与相关联的应用程序时将重新启动此应用程序。</span><span class="sxs-lookup"><span data-stu-id="86d71-108">If you use Visual Studio to deploy an application into a production environment and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="86d71-109">这将停止所有本地计算机上的任何主机实例运行其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="86d71-109">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a><span data-ttu-id="86d71-110">将项目添加到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="86d71-110">Adding Artifacts to a BizTalk Application</span></span>  
 <span data-ttu-id="86d71-111">**移动项目可以移动的依赖项**</span><span class="sxs-lookup"><span data-stu-id="86d71-111">**Moving an artifact can move dependencies**</span></span>  
  
 <span data-ttu-id="86d71-112">当将项目移到新的应用程序时，它在其具有依赖关系的任何其他项目也被移动，除非新的应用程序具有对包含取决于移动的项目的项目的应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="86d71-112">When you move an artifact to a new application, any other artifacts on which it has dependencies are also moved unless the new application has a reference to the application(s) containing the artifacts that the moved artifact depends upon.</span></span> <span data-ttu-id="86d71-113">此外，移动项目有依赖关系的任何项目也将被移动，除非其包含的应用程序具有对新应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="86d71-113">Also, any artifacts that have dependencies on the moved artifact also will be moved unless the application(s) containing them have a reference to the new application.</span></span> <span data-ttu-id="86d71-114">当移动项目，将向您显示一起移动的其他项目的列表。</span><span class="sxs-lookup"><span data-stu-id="86d71-114">When moving an artifact, you will be shown the list of other artifacts that will also be moved.</span></span> <span data-ttu-id="86d71-115">有关移动项目的说明，请参阅[如何将项目移到不同的应用程序](http://go.microsoft.com/fwlink/?LinkId=154999)(http://go.microsoft.com/fwlink/?LinkId=154999)。</span><span class="sxs-lookup"><span data-stu-id="86d71-115">For instructions on moving an artifact, see [How to Move an Artifact to a Different Application](http://go.microsoft.com/fwlink/?LinkId=154999) (http://go.microsoft.com/fwlink/?LinkId=154999).</span></span>  
  
## <a name="exporting-a-biztalk-application"></a><span data-ttu-id="86d71-116">导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="86d71-116">Exporting a BizTalk Application</span></span>  
 <span data-ttu-id="86d71-117">**安装 Windows Vista 上的.msi 文件时，可以显示不正确错误**</span><span class="sxs-lookup"><span data-stu-id="86d71-117">**An incorrect error can be displayed when installing an .msi file on Windows Vista**</span></span>  
  
 <span data-ttu-id="86d71-118">当使用安装.msi 程序包导出[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]Windows Vista® 上运行的 BizTalk Server，可能会收到以下错误，"安装程序遇到意外的错误安装此包。</span><span class="sxs-lookup"><span data-stu-id="86d71-118">When installing an .msi package exported using [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] on BizTalk Server running on Windows Vista®, you may receive the following incorrect error, "The installer has encountered an unexpected error installing this package.</span></span> <span data-ttu-id="86d71-119">这可能表示此软件包存在问题。</span><span class="sxs-lookup"><span data-stu-id="86d71-119">This may indicate a problem with this package.</span></span> <span data-ttu-id="86d71-120">错误代码为 2869年。"</span><span class="sxs-lookup"><span data-stu-id="86d71-120">The error code is 2869."</span></span> <span data-ttu-id="86d71-121">若要更正此错误，首先使用 BizTalk Server 将包导入然后重新导出并安装包。</span><span class="sxs-lookup"><span data-stu-id="86d71-121">To correct this error, first import the package using BizTalk Server and then re-export and install the package.</span></span>  
  
## <a name="importing-a-biztalk-application"></a><span data-ttu-id="86d71-122">导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="86d71-122">Importing a BizTalk Application</span></span>  
 <span data-ttu-id="86d71-123">**密码不会从绑定文件添加到应用程序**</span><span class="sxs-lookup"><span data-stu-id="86d71-123">**Passwords are not removed from binding files added to an application**</span></span>  
  
 <span data-ttu-id="86d71-124">出于安全原因，在应用程序导出过程中不会保留密码从应用程序绑定。</span><span class="sxs-lookup"><span data-stu-id="86d71-124">For security reasons, during application export, passwords are removed from application bindings.</span></span> <span data-ttu-id="86d71-125">它们不会但是，删除从绑定文件已添加到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="86d71-125">They are not, however, removed from any binding files that were added to the application.</span></span> <span data-ttu-id="86d71-126">在导入应用程序之后, 将需要重新配置密码，以便对函数应用程序。</span><span class="sxs-lookup"><span data-stu-id="86d71-126">After importing the application, you will need to reconfigure the passwords in order for the application to function.</span></span> <span data-ttu-id="86d71-127">可以通过编辑绑定文件或使用管理控制台执行此操作。</span><span class="sxs-lookup"><span data-stu-id="86d71-127">You can do this by editing the binding file or by using the Administration console.</span></span> <span data-ttu-id="86d71-128">有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkId=155000)(http://go.microsoft.com/fwlink/?LinkId=155000)。</span><span class="sxs-lookup"><span data-stu-id="86d71-128">For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkId=155000) (http://go.microsoft.com/fwlink/?LinkId=155000).</span></span> <span data-ttu-id="86d71-129">有关配置适配器的安全性的详细信息，请参阅[使用适配器](http://go.microsoft.com/fwlink/?LinkId=155001)(http://go.microsoft.com/fwlink/?LinkId=155001)。</span><span class="sxs-lookup"><span data-stu-id="86d71-129">For more information about configuring security for adapters, see [Using Adapters](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001).</span></span>  
  
 <span data-ttu-id="86d71-130">**BizTalk Server 不会回滚已编写脚本的导入或安装**</span><span class="sxs-lookup"><span data-stu-id="86d71-130">**BizTalk Server does not roll back scripted imports or installs**</span></span>  
  
 <span data-ttu-id="86d71-131">如果导入失败，BizTalk Server 将回滚所有导入操作除外自定义脚本执行的任何操作。</span><span class="sxs-lookup"><span data-stu-id="86d71-131">If an import fails, BizTalk Server rolls back all import operations except for any actions performed by custom scripts.</span></span> <span data-ttu-id="86d71-132">这也是如此的安装和卸载操作。</span><span class="sxs-lookup"><span data-stu-id="86d71-132">This is also true for install and uninstall operations.</span></span>  
  
 <span data-ttu-id="86d71-133">**缺少架构可能不会导入后报告**</span><span class="sxs-lookup"><span data-stu-id="86d71-133">**A missing schema might not be reported after an import**</span></span>  
  
 <span data-ttu-id="86d71-134">如果一个应用程序在另一个应用程序中使用的属性架构中创建的发送端口的筛选器，然后将第一个应用程序导入新的 BizTalk 组，不会收到的警告，该架构缺少，并且筛选功能将不正常时安装和启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="86d71-134">If you create a filter for a send port in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="86d71-135">可以通过导入包含架构，然后再安装不包含架构的应用程序的应用程序来更正此问题。</span><span class="sxs-lookup"><span data-stu-id="86d71-135">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d71-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="86d71-136">See Also</span></span>  
 [<span data-ttu-id="86d71-137">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="86d71-137">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)