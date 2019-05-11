---
title: 如何从发送端口删除证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cee3cb77368b8128ad5be66e4628f9c693f71c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335098"
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a>如何从发送端口删除证书
本主题介绍如何使用 BizTalk Server 管理控制台从发送端口删除安全证书。 发送端口时执行此操作时，将无法再加密的消息;将以明文形式发送消息。 从发送端口删除证书不会删除它从证书存储。  
  
> [!NOTE]
>  应用程序开发人员可以删除安全证书从发送端口在开发过程中通过使用本主题中的过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a>若要从发送端口删除证书  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要从发送端口删除证书。  
  
3. 展开**发送端口**，右键单击发送端口，单击**属性**，然后单击**证书**。  
  
4. 单击**删除证书**，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)