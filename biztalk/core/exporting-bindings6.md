---
title: 导出 Bindings6 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- exporting, bindings
ms.assetid: 052a429e-3237-44d4-8933-00aa5edfb212
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee3d7df759dab97dca6a2e7677abb0bad15f8cd7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022875"
---
# <a name="exporting-bindings"></a><span data-ttu-id="6ea29-102">导出绑定</span><span class="sxs-lookup"><span data-stu-id="6ea29-102">Exporting Bindings</span></span>
<span data-ttu-id="6ea29-103">在本部分中的主题介绍如何导出 BizTalk 组、 程序集或到.xml 文件的应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="6ea29-103">The topics in this section describe how to export bindings for a BizTalk group, assembly, or application into an .xml file.</span></span> <span data-ttu-id="6ea29-104">(绑定定义如何主机、 发送端口、 发送端口组、 接收端口、 接收位置，参与方是与业务流程、 管道、 映射和架构相关联。)你可以然后绑定导入从.xml 文件到另一个组或应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ea29-104">(Bindings define how hosts, send ports, send port groups, receive ports, receive locations, parties are associated with orchestrations, pipelines, maps, and schemas.) You can then import the bindings from the .xml file into another group or application.</span></span> <span data-ttu-id="6ea29-105">导入绑定将覆盖所有现有组或应用程序中具有相同名称的绑定。</span><span class="sxs-lookup"><span data-stu-id="6ea29-105">Importing bindings overwrites any existing bindings of the same name in the group or application.</span></span> <span data-ttu-id="6ea29-106">此外可以将绑定添加到应用程序，不会覆盖现有绑定。</span><span class="sxs-lookup"><span data-stu-id="6ea29-106">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="6ea29-107">导入应用程序添加的绑定会生效。</span><span class="sxs-lookup"><span data-stu-id="6ea29-107">The bindings that you add do not take effect until you import the application.</span></span>  
  
 <span data-ttu-id="6ea29-108">您可能会发现，使用绑定文件加快了应用程序部署在以下情况下通过无需手动配置绑定：</span><span class="sxs-lookup"><span data-stu-id="6ea29-108">You may find that using binding files speeds application deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
- <span data-ttu-id="6ea29-109">在一个部署环境之间移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ea29-109">Moving an application from one deployment environment to another.</span></span>  
  
- <span data-ttu-id="6ea29-110">更新的程序集。</span><span class="sxs-lookup"><span data-stu-id="6ea29-110">Updating an assembly.</span></span>  
  
- <span data-ttu-id="6ea29-111">将程序集以及及其绑定部署到多个 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="6ea29-111">Deploying an assembly together with its bindings to multiple BizTalk groups.</span></span>  
  
  <span data-ttu-id="6ea29-112">有关用于这些目的使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea29-112">For more information about using binding files for these purposes, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
  <span data-ttu-id="6ea29-113">有关导入和添加绑定的详细信息，请参阅[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)，和[如何添加绑定向应用程序文件](../core/how-to-add-a-binding-file-to-an-application2.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea29-113">For more information about importing and adding bindings, see [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md), [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md), and [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ea29-114">绑定文件可能包含敏感数据。</span><span class="sxs-lookup"><span data-stu-id="6ea29-114">The binding file may contain sensitive data.</span></span> <span data-ttu-id="6ea29-115">请务必采取措施来保护文件。</span><span class="sxs-lookup"><span data-stu-id="6ea29-115">Be sure to take steps to secure the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ea29-116">出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="6ea29-116">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="6ea29-117">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="6ea29-117">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="6ea29-118">您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。</span><span class="sxs-lookup"><span data-stu-id="6ea29-118">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="6ea29-119">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea29-119">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="6ea29-120">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea29-120">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ea29-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="6ea29-121">In This Section</span></span>  
  
-   [<span data-ttu-id="6ea29-122">如何导出 BizTalk 组的绑定</span><span class="sxs-lookup"><span data-stu-id="6ea29-122">How to Export Bindings for a BizTalk Group</span></span>](../core/how-to-export-bindings-for-a-biztalk-group.md)  
  
-   [<span data-ttu-id="6ea29-123">如何导出 BizTalk 应用程序的绑定</span><span class="sxs-lookup"><span data-stu-id="6ea29-123">How to Export Bindings for a BizTalk Application</span></span>](../core/how-to-export-bindings-for-a-biztalk-application.md)  
  
-   [<span data-ttu-id="6ea29-124">如何导出 BizTalk 程序集的绑定</span><span class="sxs-lookup"><span data-stu-id="6ea29-124">How to Export Bindings for a BizTalk Assembly</span></span>](../core/how-to-export-bindings-for-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="6ea29-125">如何导出 EDI-AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="6ea29-125">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)