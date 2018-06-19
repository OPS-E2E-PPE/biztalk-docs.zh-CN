---
title: 如何分配到证书接收位置 |Microsoft 文档
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
ms.assetid: 54ae300e-62c5-480f-a9b7-e5c3457a0f80
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94554aa5781ed609e5129d58ab75e5709e432278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248029"
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a>如何分配到证书接收位置
本主题将介绍如何使用 BizTalk Server 管理控制台向接收位置分配安全证书。 您只能在双向接收位置上执行此过程。 在运行 BizTalk Server 的计算机上的“其他人”证书存储中必须有证书，否则不会处理与此接收位置关联的消息并将记录错误。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a>若要将证书分配给接收位置  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其分配证书的接收位置所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  展开**接收位置**，右键单击接收位置，单击**属性**，然后单击**证书**。  
  
4.  如果本地计算机上是否存在此证书，请单击**浏览**，浏览到你想要分配给此证书接收位置，，然后单击**确定**。 否则，跳过此步骤。  
  
    > [!NOTE]
    >  如果您在从远程计算机执行此操作，则确保在运行 BizTalk Server 的计算机上存在证书，而不是只在本地计算机上存在证书。 否则，接收位置将无法处理消息。  
  
5.  如果证书中不存在的本地计算机上，**指纹**框中，键入或粘贴证书指纹，，然后单击**确定**。 证书指纹的格式为 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数。  
  
## <a name="see-also"></a>另请参阅  
 [管理接收位置](../core/managing-receive-locations.md)