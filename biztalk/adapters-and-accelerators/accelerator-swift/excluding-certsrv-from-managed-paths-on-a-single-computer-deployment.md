---
title: 不包括从 CertSrv 托管在单台计算机部署上的路径 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c77fc1733859cd903bafcebc26162323feff82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207429"
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a>从托管在单台计算机部署上的路径中排除 CertSrv
如果你已经部署了[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]单台计算机上，并且也安装证书服务器在同一台计算机，你需要从托管路径中排除证书服务器 (CertSrv) [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint Server 管理中心。  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a>若要从托管路径排除 CertSrv  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
2.  在管理中心窗口中，在**虚拟服务器配置**部分中，单击**配置虚拟服务器设置**。  
  
3.  在虚拟服务器列表窗口中，单击**Default Web Site**。  
  
4.  在虚拟服务器设置窗口中，在**虚拟服务器管理**部分中，单击**定义管理路径**。  
  
5.  在定义管理路径窗口中，在**添加新路径**部分中，输入**CertSrv**中**路径**文本框。 在**类型**部分中，单击**排除路径**。 单击 **“确定”**。  
  
6.  关闭定义管理路径窗口。