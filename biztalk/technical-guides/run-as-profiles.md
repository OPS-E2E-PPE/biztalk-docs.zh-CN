---
title: "运行方式配置文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69fa6c9401f606619b2fb8d22d95ded48c18a092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-as-profiles"></a>运行方式配置文件
首次导入 BizTalk Server 核心库管理包，将创建两个新运行方式配置文件：  
  
-   **BizTalk Server 发现帐户**。 此配置文件是与 BizTalk Server 角色组件的所有发现相关联。  
  
-   **BizTalk Server 监视帐户**。 此配置文件与所有监视器和任务相关联。  
  
 默认情况下，所有发现、 监视器和任务在 BizTalk Server 管理包默认为使用"默认操作帐户"运行方式配置文件中定义的帐户中定义。  如果给定系统的默认操作帐户没有发现或监视 BizTalk 的必要权限，然后这些系统可绑定到 BizTalk Server 运行方式配置文件，它们有权访问 BizTalk Server 中更具体的凭据。  
  
 若要为 BizTalk Server 中配置运行方式配置文件的一般步骤如下：  
  
### <a name="to-configure-run-as-profiles"></a>若要配置运行方式配置文件  
  
1.  标识默认操作帐户其中具有权限不足以监视 BizTalk Server 的目标计算机的名称。  
  
2.  对于每个系统创建或使用一组现有凭据至少具有中论述的 BizTalk Server 特权[低特权环境](../technical-guides/low-privilege-environments.md)本管理包指南的一部分。  
  
3.  对于在步骤 2 中标识的凭据的每组，请确保管理组中存在相应运行方式帐户。 如有必要，请创建运行方式帐户。  
  
4.  在上设置的目标和运行方式帐户之间的映射**运行方式帐户**的每个运行方式配置文件的选项卡。