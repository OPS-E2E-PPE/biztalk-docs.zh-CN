---
title: "BizTalk Server 中的 RosettaNet 私有过程教程的先决条件 |Microsoft 文档"
description: "单步执行 RosettaNet 快捷键 (BTARN) BizTalk Server 中私有过程本教程的先决条件"
caps.latest.revision: "7"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 4da7190c7212f74a90689ca403d899eb1a849cc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-private-process-tutorial"></a>对于私有过程教程准备

## <a name="prerequisites"></a>先决条件
在开始本教程： 之前
  
-   执行完全安装的 BizTalk Server 和[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]两台计算机上。 有关详细信息，请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。  
  
    > [!IMPORTANT]
    >  请确保你完全配置 RosettaNet 快捷键，包括起始 BTARN 业务流程。 请参阅[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)。 你可能还需要添加[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到 Microsoft Windows® SharePoint™ Services 托管的路径的排除列表 （包括 btarnhttpreceive） 的虚拟目录。 
  
-   本教程通过使用两台计算机而不环回协议一台计算机来模拟真实世界方案。 只要本教程使用计算机名称，它会使用与计算机名称的占位符。 该占位符替换为你选择的实际计算机名称。 例如，如果计算机运行 Contoso 解决方案命名为**Contoso**，任何匹配项替换的教程中\\ \\< contoso**_** *计算机*> 具有该计算机名称。  
  
 本教程使用证书改进 Contoso 和 Fabrikam 之间的安全通信。 你必须生成任何证书要求，以及在各自计算机上安装它们。  
  
## <a name="next-steps"></a>后续步骤
  
-   [Contoso 数据库还原](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [生成并启用证书](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)