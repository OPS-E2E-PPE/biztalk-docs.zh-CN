---
title: 运行方式配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a51092ace594033ae559e536cb65240ac44e063
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270425"
---
# <a name="run-as-profiles"></a>运行方式配置文件
首次导入 BizTalk Server 核心库管理包，将创建两个新运行方式配置文件：  
  
- **BizTalk Server 发现帐户**。 此配置文件是与 BizTalk Server 角色组件的所有发现相关联。  
  
- **BizTalk Server 监视帐户**。 此配置文件与所有监视器和任务相关联。  
  
  默认情况下，所有发现、 监视器和 BizTalk Server 管理包默认为使用"默认操作帐户"运行方式配置文件中定义的帐户中定义的任务。  如果给定系统的默认操作帐户不具有发现或监视 BizTalk 的必要权限，这些系统可以将绑定到 BizTalk Server 运行方式配置文件，它们具有访问 BizTalk Server 中更具体的凭据。  
  
  若要配置 BizTalk Server 运行方式配置文件的一般步骤如下：  
  
### <a name="to-configure-run-as-profiles"></a>若要配置运行方式配置文件  
  
1.  确定其中的默认操作帐户有权限不足以监视 BizTalk Server 的目标计算机的名称。  
  
2.  对于每个系统创建或使用一组现有凭据至少具有中论述的 BizTalk Server 特权[低特权环境](../technical-guides/low-privilege-environments.md)部分中的此管理包指南。  
  
3.  对于每个组在步骤 2 中标识的凭据，请确保管理组中存在相应运行方式帐户。 如有必要，请创建运行方式帐户。  
  
4.  上设置的目标和运行方式帐户之间的映射**运行方式帐户**的每个运行方式配置文件的选项卡。