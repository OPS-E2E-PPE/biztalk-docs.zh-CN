---
title: 将证书安装 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, installing
- installing, certificates
ms.assetid: 7525f771-623c-420f-99ca-c834e819829d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5ded26548303dfe9c9a095c24396b4e2683ca4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209461"
---
# <a name="installing-certificates"></a>安装证书
若要发送、 修复或提交消息，必须安装的正确证书。 本主题介绍如何添加证书。 在生产环境中，请参阅你的 IT 部门的证书。  
  
 **摘要**  
  
 本部分将说明了如何创建和存储以下证书：  
  
-   每个客户端计算机上为每个消息修复和新提交证书-当前用户的个人文件夹中的角色的证书存储  
  
-   为每个消息修复和新提交的证书 （本地计算机） 的其他人文件夹中的角色的证书存储在每个 BizTalk 业务流程服务器计算机上  
  
-   为每个客户端计算机上的证书 （本地计算机） 存储中的受信任根证书颁发机构文件夹的证书颁发机构的证书  
  
 如果你已经部署了[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]单台计算机上，而且还可以在同一台计算机上安装的证书服务器，需要从托管路径中排除该证书服务器[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]SharePoint 服务器。  
  
 本部分包含：  
  
-   [将证书添加到客户端上的证书存储](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  
  
-   [将证书添加到服务器上的证书存储](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  
  
-   [从托管在单台计算机部署上的路径中排除 CertSrv](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)