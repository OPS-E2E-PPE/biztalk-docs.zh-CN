---
title: 聚类分析主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50813db21de9505b6c417be8950279fcd62a37cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277209"
---
# <a name="clustering-the-master-secret-server"></a>聚类分析主密钥服务器
BizTalk Server 应用程序服务维护硬编码依赖于随一起安装的企业单一登录 (SSO) 服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 SSO 服务必须能够与启动主密钥服务器进行通信。 我们建议您在主密钥服务器提供容错能力的主密钥服务器上群集 SSO 服务。 有关详细信息，请参阅[高可用性 SSO 安装选项](http://go.microsoft.com/fwlink/?LinkId=156838)(<http://go.microsoft.com/fwlink/?LinkId=156838>) 在 BizTalk Server 帮助。  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a>准备进行群集主密钥服务器  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a>决定是否要使用的专用的群集或 SQL Server 群集  
 聚类分析硬件成本很高。 若要减少高度可用的解决方案的硬件资源，可以添加在主密钥服务器为群集资源中你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集。 如果使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库群集，我们建议您不要将主密钥服务器上作为 MessageBox 数据库的同一个活动节点。 MessageBox 数据库是通常较为繁忙比其他数据库。 即使在主密钥服务器不会消耗许多硬件资源，则最好从活动的 MessageBox 数据库节点将其移动到另一个活动群集节点。  
  
### <a name="clustering-the-sso-database"></a>聚类分析的 SSO 数据库  
 主密钥服务器取决于 SSO 数据库。 若要构建一个高可用性 SSO，您必须将群集 SSO 数据库。 有关聚类分析 BizTalk 数据库的详细信息，请参阅[聚类分析 BizTalk Server 数据库 2](../technical-guides/clustering-the-biztalk-server-databases2.md)。  
  
### <a name="creating-domain-groups-and-accounts"></a>创建域组和帐户  
 需要群集主密钥服务器之前，配置以下域组和帐户：  
  
-   创建具有名称 SSO Administrators 和 SSO Affiliate Administrators 域组。 若要创建企业 SSO 服务的群集的实例，必须为域组中创建的 SSO Administrators 和 SSO Affiliate Administrators 组。  
  
-   创建或指定域帐户是 SSO Administrators 域组的成员。 每个节点上的企业 SSO 服务将配置为作为此域帐户登录。 此帐户必须在群集中每个节点上具有"作为服务登录"权限。 此帐户还必须授予对群集的完全控制访问。  
  
## <a name="clustering-the-master-secret-server"></a>聚类分析主密钥服务器  
 下面是聚类分析主密钥服务器的基本步骤：  
  
1. 安装和配置企业 SSO 群集节点上。  
  
2. 创建群集的企业 SSO 资源和从属资源。  
  
3. 还原第二个群集节点上的主密钥。 如果将主密钥服务器移到群集时，必须还原的第一个的群集节点上的主密钥。  
  
4. 将包含 SSO 服务，联机的群集组。  
  
5. 更新管理数据库中的主机密名称。  
  
   有关群集主密钥服务器的详细步骤，请参阅[如何群集主密钥服务器](http://go.microsoft.com/fwlink/?LinkId=156839)(<http://go.microsoft.com/fwlink/?LinkId=156839>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="see-also"></a>请参阅  
 [手动指定新主密钥服务器](../technical-guides/designating-a-new-master-secret-server-manually.md)