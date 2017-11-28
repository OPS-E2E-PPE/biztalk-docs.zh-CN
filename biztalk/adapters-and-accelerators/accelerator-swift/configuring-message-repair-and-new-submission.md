---
title: "配置消息修复和新提交 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, configuring
- A4SWIFT, Message Repair and New Submission
- configuring, Message Repair and New Submission
ms.assetid: e3e5e865-109c-469e-8b5b-c2675583d5a5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00e42bcfc5e744aa005e2e0a790dfc505b7a834d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-message-repair-and-new-submission"></a><span data-ttu-id="31a27-102">配置消息修复和新的提交</span><span class="sxs-lookup"><span data-stu-id="31a27-102">Configuring Message Repair and New Submission</span></span>
<span data-ttu-id="31a27-103">以下各节中，若要配置的消息修复和新提交功能，必须执行步骤[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]下, 图中所示。</span><span class="sxs-lookup"><span data-stu-id="31a27-103">You must perform the steps in the following sections to configure the Message Repair and New Submission feature of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], as shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")  
  
 <span data-ttu-id="31a27-104">在 A4SWIFT 安装向导中，你可以选择安装消息修复和新的提交和 FIN 响应对帐 (FRR) 或消息修复和新的提交，而无需 FRR 或如果没有消息修复和新提交 FRR。</span><span class="sxs-lookup"><span data-stu-id="31a27-104">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FIN Response Reconciliation (FRR), or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="31a27-105">因此，本部分中的说明进行操作不会假定安装和配置 FRR。</span><span class="sxs-lookup"><span data-stu-id="31a27-105">As a result, the instructions in this section do not assume that you are installing and configuring FRR.</span></span> <span data-ttu-id="31a27-106">它们，但是，假定你已执行中的步骤[A4SWIFT 组件配置指南](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md)部分。</span><span class="sxs-lookup"><span data-stu-id="31a27-106">They do, however, assume that you have performed the steps in the [A4SWIFT Component Configuration Guide](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md) section.</span></span>  
  
 <span data-ttu-id="31a27-107">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="31a27-107">This section contains:</span></span>  
  
-   [<span data-ttu-id="31a27-108">安装证书</span><span class="sxs-lookup"><span data-stu-id="31a27-108">Installing Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)  
  
-   [<span data-ttu-id="31a27-109">设置 A4SWIFT 属性</span><span class="sxs-lookup"><span data-stu-id="31a27-109">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)  
  
-   [<span data-ttu-id="31a27-110">添加 A4SWIFT 用户和更新 Windows 组</span><span class="sxs-lookup"><span data-stu-id="31a27-110">Adding A4SWIFT Users and Updating Windows Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-a4swift-users-and-updating-windows-groups.md)  
  
-   [<span data-ttu-id="31a27-111">添加角色和部门</span><span class="sxs-lookup"><span data-stu-id="31a27-111">Adding Roles and Departments</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-roles-and-departments.md)  
  
-   [<span data-ttu-id="31a27-112">部署 A4SWIFT 信封架构</span><span class="sxs-lookup"><span data-stu-id="31a27-112">Deploying A4SWIFT Envelope Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-envelope-schemas.md)  
  
-   [<span data-ttu-id="31a27-113">发布 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="31a27-113">Publishing InfoPath Form Templates</span></span>](http://msdn.microsoft.com/en-us/2947e1ad-8c44-4cdb-bbde-7683e186b41b)