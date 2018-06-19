---
title: 创建或编辑过程配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process configuration, modifying
- process configuration, creating
- creating, process configuration
- modifying, process configuration
ms.assetid: 39cc2c93-0986-48d3-8c6f-4280ec9af4e0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9130ab7370f8f6e1fcbe75bc7a85a6c74dfe328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207117"
---
# <a name="creating-or-editing-a-process-configuration"></a><span data-ttu-id="34a9b-102">创建或编辑过程配置</span><span class="sxs-lookup"><span data-stu-id="34a9b-102">Creating or Editing a Process Configuration</span></span>
<span data-ttu-id="34a9b-103">本部分介绍如何创建或编辑过程配置以实现在合作伙伴接口过程 (PIP) [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34a9b-103">This section describes how to create or edit a process configuration to implement a Partner Interface Process (PIP) in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="34a9b-104">RosettaNet PIP 定义了两个贸易合作伙伴间的业务流程对话。</span><span class="sxs-lookup"><span data-stu-id="34a9b-104">A RosettaNet PIP defines a business-process dialog between two trading partners.</span></span> <span data-ttu-id="34a9b-105">在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，若要创建 PIP 与合作伙伴，你必须首先创建过程配置。</span><span class="sxs-lookup"><span data-stu-id="34a9b-105">In [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], to create a PIP with a partner, you must first create a process configuration.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="34a9b-106">使用此配置文件来存储所有配置特征的 PIP。</span><span class="sxs-lookup"><span data-stu-id="34a9b-106"> uses this profile to store all configuration characteristics of the PIP.</span></span> <span data-ttu-id="34a9b-107">然后，您可以使用此配置创建与合作伙伴的协议。</span><span class="sxs-lookup"><span data-stu-id="34a9b-107">You can then use this configuration to create an agreement with the partner.</span></span>  
  
 <span data-ttu-id="34a9b-108">进程配置属性和创建或编辑过程配置的过程的信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="34a9b-108">For information about process configuration properties, and procedures for creating or editing a process configuration, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="34a9b-109">在创建新的流程配置过程中，必须基于 PIP 规范文档的设置，该文档由 RosettaNet 组织进行维护。</span><span class="sxs-lookup"><span data-stu-id="34a9b-109">In creating a new process configuration, you must base the settings on the PIP specification document maintained by the RosettaNet organization.</span></span> <span data-ttu-id="34a9b-110">所有的流程配置设置都来自于 PIP 规范，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 用默认值填充了大多数的设置，这些值是这些字段最常用的值。</span><span class="sxs-lookup"><span data-stu-id="34a9b-110">All process configuration settings come from the PIP specifications, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] populates most of the settings with default values that are the most typically used values for the fields.</span></span> <span data-ttu-id="34a9b-111">您必须检验这些设置与相应的 PIP 规范中的值是否相符。</span><span class="sxs-lookup"><span data-stu-id="34a9b-111">You must verify that the settings correspond to the values in the appropriate PIP specification.</span></span> <span data-ttu-id="34a9b-112">有关您输入的 PIP 设置如何映射到 PIP 规范中的指南的详细信息，请参阅[使用 PIP 规范创建过程配置](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="34a9b-112">For more information about how the PIP settings that you enter map to the guidance in the PIP specification, see [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="34a9b-113">流程配置可用于 RosettaNet 或 CIDX（化工行业数据交换）。</span><span class="sxs-lookup"><span data-stu-id="34a9b-113">The process configuration can be for either RosettaNet or CIDX (Chemical Industry Data Exchange).</span></span> <span data-ttu-id="34a9b-114">有关 CIDX 配置的信息，请参阅[设置向上 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)。</span><span class="sxs-lookup"><span data-stu-id="34a9b-114">For information about a CIDX configuration, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="34a9b-115"> 不支持在活动流程存在时更改流程配置。</span><span class="sxs-lookup"><span data-stu-id="34a9b-115"> does not support changing a process configuration while there are active processes.</span></span> <span data-ttu-id="34a9b-116">如果您强行更改，则活动流程将因失败而中止。</span><span class="sxs-lookup"><span data-stu-id="34a9b-116">If you do so, the active processes will complete with failures.</span></span> <span data-ttu-id="34a9b-117">所有新流程都将成功获取新的配置设置。</span><span class="sxs-lookup"><span data-stu-id="34a9b-117">All new processes will successfully pick up the new configuration settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34a9b-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="34a9b-118">In This Section</span></span>  
  
-   [<span data-ttu-id="34a9b-119">如何创建或编辑过程配置</span><span class="sxs-lookup"><span data-stu-id="34a9b-119">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [<span data-ttu-id="34a9b-120">使用 PIP 规范创建过程配置</span><span class="sxs-lookup"><span data-stu-id="34a9b-120">Using the PIP Specification to Create a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [<span data-ttu-id="34a9b-121">授权和不可否认性属性</span><span class="sxs-lookup"><span data-stu-id="34a9b-121">Authorization and Non-Repudiation Properties</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [<span data-ttu-id="34a9b-122">设置向上 CIDX eStandards 消息交换</span><span class="sxs-lookup"><span data-stu-id="34a9b-122">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)