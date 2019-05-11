---
title: 创建应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e93e3feacf3e8243fc6871fe3f18c17aa9ccba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305988"
---
# <a name="creating-an-application"></a><span data-ttu-id="34026-102">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="34026-102">Creating an Application</span></span>
<span data-ttu-id="34026-103">有三种方法来创建 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="34026-103">There are three ways to create a BizTalk application.</span></span> <span data-ttu-id="34026-104">也有几个选项为命名、 引用，并将项目部署到应用程序。</span><span class="sxs-lookup"><span data-stu-id="34026-104">There are also several options for naming, referencing, and deploying artifacts to applications.</span></span>  
  
## <a name="creating-a-biztalk-application"></a><span data-ttu-id="34026-105">创建 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="34026-105">Creating a BizTalk Application</span></span>  
 <span data-ttu-id="34026-106">通过三种方式是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="34026-106">The three ways are as follows:</span></span>  
  
1. <span data-ttu-id="34026-107">使用 BizTalk Server 管理控制台的新的应用程序命令或 BTSTask 命令行工具的 AddApp 命令创建的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="34026-107">Create the BizTalk application by using the New Application command of the BizTalk Server Administration console or the AddApp command of the BTSTask command-line tool.</span></span> <span data-ttu-id="34026-108">有关使用这些命令的详细信息，请参阅[如何创建应用程序](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。</span><span class="sxs-lookup"><span data-stu-id="34026-108">For more information about using these commands, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
2. <span data-ttu-id="34026-109">导入从另一个应用程序导出的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="34026-109">Import an .msi file that was exported from another application.</span></span> <span data-ttu-id="34026-110">如果当前的 BizTalk 组中不存在该应用程序，包括其项目的应用程序是自动创建当前 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="34026-110">If the application does not already exist in the current BizTalk group, the application, including its artifacts, is automatically created in the current BizTalk group.</span></span> <span data-ttu-id="34026-111">有关导入应用程序的详细信息，请参阅[导入 BizTalk 应用程序的方式](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。</span><span class="sxs-lookup"><span data-stu-id="34026-111">For more information about importing applications, see [How to Import a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).</span></span>  
  
3. <span data-ttu-id="34026-112">部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="34026-112">Deploy BizTalk assemblies from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="34026-113">如果 Visual Studio 中的项目的部署属性中指定的应用程序不存在当前的 BizTalk 组中，它将自动创建。</span><span class="sxs-lookup"><span data-stu-id="34026-113">If the application specified in the deployment properties for a project in Visual Studio does not exist in the current BizTalk group, it will be automatically created.</span></span> <span data-ttu-id="34026-114">部署 Visual Studio 中的程序集的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。</span><span class="sxs-lookup"><span data-stu-id="34026-114">For more information about deploying an assembly from Visual Studio, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>  
  
   <span data-ttu-id="34026-115">若要部署使用某一.msi 文件的应用程序，该目标应用程序不需要存在，但将自动创建。</span><span class="sxs-lookup"><span data-stu-id="34026-115">To deploy an application using an .msi file, the destination application does not need to exist, but will be automatically created.</span></span> <span data-ttu-id="34026-116">但是，若要导入绑定到另一个应用程序中，目标应用程序必须已存在。</span><span class="sxs-lookup"><span data-stu-id="34026-116">However, to import bindings from one application to another, the destination application must already exist.</span></span> <span data-ttu-id="34026-117">如果没有，您需要通过执行上面列出的过程之一来创建。</span><span class="sxs-lookup"><span data-stu-id="34026-117">If not, you need to create it by performing one of the procedures listed above.</span></span>  
  
   <span data-ttu-id="34026-118">有关创建应用程序所需的特定步骤的详细信息，请参阅[如何创建应用程序](http://go.microsoft.com/fwlink/?LinkId=155007)(http://go.microsoft.com/fwlink/?LinkId=155007)。</span><span class="sxs-lookup"><span data-stu-id="34026-118">For more information about the specific steps required to create an application, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
## <a name="application-options"></a><span data-ttu-id="34026-119">应用程序选项</span><span class="sxs-lookup"><span data-stu-id="34026-119">Application Options</span></span>  
 <span data-ttu-id="34026-120">在创建新的应用程序之前, 应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34026-120">Before creating a new application, you should do the following:</span></span>  
  
-   <span data-ttu-id="34026-121">确定在应用程序的 BizTalk 组中是唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="34026-121">Determine a name that is unique within the BizTalk group for the application.</span></span>  
  
-   <span data-ttu-id="34026-122">添加新应用程序中对任何应用程序包含你想要在新的应用程序中重复使用的项目的引用。</span><span class="sxs-lookup"><span data-stu-id="34026-122">Add a reference from the new application to any application containing artifacts that you want to reuse in the new application.</span></span> <span data-ttu-id="34026-123">有关应用程序之间的依赖关系的详细信息，请参阅[依赖项和应用程序部署](http://go.microsoft.com/fwlink/?LinkId=155008)(http://go.microsoft.com/fwlink/?LinkId=155008)。</span><span class="sxs-lookup"><span data-stu-id="34026-123">For more information about dependencies between applications, see [Dependencies and Application Deployment](http://go.microsoft.com/fwlink/?LinkId=155008) (http://go.microsoft.com/fwlink/?LinkId=155008).</span></span>  
  
-   <span data-ttu-id="34026-124">确定您是否要将某些项目部署到单独的应用程序，例如，应部署到其自己单独的应用程序的共享项目。</span><span class="sxs-lookup"><span data-stu-id="34026-124">Determine whether you want to deploy some artifacts into separate applications, for example, shared artifacts that should be deployed into their own separate application.</span></span>