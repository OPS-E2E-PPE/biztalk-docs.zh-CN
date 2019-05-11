---
title: 创建或编辑流程配置 |Microsoft Docs
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
ms.openlocfilehash: c8ac47ff1b939d9b0227ff2ae5dd176fdbde0260
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284328"
---
# <a name="creating-or-editing-a-process-configuration"></a><span data-ttu-id="1a21c-102">创建或编辑流程配置</span><span class="sxs-lookup"><span data-stu-id="1a21c-102">Creating or Editing a Process Configuration</span></span>
<span data-ttu-id="1a21c-103">本部分介绍如何创建或编辑流程配置，以便在 Microsoft 中实现合作伙伴接口流程 (PIP) [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1a21c-103">This section describes how to create or edit a process configuration to implement a Partner Interface Process (PIP) in Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="1a21c-104">RosettaNet PIP 定义两个贸易合作伙伴之间的业务流程对话框。</span><span class="sxs-lookup"><span data-stu-id="1a21c-104">A RosettaNet PIP defines a business-process dialog between two trading partners.</span></span> <span data-ttu-id="1a21c-105">在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、 PIP 创建与合作伙伴，必须首先创建流程配置。</span><span class="sxs-lookup"><span data-stu-id="1a21c-105">In [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], to create a PIP with a partner, you must first create a process configuration.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="1a21c-106">使用此配置文件存储 PIP 的所有配置特性。</span><span class="sxs-lookup"><span data-stu-id="1a21c-106">uses this profile to store all configuration characteristics of the PIP.</span></span> <span data-ttu-id="1a21c-107">然后可以使用此配置与合作伙伴创建协议。</span><span class="sxs-lookup"><span data-stu-id="1a21c-107">You can then use this configuration to create an agreement with the partner.</span></span>  
  
 <span data-ttu-id="1a21c-108">有关流程配置属性，以及用于创建或编辑流程配置过程的信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="1a21c-108">For information about process configuration properties, and procedures for creating or editing a process configuration, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="1a21c-109">在创建新的流程配置时，您必须基于 PIP 规范文档由 RosettaNet 组织维护上的设置。</span><span class="sxs-lookup"><span data-stu-id="1a21c-109">In creating a new process configuration, you must base the settings on the PIP specification document maintained by the RosettaNet organization.</span></span> <span data-ttu-id="1a21c-110">所有的流程配置设置都来自于 PIP 规范和[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]填充的大多数设置的默认值，是最常用的字段值。</span><span class="sxs-lookup"><span data-stu-id="1a21c-110">All process configuration settings come from the PIP specifications, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] populates most of the settings with default values that are the most typically used values for the fields.</span></span> <span data-ttu-id="1a21c-111">你必须验证的设置对应于相应的 PIP 规范中的值。</span><span class="sxs-lookup"><span data-stu-id="1a21c-111">You must verify that the settings correspond to the values in the appropriate PIP specification.</span></span> <span data-ttu-id="1a21c-112">有关如何输入的 PIP 设置映射到 PIP 规范中的指南的详细信息，请参阅[使用 PIP 规范创建流程配置](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="1a21c-112">For more information about how the PIP settings that you enter map to the guidance in the PIP specification, see [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="1a21c-113">进程配置可用于 RosettaNet 或 CIDX （化工行业数据交换）。</span><span class="sxs-lookup"><span data-stu-id="1a21c-113">The process configuration can be for either RosettaNet or CIDX (Chemical Industry Data Exchange).</span></span> <span data-ttu-id="1a21c-114">有关 CIDX 配置的信息，请参阅[设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)。</span><span class="sxs-lookup"><span data-stu-id="1a21c-114">For information about a CIDX configuration, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="1a21c-115">不支持更改流程配置时，有活动进程。</span><span class="sxs-lookup"><span data-stu-id="1a21c-115">does not support changing a process configuration while there are active processes.</span></span> <span data-ttu-id="1a21c-116">如果这样做，则活动流程将因失败而中止。</span><span class="sxs-lookup"><span data-stu-id="1a21c-116">If you do so, the active processes will complete with failures.</span></span> <span data-ttu-id="1a21c-117">所有新进程已成功将选取新的配置设置。</span><span class="sxs-lookup"><span data-stu-id="1a21c-117">All new processes will successfully pick up the new configuration settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1a21c-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="1a21c-118">In This Section</span></span>  
  
-   [<span data-ttu-id="1a21c-119">如何创建或编辑流程配置</span><span class="sxs-lookup"><span data-stu-id="1a21c-119">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [<span data-ttu-id="1a21c-120">使用 PIP 规范创建流程配置</span><span class="sxs-lookup"><span data-stu-id="1a21c-120">Using the PIP Specification to Create a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [<span data-ttu-id="1a21c-121">授权属性和不可否认性属性</span><span class="sxs-lookup"><span data-stu-id="1a21c-121">Authorization and Non-Repudiation Properties</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [<span data-ttu-id="1a21c-122">设置 CIDX eStandards 消息交换</span><span class="sxs-lookup"><span data-stu-id="1a21c-122">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)