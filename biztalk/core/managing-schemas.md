---
title: 管理架构 |Microsoft 文档
description: 使用 BizTalk 管理可以使用架构在 BizTalk Server 中，包括显示和隐藏属性，查看 XSD，启用跟踪
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
ms.openlocfilehash: f0d7fe3eee97cf81c668ffe90fd9c0897af23cc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262597"
---
# <a name="manage-schemas"></a><span data-ttu-id="0507b-103">管理架构</span><span class="sxs-lookup"><span data-stu-id="0507b-103">Manage Schemas</span></span>

## <a name="overiew"></a><span data-ttu-id="0507b-104">概述</span><span class="sxs-lookup"><span data-stu-id="0507b-104">Overiew</span></span>
<span data-ttu-id="0507b-105">本部分介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来管理架构。</span><span class="sxs-lookup"><span data-stu-id="0507b-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage schemas.</span></span> <span data-ttu-id="0507b-106">架构通过管道和业务流程中用于表示将处理的消息。</span><span class="sxs-lookup"><span data-stu-id="0507b-106">Schemas are used by pipelines and orchestrations to represent the message that will be processed.</span></span>  
  
 <span data-ttu-id="0507b-107">在中创建架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和编译到 BizTalk 程序集中。</span><span class="sxs-lookup"><span data-stu-id="0507b-107">Schemas are created in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="0507b-108">不能单独; 将架构添加到应用程序架构添加到应用程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0507b-108">You cannot add a schema to an application individually; a schema is added to an application as follows:</span></span>  
  
-   <span data-ttu-id="0507b-109">当你添加 BizTalk 程序集包含应用程序，架构中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0507b-109">When you add a BizTalk assembly containing a schema to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="0507b-110">当你导入的应用程序中所述包括 BizTalk 程序集包含架构，.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0507b-110">When you import an .msi file into an application that includes a BizTalk assembly containing a schema, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="0507b-111">当开发人员将部署到应用程序包含来自的架构的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中所述，[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0507b-111">When a developer deploys into an application an assembly containing a schema from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="0507b-112">有关架构的背景信息，请参阅[架构](../core/schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="0507b-112">For background information about schemas, see [Schemas](../core/schemas.md).</span></span> <span data-ttu-id="0507b-113">有关开发架构的信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="0507b-113">For information about developing schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0507b-114">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="0507b-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="0507b-115">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="0507b-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0507b-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0507b-116">Next steps</span></span> 
  
-   [<span data-ttu-id="0507b-117">显示和隐藏属性架构</span><span class="sxs-lookup"><span data-stu-id="0507b-117">Show and Hide Property Schemas</span></span>](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [<span data-ttu-id="0507b-118">查看架构的架构定义 (XSD)</span><span class="sxs-lookup"><span data-stu-id="0507b-118">View the Schema Definition (XSD) of a Schema</span></span>](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [<span data-ttu-id="0507b-119">配置架构的跟踪</span><span class="sxs-lookup"><span data-stu-id="0507b-119">Configure Tracking for a Schema</span></span>](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [<span data-ttu-id="0507b-120">从应用程序中删除架构</span><span class="sxs-lookup"><span data-stu-id="0507b-120">Remove a Schema from an Application</span></span>](../core/how-to-remove-a-schema-from-an-application.md)