---
title: "导出证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1898162b27956e4e527013ff765edf6aea440e9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exporting-certificates"></a>导出证书
本主题说明如何使用证书导出向导导出证书。 使用此向导可导出公用证书或私用证书。  
  
### <a name="to-export-a-partner-certificate"></a>导出合作伙伴证书  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] ，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2.  展开**证书 （本地计算机）**，展开**其他人**，然后单击**证书**。  
  
3.  在右窗格中，右键单击证书的名称，指向**所有任务**，然后单击**导出**。  
  
4.  上**欢迎使用证书导出向导**页上，单击**下一步**。  
  
5.  上**导出文件格式**页上，选择你想要为文件使用的格式。 此格式通常为 DER 编码二进制 x.509，用于导出二进制编码文件，或者是 Base64 编码的 x.509，用于导出 Base64 编码文件。  
  
    > [!NOTE]
    >  使用 Base64 对证书编码使得可以在 UNIX 服务器上使用证书。  
  
6.  上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型文件的名称，请单击**下一步**，然后单击**完成**.  
  
### <a name="to-export-the-home-organization-certificate"></a>导出本组织证书  
  
1.  单击**启动**，单击**运行**，类型**runas /user:\<承载服务 > mmc**，其中\< *hostservice*> 是你在安装时，在与主机服务关联的服务名称[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]，然后单击**确定**运行[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理控制台 (MMC) 的上下文中主机服务。  
  
    > [!NOTE]
    >  你运行**runas**命令假定访问主页组织证书所需的主机服务的标识。  
  
2.  展开**证书-当前用户**，展开**个人**，然后单击**证书**。  
  
3.  在右窗格中，右键单击证书的名称，指向**所有任务**，然后单击**导出**。  
  
4.  上**欢迎使用证书导出向导**页上，单击**下一步**。  
  
5.  若要导出的公钥与证书的私钥关联，将保留**否，不导出私钥**选。 若要导出的私钥，请选择**是，导出私钥**。  
  
    > [!NOTE]
    >  如果你选择**是，导出私钥**，强烈建议不要不将生成的文件发送到合作伙伴。  
  
    > [!NOTE]
    >  **是，导出私钥**选项将不可用，如果你未做私钥可导出时你首次导入它。  
  
6.  上**导出文件格式**页上，选择你想要为文件使用的格式。 此格式通常为 DER 编码二进制 x.509，用于导出二进制编码文件，或者是 Base64 编码的 x.509，用于导出 Base64 编码文件。  
  
    > [!NOTE]
    >  使用 Base64 对证书编码使得可以在 UNIX 服务器上使用证书。  
  
7.  上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型文件的名称，请单击**下一步**，然后单击**完成**.  
  
## <a name="see-also"></a>另请参阅  
 [管理证书](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)