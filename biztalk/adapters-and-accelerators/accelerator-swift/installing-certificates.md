---
title: 安装证书 |Microsoft Docs
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
ms.openlocfilehash: 4d1593c28186e0b5f96c749e67469257592e291d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377287"
---
# <a name="installing-certificates"></a>安装证书
若要发送、 修复或将消息提交，您必须安装了正确的证书。 本主题介绍如何添加证书。 在生产环境中，请参阅 IT 部门以获得证书。  

 **摘要**  

 本部分说明如何创建并存储在以下证书：  

- 每个客户端计算机上的每个消息修复和新提交证书-当前用户的个人文件夹中的角色的证书存储  

- 每个 BizTalk 业务流程服务器计算机上的每个消息修复和新提交的证书 （本地计算机） 的其他人文件夹中的角色的证书存储  

- 为每个客户端计算机上的证书 （本地计算机） 存储中的受信任的根证书颁发机构文件夹的证书颁发机构的证书  

  如果您部署了[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]一台计算机上，而且还必须安装在同一台计算机上的证书服务器，需要为 Microsoft SharePoint Server 从管理路径排除证书服务器。  

  本部分包含：  

- [将证书添加到客户端上的证书存储](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  

- [将证书添加到服务器上的证书存储](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  

- [从单台计算机部署的管理路径中排除证书服务器](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)
