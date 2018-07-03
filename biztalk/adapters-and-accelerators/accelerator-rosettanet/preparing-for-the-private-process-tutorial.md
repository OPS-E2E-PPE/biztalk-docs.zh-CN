---
title: 在 BizTalk Server 中 RosettaNet 专用流程教程的先决条件 |Microsoft Docs
description: 单步执行 BizTalk Server 中的 RosettaNet 加速器 (BTARN) 的专用流程教程的先决条件
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 823788385b659f5aa26d4aa92db1e234f2773600
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010926"
---
# <a name="prepare-for-the-private-process-tutorial"></a>准备专用流程教程

## <a name="prerequisites"></a>必要條件
教程： 开始前
  
- 执行完全安装的 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]两台计算机上。 有关详细信息，请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。  
  
  > [!IMPORTANT]
  >  请确保您完全配置 RosettaNet 加速器，包括启动 BTARN 业务流程。 请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。 您可能还需要添加[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到 Microsoft Windows® SharePoint™ Services 管理的路径排除列表 （包括 btarnhttpreceive） 的虚拟目录。 
  
- 本教程通过使用两台计算机而不一台具有环回协议来模拟真实方案。 每当本教程使用计算机名称，它会使用与计算机名称的占位符。 该占位符替换为你选择的实际计算机名称。 例如，如果计算机运行你的 Contoso 解决方案命名为**Contoso**，在本教程的中替换任何出现\\ \\< contoso<strong>_</strong> *计算机*\>具有该计算机名称。  
  
  本教程使用证书改进 Contoso 和 Fabrikam 之间的安全通信。 必须生成所有证书要求，并在各自计算机上安装它们。  
  
## <a name="next-steps"></a>后续步骤
  
-   [还原 Contoso 数据库](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [生成和启用证书](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)