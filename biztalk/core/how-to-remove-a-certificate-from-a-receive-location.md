---
title: 如何删除从证书接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 717d41bf-4260-4df4-9d0a-07243bb9b12c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e70cd846c364d52544bf8504d42132dd35fe65d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254533"
---
# <a name="how-to-remove-a-certificate-from-a-receive-location"></a>如何从接收位置删除证书
本主题将介绍如何使用 BizTalk Server 管理控制台从接收位置删除安全证书。 执行此操作后，接收位置将不再对消息进行加密，消息将以明文形式发送。 从接收位置删除证书并不会从证书存储中删除该证书。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-certificate-from-a-receive-location"></a>从接收位置删除证书  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要从接收位置删除其证书的 BizTalk 组和 BizTalk 应用程序。  
  
3.  展开**接收位置**，右键单击接收位置，单击**属性**，然后单击**证书**。  
  
4.  单击**删除证书**，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [管理接收位置](../core/managing-receive-locations.md)