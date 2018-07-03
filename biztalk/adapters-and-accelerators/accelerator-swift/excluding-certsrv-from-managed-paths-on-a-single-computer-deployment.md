---
title: 排除证书服务器从管理路径在单台计算机部署 |Microsoft Docs
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
ms.openlocfilehash: 1651131369ef4a8e0c4683b82f5b97163e33382f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987838"
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a>从单台计算机部署的管理路径中排除证书服务器
如果您部署了[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]一台计算机上并且也已安装证书服务器在同一台计算机，你需要排除证书服务器 (CertSrv) 从 Microsoft SharePoint Server 中心管理中的托管路径。  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a>若要从管理路径中排除 CertSrv  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。  
  
2.  在管理中心窗口中**虚拟服务器配置**部分中，单击**配置虚拟服务器设置**。  
  
3.  在虚拟服务器列表窗口中，单击**Default Web Site**。  
  
4.  在虚拟服务器设置窗口中**虚拟服务器管理**部分中，单击**定义管理路径**。  
  
5.  在定义管理路径窗口中**添加新路径**部分中，输入**CertSrv**中**路径**文本框。 在中**类型**部分中，单击**排除的路径**。 单击“确定” 。  
  
6.  关闭定义管理路径窗口中。