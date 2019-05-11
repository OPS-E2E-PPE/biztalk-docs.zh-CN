---
title: 管理架构 |Microsoft Docs
description: 使用 BizTalk 管理可以使用在 BizTalk Server 中，包括显示和隐藏属性架构，查看其 XSD，启用跟踪
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5632e79-b182-41c9-9138-eb88b44e3172
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c39d6bd414a1f9558e058881c41f6dd9bd1e5d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531139"
---
# <a name="manage-schemas"></a><span data-ttu-id="fae7d-103">管理架构</span><span class="sxs-lookup"><span data-stu-id="fae7d-103">Manage Schemas</span></span>

## <a name="overiew"></a><span data-ttu-id="fae7d-104">概述</span><span class="sxs-lookup"><span data-stu-id="fae7d-104">Overiew</span></span>
<span data-ttu-id="fae7d-105">本部分说明了使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来管理架构。</span><span class="sxs-lookup"><span data-stu-id="fae7d-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage schemas.</span></span> <span data-ttu-id="fae7d-106">管道和业务流程使用架构来表示将处理的消息。</span><span class="sxs-lookup"><span data-stu-id="fae7d-106">Schemas are used by pipelines and orchestrations to represent the message that will be processed.</span></span>  
  
 <span data-ttu-id="fae7d-107">在创建架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="fae7d-107">Schemas are created in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="fae7d-108">不能单独; 将架构添加到应用程序架构添加到应用程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fae7d-108">You cannot add a schema to an application individually; a schema is added to an application as follows:</span></span>  
  
- <span data-ttu-id="fae7d-109">当添加包含到应用程序，架构的 BizTalk 程序集，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="fae7d-109">When you add a BizTalk assembly containing a schema to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="fae7d-110">某一.msi 文件导入包含 BizTalk 程序集包含架构，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="fae7d-110">When you import an .msi file into an application that includes a BizTalk assembly containing a schema, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="fae7d-111">当开发人员部署到应用程序包含来自的架构的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="fae7d-111">When a developer deploys into an application an assembly containing a schema from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="fae7d-112">有关架构的背景信息，请参阅[架构](../core/schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="fae7d-112">For background information about schemas, see [Schemas](../core/schemas.md).</span></span> <span data-ttu-id="fae7d-113">有关开发架构的信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="fae7d-113">For information about developing schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fae7d-114">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="fae7d-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="fae7d-115">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="fae7d-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="fae7d-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fae7d-116">Next steps</span></span> 
  
-   [<span data-ttu-id="fae7d-117">显示和隐藏属性架构</span><span class="sxs-lookup"><span data-stu-id="fae7d-117">Show and Hide Property Schemas</span></span>](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [<span data-ttu-id="fae7d-118">查看某一架构的架构定义 (XSD)</span><span class="sxs-lookup"><span data-stu-id="fae7d-118">View the Schema Definition (XSD) of a Schema</span></span>](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [<span data-ttu-id="fae7d-119">为架构配置跟踪</span><span class="sxs-lookup"><span data-stu-id="fae7d-119">Configure Tracking for a Schema</span></span>](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [<span data-ttu-id="fae7d-120">从应用程序中删除架构</span><span class="sxs-lookup"><span data-stu-id="fae7d-120">Remove a Schema from an Application</span></span>](../core/how-to-remove-a-schema-from-an-application.md)