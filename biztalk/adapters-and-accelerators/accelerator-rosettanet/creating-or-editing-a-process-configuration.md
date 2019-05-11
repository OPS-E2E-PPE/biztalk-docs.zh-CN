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
# <a name="creating-or-editing-a-process-configuration"></a>创建或编辑流程配置
本部分介绍如何创建或编辑流程配置，以便在 Microsoft 中实现合作伙伴接口流程 (PIP) [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 RosettaNet PIP 定义两个贸易合作伙伴之间的业务流程对话框。 在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、 PIP 创建与合作伙伴，必须首先创建流程配置。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用此配置文件存储 PIP 的所有配置特性。 然后可以使用此配置与合作伙伴创建协议。  
  
 有关流程配置属性，以及用于创建或编辑流程配置过程的信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
 在创建新的流程配置时，您必须基于 PIP 规范文档由 RosettaNet 组织维护上的设置。 所有的流程配置设置都来自于 PIP 规范和[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]填充的大多数设置的默认值，是最常用的字段值。 你必须验证的设置对应于相应的 PIP 规范中的值。 有关如何输入的 PIP 设置映射到 PIP 规范中的指南的详细信息，请参阅[使用 PIP 规范创建流程配置](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)。  
  
 进程配置可用于 RosettaNet 或 CIDX （化工行业数据交换）。 有关 CIDX 配置的信息，请参阅[设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持更改流程配置时，有活动进程。 如果这样做，则活动流程将因失败而中止。 所有新进程已成功将选取新的配置设置。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [使用 PIP 规范创建流程配置](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [授权属性和不可否认性属性](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)