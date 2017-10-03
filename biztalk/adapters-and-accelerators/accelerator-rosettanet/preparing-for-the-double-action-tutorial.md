---
title: "BizTalk Server 中的 RosettaNet Double 操作教程的先决条件 |Microsoft 文档"
description: "单步执行双操作教程 RosettaNet 快捷键 (BTARN) BizTalk Server 中的先决条件"
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87e2750a16d2c65b5838b6d61f27cbd2b2ff9885
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-double-action-tutorial"></a>对于双操作教程准备

## <a name="prerequisites"></a>先决条件
在开始本教程： 之前
  
-   执行完全安装的 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]两台计算机上。 有关详细信息，请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。  
  
    > [!IMPORTANT]
    >  请确保你完全配置 RosettaNet 快捷键，包括起始 BTARN 业务流程。 请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。
  
-   本教程使用两台计算机而不是一台具有环回协议的计算机来模拟现实方案。 本教程用占位符作为计算机名。 该占位符替换为你选择的实际计算机名称。 例如，如果计算机运行 Contoso 解决方案命名为**Contoso**，任何匹配项替换的教程中\\ \\< contoso**_** *计算机*> 具有该计算机名称。  
  
-   本教程使用证书改进 Contoso 和 Fabrikam 之间的安全通信。 你必须生成任何证书要求，以及在其各自的计算机上安装它们。  
  
## <a name="next-steps"></a>后续步骤 
  
-   [步骤 1： 创建证书颁发机构](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [步骤 2： 创建公共和私有证书](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [步骤 3： 导入公共和私有证书](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [步骤 4： 启用安全套接字在 IIS 中的层](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)