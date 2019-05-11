---
title: 如何为发送端口分配证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, assigning
- managing [send ports], certificates
- assigning certificates
- certificates, send ports
ms.assetid: ba9e9c8b-f5b6-4fee-9e89-31b0f1df6ed4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb9fbc2cc7237f1e5cf9343f7ae8537b7ea8218a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387209"
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a>如何为发送端口分配证书
本主题介绍如何使用 BizTalk Server 管理控制台为发送端口分配安全证书。 该证书必须位于运行 BizTalk Server 的计算机上的其他人证书存储或将不会处理与此发送端口相关联的消息，并将记录错误。  
  
> [!NOTE]
>  应用程序开发人员可以分配安全证书向发送端口在开发过程中通过使用本主题中的过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a>若要为发送端口分配证书  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要将证书分配到发送端口。  
  
3. 展开**发送端口**，右键单击发送端口，单击**属性**，然后单击**证书**。  
  
4. 如果证书存在于本地计算机上，单击**浏览**，浏览到你想要将分配到此发送端口，然后单击该证书**确定**。 否则，跳过此步骤。  
  
   > [!NOTE]
   >  即使在本地计算机上存在证书，它还必须存在运行 BizTalk Server 中，如果不同之前将无法处理消息的发送端口, 的计算机上。  
  
5. 如果证书中不存在本地计算机上**指纹**框中，键入或粘贴证书指纹，然后单击**确定**。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)