---
title: 管理映射 |Microsoft Docs
description: 若要使用 BizTalk Server，其中包括查看和删除映射中的映射的链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e8e3057-5a9f-4b6b-b6ee-c71b7e6a51ac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a00e4abf979b7e52cd649c8ef663af22016967bc
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531098"
---
# <a name="manage-maps"></a><span data-ttu-id="7fb11-103">管理映射</span><span class="sxs-lookup"><span data-stu-id="7fb11-103">Manage Maps</span></span>

## <a name="overview"></a><span data-ttu-id="7fb11-104">概述</span><span class="sxs-lookup"><span data-stu-id="7fb11-104">Overview</span></span>
<span data-ttu-id="7fb11-105">本部分说明了使用 BizTalk Server 管理控制台来管理映射。</span><span class="sxs-lookup"><span data-stu-id="7fb11-105">This section provides instructions on managing maps by using the BizTalk Server Administration console.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7fb11-106">使用映射转换的记录和记录的一个架构中的字段和另一个架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="7fb11-106">uses maps to translate the records and fields in one schema to the records and fields in another schema.</span></span> <span data-ttu-id="7fb11-107">映射可能由业务流程，发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7fb11-107">Maps may be used by orchestrations, send ports, and receive ports.</span></span>  

## <a name="add-maps-to-an-application"></a><span data-ttu-id="7fb11-108">将地图添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="7fb11-108">Add maps to an application</span></span>  
 <span data-ttu-id="7fb11-109">映射内置的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="7fb11-109">Maps are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="7fb11-110">不能单独; 将映射添加到应用程序映射添加到应用程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7fb11-110">You cannot add a map to an application individually; a map is added to an application as follows:</span></span>  
  
- <span data-ttu-id="7fb11-111">添加 BizTalk 程序集包含映射到该应用程序，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb11-111">When you add a BizTalk assembly containing a map to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="7fb11-112">某一.msi 文件导入包含其中包含的映射的 BizTalk 程序集，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb11-112">When you import an .msi file into an application that includes a BizTalk assembly containing a map, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="7fb11-113">当开发人员部署到应用程序包含从映射的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb11-113">When a developer deploys into an application an assembly containing a map from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="7fb11-114">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb11-114">For background information about maps, see [Maps](../core/maps.md).</span></span> <span data-ttu-id="7fb11-115">有关创建映射的信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb11-115">For information about creating maps, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fb11-116">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="7fb11-116">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="7fb11-117">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="7fb11-117">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="7fb11-118">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7fb11-118">Next steps</span></span> 
  
-   [<span data-ttu-id="7fb11-119">查看应用程序映射</span><span class="sxs-lookup"><span data-stu-id="7fb11-119">View the Maps for an Application</span></span>](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [<span data-ttu-id="7fb11-120">从应用程序中删除映射</span><span class="sxs-lookup"><span data-stu-id="7fb11-120">Remove a Map from an Application</span></span>](../core/how-to-remove-a-map-from-an-application.md)