---
title: "导出 Bindings6 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- exporting, bindings
ms.assetid: 052a429e-3237-44d4-8933-00aa5edfb212
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362984eca1dcec4fb68bfbac92c30da81de8a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exporting-bindings"></a><span data-ttu-id="27c15-102">导出绑定</span><span class="sxs-lookup"><span data-stu-id="27c15-102">Exporting Bindings</span></span>
<span data-ttu-id="27c15-103">本部分中的主题介绍如何导出 BizTalk 组、 程序集，或到一个.xml 文件的应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="27c15-103">The topics in this section describe how to export bindings for a BizTalk group, assembly, or application into an .xml file.</span></span> <span data-ttu-id="27c15-104">(绑定定义主机，发送端口将端口组的发送、 接收端口，则接收位置，各方都与业务流程、 管道、 映射和架构相关联。)您然后可以从.xml 文件到另一个组或应用程序来导入绑定。</span><span class="sxs-lookup"><span data-stu-id="27c15-104">(Bindings define how hosts, send ports, send port groups, receive ports, receive locations, parties are associated with orchestrations, pipelines, maps, and schemas.) You can then import the bindings from the .xml file into another group or application.</span></span> <span data-ttu-id="27c15-105">导入绑定将覆盖任何现有组或应用程序中的相同名称的绑定。</span><span class="sxs-lookup"><span data-stu-id="27c15-105">Importing bindings overwrites any existing bindings of the same name in the group or application.</span></span> <span data-ttu-id="27c15-106">你还可以向应用程序，不会覆盖现有绑定添加绑定。</span><span class="sxs-lookup"><span data-stu-id="27c15-106">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="27c15-107">在导入应用程序之前，你添加的绑定不会生效。</span><span class="sxs-lookup"><span data-stu-id="27c15-107">The bindings that you add do not take effect until you import the application.</span></span>  
  
 <span data-ttu-id="27c15-108">你可能会发现，使用绑定文件加快了应用程序部署在下列情况中通过避免需要手动配置绑定：</span><span class="sxs-lookup"><span data-stu-id="27c15-108">You may find that using binding files speeds application deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
-   <span data-ttu-id="27c15-109">将应用程序从一种部署环境移到另一个。</span><span class="sxs-lookup"><span data-stu-id="27c15-109">Moving an application from one deployment environment to another.</span></span>  
  
-   <span data-ttu-id="27c15-110">更新程序集。</span><span class="sxs-lookup"><span data-stu-id="27c15-110">Updating an assembly.</span></span>  
  
-   <span data-ttu-id="27c15-111">将其绑定以及程序集部署到多个 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="27c15-111">Deploying an assembly together with its bindings to multiple BizTalk groups.</span></span>  
  
 <span data-ttu-id="27c15-112">有关针对这些目的使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="27c15-112">For more information about using binding files for these purposes, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
 <span data-ttu-id="27c15-113">有关导入和添加绑定的详细信息，请参阅[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，[如何导入绑定到 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)，和[如何将绑定添加向应用程序的文件](../core/how-to-add-a-binding-file-to-an-application2.md)。</span><span class="sxs-lookup"><span data-stu-id="27c15-113">For more information about importing and adding bindings, see [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md), [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md), and [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27c15-114">绑定文件可能包含敏感数据。</span><span class="sxs-lookup"><span data-stu-id="27c15-114">The binding file may contain sensitive data.</span></span> <span data-ttu-id="27c15-115">请确保采取措施来保护文件。</span><span class="sxs-lookup"><span data-stu-id="27c15-115">Be sure to take steps to secure the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27c15-116">出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="27c15-116">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="27c15-117">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="27c15-117">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="27c15-118">您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。</span><span class="sxs-lookup"><span data-stu-id="27c15-118">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="27c15-119">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="27c15-119">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="27c15-120">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="27c15-120">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27c15-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="27c15-121">In This Section</span></span>  
  
-   [<span data-ttu-id="27c15-122">如何导出绑定 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="27c15-122">How to Export Bindings for a BizTalk Group</span></span>](../core/how-to-export-bindings-for-a-biztalk-group.md)  
  
-   [<span data-ttu-id="27c15-123">如何导出 BizTalk 应用程序的绑定</span><span class="sxs-lookup"><span data-stu-id="27c15-123">How to Export Bindings for a BizTalk Application</span></span>](../core/how-to-export-bindings-for-a-biztalk-application.md)  
  
-   [<span data-ttu-id="27c15-124">如何导出 BizTalk 程序集绑定</span><span class="sxs-lookup"><span data-stu-id="27c15-124">How to Export Bindings for a BizTalk Assembly</span></span>](../core/how-to-export-bindings-for-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="27c15-125">如何导出 EDI AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="27c15-125">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)