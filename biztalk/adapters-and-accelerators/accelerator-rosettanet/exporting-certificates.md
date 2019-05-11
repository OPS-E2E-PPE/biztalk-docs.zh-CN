---
title: 导出证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00fb00a1b256be192ce591b2b11ec70ab9b9d398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283725"
---
# <a name="exporting-certificates"></a>导出证书
本主题介绍如何使用证书导出向导导出的证书。 使用此向导导出公共证书或私用证书。  
  
### <a name="to-export-a-partner-certificate"></a>若要导出合作伙伴证书  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] ，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2. 展开**证书 （本地计算机）**，展开**其他人**，然后单击**证书**。  
  
3. 在右窗格中，右键单击证书名称，指向**的所有任务**，然后单击**导出**。  
  
4. 上**欢迎使用证书导出向导**页上，单击**下一步**。  
  
5. 上**导出文件格式**页上，选择你想要使用的文件的格式。 此格式通常为 DER 编码二进制 x.509，用于导出二进制编码的文件，或 Base-64 编码 x.509，用于导出的 Base-64 编码文件。  
  
   > [!NOTE]
   >  对证书采用 Base-64 编码，可以在 UNIX 服务器上使用证书。  
  
6. 上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型的文件的名称，单击**下一步**，然后单击**完成**.  
  
### <a name="to-export-the-home-organization-certificate"></a>若要导出本组织证书  
  
1. 单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，其中\< *hostservice* \>是安装 Microsoft 时与主机服务关联的服务名称[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]，然后单击**确定**中运行 Microsoft 管理控制台 (MMC)主机服务的上下文。  
  
   > [!NOTE]
   >  在运行**runas**命令可以获得主机服务，以访问本组织证书所需的标识。  
  
2. 展开**证书-当前用户**，展开**个人**，然后单击**证书**。  
  
3. 在右窗格中，右键单击证书名称，指向**的所有任务**，然后单击**导出**。  
  
4. 上**欢迎使用证书导出向导**页上，单击**下一步**。  
  
5. 若要导出公钥与证书的私钥关联，将保留**否，不导出私钥**选定。 若要导出的私钥，请选择**是，导出私钥**。  
  
   > [!NOTE]
   >  如果选择**是，导出私钥**，强烈建议不要向合作伙伴发送生成的文件。  
  
   > [!NOTE]
   >  **是，导出私钥**选项将不可用，如果你未作私钥可导出时您首次导入它。  
  
6. 上**导出文件格式**页上，选择你想要使用的文件的格式。 此格式通常为 DER 编码二进制 x.509，用于导出二进制编码的文件，或 Base-64 编码 x.509，用于导出的 Base-64 编码文件。  
  
   > [!NOTE]
   >  对证书采用 Base-64 编码，可以在 UNIX 服务器上使用证书。  
  
7. 上**导出的文件**页上，单击**浏览**，找到你想要将文件存储，其中类型的文件的名称，单击**下一步**，然后单击**完成**.  
  
## <a name="see-also"></a>请参阅  
 [管理证书](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)