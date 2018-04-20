---
title: 更新应用程序中的绑定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4d30296a2bb81b3685793884010f02eb950828
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="updating-the-bindings-in-an-application"></a><span data-ttu-id="d9a5f-102">更新应用程序中的绑定</span><span class="sxs-lookup"><span data-stu-id="d9a5f-102">Updating the Bindings in an Application</span></span>
<span data-ttu-id="d9a5f-103">在更新应用程序中的一个程序集时，通常会覆盖该程序集的绑定，也有可能该程序集根本未绑定，所以您不得不手动重新配置绑定。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-103">When you update an assembly in an application, its bindings are often overwritten or else the assembly may not be bound at all, forcing you to manually reconfigure bindings.</span></span> <span data-ttu-id="d9a5f-104">要避免此问题，可以使用绑定文件若要更新的程序集的相同版本或更新的程序集的较新版本。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-104">To avoid this, you can use a binding file to update the same version of the assembly or update an assembly with a newer version.</span></span>  
  
## <a name="updating-the-same-version-of-an-assembly"></a><span data-ttu-id="d9a5f-105">更新相同版本的程序集</span><span class="sxs-lookup"><span data-stu-id="d9a5f-105">Updating the Same Version of an Assembly</span></span>  
 <span data-ttu-id="d9a5f-106">如果程序集具有早期绑定端口或动态端口，而您在 BizTalk Server 管理控制台中更改了端口配置，在您使用相同版本号的程序集来更新当前程序集时这些设置将丢失。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-106">If the assembly has early bound ports or dynamic ports, and you changed the port configuration in the BizTalk Server Administration console, the settings will be lost when you update the assembly with an assembly having the same version number.</span></span> <span data-ttu-id="d9a5f-107">你可以为你要更新的程序集导出绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-107">You can export a binding file for the assembly that you are going to update.</span></span> <span data-ttu-id="d9a5f-108">在更新后的程序集，可以导入应用程序的程序集，然后将其绑定文件以重新应用上一绑定导入。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-108">After updating the assembly, you can import the assembly into the application and then import its binding file to reapply the previous bindings.</span></span>  
  
## <a name="updating-an-assembly-with-a-newer-version"></a><span data-ttu-id="d9a5f-109">更新的较新版本的程序集</span><span class="sxs-lookup"><span data-stu-id="d9a5f-109">Updating an Assembly with a Newer Version</span></span>  
 <span data-ttu-id="d9a5f-110">你可以通过导出与绑定文件到单个程序集关联的绑定、 绑定和编辑文件以反映新的程序集版本，然后将程序集绑定到应用程序导入更新的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-110">You can update the version of an assembly by exporting the binding associated with a single assembly into a binding file, editing the binding file to reflect a new assembly version, and then importing the bindings of the assembly into the application.</span></span> <span data-ttu-id="d9a5f-111">有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkID=155000)(超链接"http://go.microsoft.com/fwlink/?LinkID=155000"http://go.microsoft.com/fwlink/?LinkID=155000)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="d9a5f-111">For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkID=155000) ( HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=155000" http://go.microsoft.com/fwlink/?LinkID=155000) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>