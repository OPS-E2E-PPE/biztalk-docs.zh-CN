---
title: 管理 BAM 定义文件所需的用户权限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb4fb73f-b783-4a04-9bd6-a135b3dd2655
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e12997684bb934e4e5f2891046afe07c749b2a70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267666"
---
# <a name="required-user-rights-for-managing-bam-definition-files"></a><span data-ttu-id="2e62d-102">管理 BAM 定义文件所需的用户权限</span><span class="sxs-lookup"><span data-stu-id="2e62d-102">Required User Rights for Managing BAM Definition Files</span></span>
<span data-ttu-id="2e62d-103">任何角色的用户均可以创建、管理和查看 BAM 定义文件。</span><span class="sxs-lookup"><span data-stu-id="2e62d-103">BAM definition files can be created, managed, and viewed by users in any role.</span></span> <span data-ttu-id="2e62d-104">管理 BAM 定义文件包括部署和删除这些文件，以及管理与定义文件相关联的活动、视图、警报和项目。</span><span class="sxs-lookup"><span data-stu-id="2e62d-104">Managing BAM definition files includes deploying and removing them as well as managing the activities, views, alerts, and artifacts that are associated with the definition file.</span></span>  
  
 <span data-ttu-id="2e62d-105">管理员应采取适当的资产保护措施，如创建具有相应访问权限的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e62d-105">Administrators should maintain proper asset protection, such as creating shared folders with appropriate access permissions.</span></span> <span data-ttu-id="2e62d-106">使用 Excel BAM 外接程序时，我们建议用户将宏安全级别设置为高。</span><span class="sxs-lookup"><span data-stu-id="2e62d-106">When using the BAM Add-In for Excel, we recommend that users set the macro security level to high.</span></span>  
  
 <span data-ttu-id="2e62d-107">虽然原则上任何用户都可以修改 BAM 定义文件，但具体要取决于对存储定义文件的位置所设置的权限。</span><span class="sxs-lookup"><span data-stu-id="2e62d-107">There are no required user rights needed to modify the BAM definition files (depending on permissions set on where the definition files are stored).</span></span> <span data-ttu-id="2e62d-108">对定义文件所做的更改不会自动应用到 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="2e62d-108">Changes to definition files are not automatically applied to the BAM infrastructure.</span></span> <span data-ttu-id="2e62d-109">若要应用这些更改，必须使用 BAM 管理实用程序。</span><span class="sxs-lookup"><span data-stu-id="2e62d-109">To apply the changes you must use the BAM Management utility.</span></span>  
  
 <span data-ttu-id="2e62d-110">若要使用 BAM 管理实用程序，您必须是 BAM 定义要应用到的计算机的管理员或 BizTalk Server Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="2e62d-110">To use the BAM Management utility, you must be an administrator on the computer to which the BAM definition is being applied or a member of the BizTalk Server Administrators group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e62d-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="2e62d-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e62d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e62d-112">See Also</span></span>  
 <span data-ttu-id="2e62d-113">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="2e62d-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="2e62d-114">[BAM 定义是什么？](../core/what-is-a-bam-definition.md) </span><span class="sxs-lookup"><span data-stu-id="2e62d-114">[What Is a BAM Definition?](../core/what-is-a-bam-definition.md) </span></span>  
 [<span data-ttu-id="2e62d-115">如何部署 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="2e62d-115">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)