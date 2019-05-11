---
title: 中的应用程序或组必须是唯一的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, artifacts
- artifacts, requirements
- applications, artifacts
ms.assetid: a758cd74-a962-4e75-aea2-47752ab72a64
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dc28a438dff5e2fe21dc00d207da64fbdd2fc69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359256"
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a><span data-ttu-id="54cc4-102">中的应用程序或组必须是唯一的项目</span><span class="sxs-lookup"><span data-stu-id="54cc4-102">Artifacts That Must Be Unique in an Application or Group</span></span>
<span data-ttu-id="54cc4-103">某些类型的 BizTalk 组或应用程序中的项目必须唯一，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="54cc4-103">Certain types of artifacts in a BizTalk group or application must be unique, as follows:</span></span>  
  
- <span data-ttu-id="54cc4-104">在组中，BizTalk 程序集和非 BizTalk.NET 程序集必须具有唯一的全名。</span><span class="sxs-lookup"><span data-stu-id="54cc4-104">Both BizTalk assemblies and non-BizTalk .NET assemblies must have a unique full name in the group.</span></span> <span data-ttu-id="54cc4-105">全名包括文件名、 公钥标记、 区域性和版本。</span><span class="sxs-lookup"><span data-stu-id="54cc4-105">The full name consists of a file name, public key token, culture, and version.</span></span>  
  
- <span data-ttu-id="54cc4-106">规则和策略必须具有唯一的名称和版本编号的组中。</span><span class="sxs-lookup"><span data-stu-id="54cc4-106">Rules and policies must have a unique name and version number in the group.</span></span>  
  
- <span data-ttu-id="54cc4-107">发送端口、 发送端口组、 接收端口和接收位置必须具有在组中唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="54cc4-107">Send ports, send port groups, receive ports, and receive locations must have a unique name in the group.</span></span>  
  
- <span data-ttu-id="54cc4-108">网站必须在组中具有唯一的虚拟目录名称。</span><span class="sxs-lookup"><span data-stu-id="54cc4-108">Web sites must have a unique virtual directory name in the group.</span></span>  
  
- <span data-ttu-id="54cc4-109">在组中，BAM 资源必须具有唯一的文件名。</span><span class="sxs-lookup"><span data-stu-id="54cc4-109">BAM resources must have a unique file name in the group.</span></span>  
  
- <span data-ttu-id="54cc4-110">在组中，证书必须具有唯一的指纹。</span><span class="sxs-lookup"><span data-stu-id="54cc4-110">Certificates must have a unique thumbprint in the group.</span></span>  
  
- <span data-ttu-id="54cc4-111">COM 组件必须在组中具有唯一的文件名。</span><span class="sxs-lookup"><span data-stu-id="54cc4-111">COM components must have a unique file name in the group.</span></span>  
  
- <span data-ttu-id="54cc4-112">在应用程序，但不是在组中，基于文件的项目，如脚本和其他平面文件，必须具有唯一的文件名称。</span><span class="sxs-lookup"><span data-stu-id="54cc4-112">File-based artifacts, such as scripts and other flat files, must have unique file names in the application, but not in the group.</span></span>  
  
  <span data-ttu-id="54cc4-113">可以指定覆盖选项导入或将项目添加到应用程序，如果应用程序中已存在该项目并且它必须是唯一的应用程序中的类型。</span><span class="sxs-lookup"><span data-stu-id="54cc4-113">You can specify the overwrite option to import or add an artifact to an application if the artifact already exists in the application and it is of a type that must be unique in an application.</span></span> <span data-ttu-id="54cc4-114">如果项目已存在的组中，另一个应用程序中，并且它是类型必须是唯一的组中，您不能添加或导入它。</span><span class="sxs-lookup"><span data-stu-id="54cc4-114">If the artifact already exists in another application in the group, and it is a type that must be unique in the group, you can neither add nor import it.</span></span>  
  
  <span data-ttu-id="54cc4-115">如果您需要使用一个应用程序中的项目，并且它已存在于组中的另一个应用程序，可以创建对包含该项目的应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="54cc4-115">If you need to use an artifact in one application and it already exists in another application in the group, you can create a reference to the application containing the artifact.</span></span> <span data-ttu-id="54cc4-116">有关详细信息请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="54cc4-116">For more information see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54cc4-117">您可以查看大多数类型的项目的完整名称的应用程序中使用 BTSTask，ListApp 命令中所述[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="54cc4-117">You can view the full name of most types of artifacts in an application by using the ListApp command of BTSTask, as described in [ListApp Command](../core/listapp-command.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54cc4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="54cc4-118">See Also</span></span>  
 [<span data-ttu-id="54cc4-119">了解 BizTalk 应用程序的部署和管理</span><span class="sxs-lookup"><span data-stu-id="54cc4-119">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)