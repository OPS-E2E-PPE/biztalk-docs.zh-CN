---
title: 导入 BizTalk 应用程序、 绑定和策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing, applications
- importing, policies
- applications, importing
- policies, importing
- importing, bindings
- bindings, importing
ms.assetid: 678bdb03-efaa-4053-9048-b71fc539d191
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7891d36e922f49efd8a5ce4f8986fcad8aa162aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382510"
---
# <a name="importing-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="bf25d-102">导入 BizTalk 应用程序、 绑定和策略</span><span class="sxs-lookup"><span data-stu-id="bf25d-102">Importing BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="bf25d-103">在本部分中的主题介绍如何将 BizTalk 应用程序、 绑定和策略导入 BizTalk 组或应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf25d-103">The topics in this section describe how to import BizTalk applications, bindings and policies into a BizTalk group or application.</span></span> <span data-ttu-id="bf25d-104">如中所述[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)，导出应用程序创建 Windows Installer (.msi) 文件，您可以使用它将应用程序的项目导入其他 BizTalk 组中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf25d-104">As mentioned in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md), exporting an application creates a Windows Installer (.msi) file that you can then use to import the application's artifacts into an application in a different BizTalk group.</span></span> <span data-ttu-id="bf25d-105">如果组中不存在指定为导入的应用程序，创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf25d-105">If the application that you specify for the import does not already exist in the group, the application is created.</span></span> <span data-ttu-id="bf25d-106">此外，注册应用程序的项目，并且其数据存储在组的 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="bf25d-106">In addition, application's artifacts are registered and their data stored in the BizTalk databases of the group.</span></span> <span data-ttu-id="bf25d-107">有关详细信息，请参阅[什么发生时导入项目](../core/what-happens-when-artifacts-are-imported.md)。</span><span class="sxs-lookup"><span data-stu-id="bf25d-107">For more information, see [What Happens When Artifacts Are Imported](../core/what-happens-when-artifacts-are-imported.md).</span></span>  
  
 <span data-ttu-id="bf25d-108">您还可以导入到 BizTalk 组或应用程序从 BizTalk 组、 应用程序或程序集，导出的绑定中所述[导出绑定](../core/exporting-bindings6.md)。</span><span class="sxs-lookup"><span data-stu-id="bf25d-108">You can also import into a BizTalk group or application the bindings that you exported from a BizTalk group, application, or assembly, as described in [Exporting Bindings](../core/exporting-bindings6.md).</span></span> <span data-ttu-id="bf25d-109">当您导入绑定时，它们将覆盖中 BizTalk 组、 应用程序或程序集具有相同名称的任何绑定。</span><span class="sxs-lookup"><span data-stu-id="bf25d-109">When you import bindings, they overwrite any bindings of the same name in the BizTalk group, application, or assembly.</span></span>  
  
 <span data-ttu-id="bf25d-110">此外，您可以将策略导入 BizTalk 组或应用程序中，从导出的 BizTalk 组中所述[如何导出策略](../core/how-to-export-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="bf25d-110">In addition, you can import a policy into a BizTalk group that you exported from a BizTalk group or application, as described in [How to Export a Policy](../core/how-to-export-a-policy.md).</span></span> <span data-ttu-id="bf25d-111">在新组中的应用程序然后可以使用该策略。</span><span class="sxs-lookup"><span data-stu-id="bf25d-111">Applications in the new group can then use the policy.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf25d-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="bf25d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="bf25d-113">如何导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="bf25d-113">How to Import a BizTalk Application</span></span>](../core/how-to-import-a-biztalk-application.md)  
  
-   [<span data-ttu-id="bf25d-114">导入绑定</span><span class="sxs-lookup"><span data-stu-id="bf25d-114">Importing Bindings</span></span>](../core/importing-bindings2.md)  
  
-   [<span data-ttu-id="bf25d-115">如何导入策略</span><span class="sxs-lookup"><span data-stu-id="bf25d-115">How to Import a Policy</span></span>](../core/how-to-import-a-policy.md)