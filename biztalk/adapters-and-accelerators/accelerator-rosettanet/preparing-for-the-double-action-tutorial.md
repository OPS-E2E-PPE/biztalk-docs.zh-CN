---
title: 在 BizTalk Server 中 RosettaNet 双操作教程的先决条件 |Microsoft Docs
description: 单步执行 BizTalk Server 中的 RosettaNet 加速器 (BTARN) 双操作教程的先决条件
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48584cf7dfee0ca4812b41e56b4e8f7c0984e4fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979006"
---
# <a name="prepare-for-the-double-action-tutorial"></a>准备双操作教程

## <a name="prerequisites"></a>必要條件
教程： 开始前
  
- 执行完全安装的 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]两台计算机上。 有关详细信息，请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。  
  
  > [!IMPORTANT]
  >  请确保您完全配置 RosettaNet 加速器，包括启动 BTARN 业务流程。 请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。
  
- 本教程使用两台计算机而不是一台具有环回协议的计算机来模拟现实方案。 本教程用占位符作为计算机名。 该占位符替换为你选择的实际计算机名称。 例如，如果计算机运行你的 Contoso 解决方案命名为**Contoso**，在本教程的中替换任何出现\\ \\< contoso<strong>_</strong> *计算机*\>具有该计算机名称。  
  
- 本教程使用证书改进 Contoso 和 Fabrikam 之间的安全通信。 必须生成所有证书要求，并在其各自计算机上安装它们。  
  
## <a name="next-steps"></a>后续步骤 
  
-   [步骤 1：创建证书颁发机构](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [步骤 2：创建公共和私有证书](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [步骤 3：导入公共和私有证书](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [步骤 4：在 IIS 中启用安全套接字层](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)