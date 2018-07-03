---
title: 手动指定新的主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b9453ade3d447e874609d1357e2383a5c21686f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975094"
---
# <a name="designating-a-new-master-secret-server-manually"></a>手动指定新的主密钥服务器
群集硬件可能成本高昂。 如果硬件成本是一个问题，则可以考虑手动指定另一个企业单一登录 (SSO) 服务器，在故障情况下保持在主密钥服务器。 使用此选项，可以为主密钥服务器升级 SSO 组中的任何其他 SSO 服务器。 主机关闭时，你可以手动升级是主密钥服务器与 SSO 服务器之一。 此技术的最大缺点是，不能编辑现有部署，重新启动现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务，或部署新的 BizTalk 应用程序，直到您提升新的主密钥服务器。  
  
 若要使该过程无缝，您需要实现某些监视机制，以便将尽可能快地发现失败。 此外可以通过使用 System Center Operations Manager 等监视应用程序自动升级过程。  
  
 有关手动移动主密钥服务器的详细信息，请参阅[如何移动主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156841)(<http://go.microsoft.com/fwlink/?LinkId=156841>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="see-also"></a>请参阅  
 [聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)