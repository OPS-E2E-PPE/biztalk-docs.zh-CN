---
title: "手动指定新主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6d635312d3765c37f1ab9c2b64505698f93e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="designating-a-new-master-secret-server-manually"></a>手动指定新主密钥服务器
群集硬件可能很昂贵。 如果硬件成本是个问题，你可以考虑手动指定另一台企业单一登录 (SSO) 服务器的主密钥服务器期间出现故障。 使用此选项，SSO 组中的任何其他 SSO 服务器可以提升到的主密钥服务器。 当主已关闭时，你可以手动将提升是主密钥服务器的 SSO 服务器之一。 此技术的最大缺点是，您不能编辑现有的部署，重新启动现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务，或部署新的 BizTalk 应用程序，直到将提升新的主密钥服务器。  
  
 为了使无缝的过程，你将需要实现某些监视机制，以便将尽可能快地发现失败。 你可以使用 System Center Operations Manager 等监视应用程序，以自动升级过程。  
  
 有关手动移动的主密钥服务器的详细信息，请参阅[如何移动主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156841)(http://go.microsoft.com/fwlink/?LinkId=156841) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="see-also"></a>另请参阅  
 [群集主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)