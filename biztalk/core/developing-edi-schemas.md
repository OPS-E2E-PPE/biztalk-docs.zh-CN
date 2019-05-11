---
title: 开发 EDI 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a8fbf3d-ebc7-47f6-87fa-e45722651262
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c87b3bd95fa6a58837a377b1454cdb6963312e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351064"
---
# <a name="developing-edi-schemas"></a><span data-ttu-id="43cc6-102">开发 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="43cc6-102">Developing EDI Schemas</span></span>
<span data-ttu-id="43cc6-103">在本部分中的主题介绍如何修改 EDI 架构以用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="43cc6-103">The topics in this section describe how to modify EDI Schemas for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="43cc6-104">若要在解决方案中使用文档架构，需要将其添加到的 BizTalk 项目中部署架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后生成并部署项目。</span><span class="sxs-lookup"><span data-stu-id="43cc6-104">To use a document schema in your solution, you need to deploy the schema by adding it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and then building and deploying the project.</span></span> [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="43cc6-105">将部署默认 BizTalk 应用程序 1 中的项目。</span><span class="sxs-lookup"><span data-stu-id="43cc6-105">will deploy the project in the default BizTalk Application 1.</span></span> <span data-ttu-id="43cc6-106">您可以看到通过打开部署的架构**架构**节点下的**BizTalk Application 1**节点**应用程序**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="43cc6-106">You can see the schemas that are deployed by opening the **Schemas** node under **BizTalk Application 1** node the **Applications** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="43cc6-107">可以通过使用命令行部署工具部署到不同的应用程序的程序集`BTSTask`。</span><span class="sxs-lookup"><span data-stu-id="43cc6-107">You can deploy an assembly into a different application by using the command-line deployment tool `BTSTask`.</span></span>  
  
 <span data-ttu-id="43cc6-108">会自动部署服务和控制架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导。</span><span class="sxs-lookup"><span data-stu-id="43cc6-108">The service and control schemas are automatically deployed by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration wizard.</span></span> <span data-ttu-id="43cc6-109">若要查看它们，请单击**架构**中的节点**BizTalk EDI 应用程序**在管理控制台中的节点。</span><span class="sxs-lookup"><span data-stu-id="43cc6-109">To see them, click the **Schemas** node in the **BizTalk EDI Application** node in the Administration Console.</span></span> <span data-ttu-id="43cc6-110">有关这些架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="43cc6-110">For more information about these schemas, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43cc6-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="43cc6-111">In This Section</span></span>  
  
-   [<span data-ttu-id="43cc6-112">修改 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="43cc6-112">Modifying EDI Schemas</span></span>](../core/modifying-edi-schemas.md)  
  
-   [<span data-ttu-id="43cc6-113">在信封架构中自定义枚举</span><span class="sxs-lookup"><span data-stu-id="43cc6-113">Customizing Enumerations in the Envelope Schema</span></span>](../core/customizing-enumerations-in-the-envelope-schema.md)  
  
-   [<span data-ttu-id="43cc6-114">配置跨字段验证</span><span class="sxs-lookup"><span data-stu-id="43cc6-114">Configuring Cross-Field Validation</span></span>](../core/configuring-cross-field-validation.md)  
  
## <a name="see-also"></a><span data-ttu-id="43cc6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="43cc6-115">See Also</span></span>  
 [<span data-ttu-id="43cc6-116">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="43cc6-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)