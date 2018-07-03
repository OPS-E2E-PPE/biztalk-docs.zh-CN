---
title: 证书源和存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, certificate storage
- importing certificates
- certificates, certificate sources
- certificates, importing
ms.assetid: 3e98fb56-4368-46f3-9329-c44fed11f4fb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13272f66fca9faec099d8fe8f1b6fb69bb1e6660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990334"
---
# <a name="certificate-sources-and-stores"></a>证书源和证书存储
本主题介绍导入和存储证书的位置。  
  
## <a name="certificate-sources"></a>证书源  
 从以下文件导入证书：  
  
- 从 .pfx 或 .p12 文件导入私用证书。 在导入证书后，对这些文件进行安全的存储。 如果您导入私用证书使用 CertWizard 实用工具，可以设置 **/可导出**切换到`False`，这是默认设置，以便私用证书不能从存储区导出到一个文件。 如果您设置 **/可导出**切换到`True`，您可以将这些证书导出到文件从证书 Microsoft 管理控制台 (MMC)。  
  
- 从 .cer 或 .der 文件导入公用证书。 合作伙伴用这些文件将其证书发送给您。  
  
- 从 .cer 或 .der 文件导入根证书。 证书授权机构用这些文件将其根证书发送给您。  
  
## <a name="certificate-storage"></a>证书存储  
 您将证书导入本地计算机的两个证书存储区之一。 中的公用证书**证书 （本地计算机）** 存储。 可以通过打开打开此存储区的节点**证书 （本地计算机）** Microsoft 中的节点[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。 您可以访问**证书 （本地计算机）** 存储如果计算机上拥有管理权限。 将公用证书存储在以下文件夹中：  
  
- 本组织中的个人文件夹中的公用证书**证书 （本地计算机）** 存储  
  
- 合作伙伴的其他人文件夹中的公用证书**证书 （本地计算机）** 存储  
  
- 从证书颁发机构的受信任的根证书颁发机构文件夹中的证书**证书 （本地计算机）** 存储  
  
  存储中的专用证书**证书-当前用户**存储。 可以通过打开管理控制台使用打开此存储区的节点**runas**命令和主机服务帐户用户。 有关详细信息，请参阅[导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 CertWizard 实用工具导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)   
 [使用 MMC 导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)   
 [导入证书&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)