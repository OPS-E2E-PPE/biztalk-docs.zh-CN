---
title: 导入证书 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78773d6eb1fc7e51ca80afadfd282d54def80b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209973"
---
# <a name="importing-certificates"></a>导入证书
本节介绍如何导入证书，包括从何处导入证书、将证书存储在何处以及使用何工具来导入证书。  
  
 有两种方法可导入证书。 你可以使用 CertWizard 工具或证书管理单元接[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台 (MMC)。  
  
-   CertWizard 为分步式命令行工具，基于开关设置来配置证书的使用。 此工具可用于[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 文件夹。  
  
-   使用 MMC 中的证书管理单元，可将证书导入到证书存储区中。 但是，该手动过程需要您单独配置证书的使用。  
  
    > [!IMPORTANT]
    >  要在 MMC 中导入或使用私用证书，已登录的用户必须具有 BizTalk 主机的用户标识。 如果没有，你必须运行**runas**用户交换机和主机服务帐户，以启动证书 MMC，例如，命令**runas /user:hostsvc mmc**。 通过运行此命令，您可获得 BizTalk 主机（BizTalkServerApplication 和 BizTalkServerIsolatedHost）的用户标识。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [证书源和存储](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [导入证书使用 CertWizard 实用工具](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [导入证书使用 MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)