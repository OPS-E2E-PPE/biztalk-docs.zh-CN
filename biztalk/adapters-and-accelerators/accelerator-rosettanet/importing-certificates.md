---
title: 导入证书 |Microsoft Docs
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
ms.openlocfilehash: 96dd45cb6a4f973b98a0a7a4a0c32c2d8452c0a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283655"
---
# <a name="importing-certificates"></a>导入证书
本部分介绍如何导入证书，包括从其导入的位置、 它们的存储的位置和使用导入它们何种工具。  
  
 有两种方法来导入证书。 可以使用 CertWizard 工具或证书管理单元中的 Microsoft 管理控制台 (MMC)。  
  
- CertWizard 为分步式命令行，用于配置基于开关设置的证书的使用。 此工具现已推出 Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 文件夹。  
  
- 证书管理单元在 MMC 中，您可导入证书的证书存储中。 但是，此手动过程需要您单独配置证书的使用。  
  
  > [!IMPORTANT]
  >  若要导入或使用私用证书 MMC 中，登录的用户必须具有 BizTalk 主机的用户标识。 如果不是，您必须运行**runas**与用户开关和主机服务帐户，以启动证书 MMC，例如，命令**runas /user: hostsvc mmc**。 通过运行以下命令，您假定 BizTalk 主机 （BizTalkServerApplication 和 BizTalkServerIsolatedHost） 的用户标识。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [证书源和证书存储](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [使用 CertWizard 实用程序导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [使用 MMC 导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)