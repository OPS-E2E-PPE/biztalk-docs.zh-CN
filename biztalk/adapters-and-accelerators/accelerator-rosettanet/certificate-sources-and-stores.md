---
title: 源和存储的证书 |Microsoft 文档
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
ms.openlocfilehash: f3ade897bb51850b4ef9dd6b530f5fc04c6b2601
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22210229"
---
# <a name="certificate-sources-and-stores"></a>证书源和存储
本主题介绍导入和存储证书的位置。  
  
## <a name="certificate-sources"></a>证书源  
 从以下文件导入证书：  
  
-   从 .pfx 或 .p12 文件导入私用证书。 在导入证书后，对这些文件进行安全的存储。 如果使用 CertWizard 实用工具将私钥证书导入，则可以设置 **/可导出**切换到`False`，这是默认设置，以便私有证书无法从存储区导出到文件。 如果你设置 **/可导出**切换到`True`，你可以从证书将这些证书导出到文件[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台 (MMC)。  
  
-   从 .cer 或 .der 文件导入公用证书。 合作伙伴用这些文件将其证书发送给您。  
  
-   从 .cer 或 .der 文件导入根证书。 证书授权机构用这些文件将其根证书发送给您。  
  
## <a name="certificate-storage"></a>证书存储  
 您将证书导入本地计算机的两个证书存储区之一。 存储中的公共证书**证书 （本地计算机）** 存储。 你可以通过打开打开的此存储节点**证书 （本地计算机）** 中的节点[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。 你可以访问**证书 （本地计算机）** 存储如果您的计算机上具有管理权限。 将公用证书存储在以下文件夹中：  
  
-   主页中的个人文件夹中的公共证书**证书 （本地计算机）** 存储  
  
-   合作伙伴的其他人文件夹中的公共证书**证书 （本地计算机）** 存储  
  
-   从的受信任根证书颁发机构文件夹中的证书颁发机构的证书**证书 （本地计算机）** 存储  
  
 存储中的私有证书**证书-当前用户**存储。 你可以通过打开管理控制台使用打开的此存储节点**runas**命令和主机服务帐户用户。 有关详细信息，请参阅[导入证书](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)。  
  
## <a name="see-also"></a>另请参阅  
 [导入证书使用 CertWizard 实用工具](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)   
 [导入证书使用 MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)   
 [导入证书&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)