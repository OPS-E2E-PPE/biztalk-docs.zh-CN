---
title: "导入 BizTalk 应用程序、 绑定和策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing, applications
- importing, policies
- applications, importing
- policies, importing
- importing, bindings
- bindings, importing
ms.assetid: 678bdb03-efaa-4053-9048-b71fc539d191
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18f7ea348fb34f4f8cc08e748799dcf8368a3c35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="40824-102">导入 BizTalk 应用程序、 绑定和策略</span><span class="sxs-lookup"><span data-stu-id="40824-102">Importing BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="40824-103">本部分中的主题介绍如何将 BizTalk 应用程序、绑定和策略导入到 BizTalk 组或应用程序。</span><span class="sxs-lookup"><span data-stu-id="40824-103">The topics in this section describe how to import BizTalk applications, bindings and policies into a BizTalk group or application.</span></span> <span data-ttu-id="40824-104">中所述[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)，导出应用程序创建 Windows Installer (.msi) 文件，然后，可以使用，以将应用程序的项目导入到不同的 BizTalk 组中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="40824-104">As mentioned in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md), exporting an application creates a Windows Installer (.msi) file that you can then use to import the application's artifacts into an application in a different BizTalk group.</span></span> <span data-ttu-id="40824-105">如果为导入指定的应用程序在组中不存在，则创建该应用程序。</span><span class="sxs-lookup"><span data-stu-id="40824-105">If the application that you specify for the import does not already exist in the group, the application is created.</span></span> <span data-ttu-id="40824-106">此外，注册应用程序的项目，并将其数据存储于该组的 BizTalk Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="40824-106">In addition, application's artifacts are registered and their data stored in the BizTalk databases of the group.</span></span> <span data-ttu-id="40824-107">有关详细信息，请参阅[什么发生时项目导入](../core/what-happens-when-artifacts-are-imported.md)。</span><span class="sxs-lookup"><span data-stu-id="40824-107">For more information, see [What Happens When Artifacts Are Imported](../core/what-happens-when-artifacts-are-imported.md).</span></span>  
  
 <span data-ttu-id="40824-108">你还可以导入到 BizTalk 组或应用程序从 BizTalk 组、 应用程序或程序集，导出的绑定中所述[导出绑定](../core/exporting-bindings6.md)。</span><span class="sxs-lookup"><span data-stu-id="40824-108">You can also import into a BizTalk group or application the bindings that you exported from a BizTalk group, application, or assembly, as described in [Exporting Bindings](../core/exporting-bindings6.md).</span></span> <span data-ttu-id="40824-109">导入绑定时，它们将覆盖 BizTalk 组、应用程序或程序集中任何同名的绑定。</span><span class="sxs-lookup"><span data-stu-id="40824-109">When you import bindings, they overwrite any bindings of the same name in the BizTalk group, application, or assembly.</span></span>  
  
 <span data-ttu-id="40824-110">此外，你可以导入策略到 BizTalk 组或应用程序，从导出的 BizTalk 组中所述[如何导出策略](../core/how-to-export-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="40824-110">In addition, you can import a policy into a BizTalk group that you exported from a BizTalk group or application, as described in [How to Export a Policy](../core/how-to-export-a-policy.md).</span></span> <span data-ttu-id="40824-111">然后，新组中的应用程序可以使用该策略。</span><span class="sxs-lookup"><span data-stu-id="40824-111">Applications in the new group can then use the policy.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40824-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="40824-112">In This Section</span></span>  
  
-   [<span data-ttu-id="40824-113">如何导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="40824-113">How to Import a BizTalk Application</span></span>](../core/how-to-import-a-biztalk-application.md)  
  
-   [<span data-ttu-id="40824-114">导入绑定</span><span class="sxs-lookup"><span data-stu-id="40824-114">Importing Bindings</span></span>](../core/importing-bindings2.md)  
  
-   [<span data-ttu-id="40824-115">如何导入策略</span><span class="sxs-lookup"><span data-stu-id="40824-115">How to Import a Policy</span></span>](../core/how-to-import-a-policy.md)