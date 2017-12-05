---
title: "群集主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f37997582cbd94d8bbb5eaee829eead0af85ad2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="clustering-the-master-secret-server"></a>群集主密钥服务器
BizTalk Server 应用程序服务维护硬编码依赖于随企业单一登录 (SSO) 服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 SSO 服务必须能够与启动的主密钥服务器进行通信。 我们建议你在主密钥服务器以提供容错功能的主密钥服务器上群集 SSO 服务。 有关详细信息，请参阅[高可用性 SSO 安装选项](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838) BizTalk Server 帮助中。  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a>准备群集主密钥服务器  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a>决定是否使用专用的群集或 SQL Server 群集  
 群集硬件也是如此。 若要减少高度可用的解决方案的硬件资源，可以添加的主密钥服务器中的群集资源作为你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集。 如果你使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集中，我们建议不要为 MessageBox 数据库相同的活动节点上放置的主密钥服务器。 MessageBox 数据库是通常更加繁忙比其他数据库。 即使是主密钥服务器不使用许多硬件资源，则最好从活动的 MessageBox 数据库节点将它移动到不同的活动群集节点。  
  
### <a name="clustering-the-sso-database"></a>群集的 SSO 数据库  
 主密钥服务器依赖于 SSO 数据库。 若要生成高可用性 SSO，必须群集 SSO 数据库。 有关群集 BizTalk 数据库的详细信息，请参阅[群集 BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md)。  
  
### <a name="creating-domain-groups-and-accounts"></a>创建域组和帐户  
 你需要在群集的主密钥服务器之前配置的以下域组和帐户：  
  
-   使用 SSO Administrators 和 SSO Affiliate Administrators 的名称创建域组。 若要创建企业 SSO 服务的群集的实例，必须为域组中创建的 SSO Administrators 和 SSO Affiliate Administrators 组。  
  
-   创建或指定为 SSO Administrators 域组的成员的域帐户。 每个节点上的企业 SSO 服务将配置为作为此域帐户登录。 此帐户必须具有群集中每个节点上的"作为服务登录"权限。 此帐户还必须授予访问群集的完全控制权限。  
  
## <a name="clustering-the-master-secret-server"></a>群集主密钥服务器  
 下面是群集的主密钥服务器的基本步骤：  
  
1.  安装和配置企业 SSO 在群集节点上。  
  
2.  创建群集的企业 SSO 资源和从属资源。  
  
3.  还原主密钥第二个群集节点上。 如果将主密钥服务器移到群集时，必须还原主密钥第一个的群集节点上。  
  
4.  将包含 SSO 服务，联机的群集组。  
  
5.  更新管理数据库中的主密钥名称。  
  
 有关群集的主密钥服务器的详细步骤，请参阅[如何安装群集主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156839)(http://go.microsoft.com/fwlink/?LinkId=156839) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="see-also"></a>另请参阅  
 [手动指定新主密钥服务器](../technical-guides/designating-a-new-master-secret-server-manually.md)