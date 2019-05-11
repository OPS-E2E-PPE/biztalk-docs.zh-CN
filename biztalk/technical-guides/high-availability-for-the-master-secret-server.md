---
title: 主密钥服务器的高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b99cb04-61a5-41cc-a409-35897c17b789
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c27f5ad770f2127dfaecd9551cdfa37b18e6748b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277201"
---
# <a name="high-availability-for-the-master-secret-server"></a>主密钥服务器的高可用性
即使您不使用企业单一登录 (SSO) 功能来映射凭据和单一登录，SSO 将是整个 Microsoft BizTalk Server 基础结构的关键部分，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 SSO 帮助确保信息的端口配置。 端口配置数据加密，并存储在 SSO 数据库中。 每个 BizTalk server 提供用于加密和解密的端口配置数据使用了 SSO 服务服务 (ENTSSO.exe)。  
  
 SSO 服务启动时，它从主密钥服务器检索加密密钥。 此加密密钥称为主密钥。 主密钥服务器是另一个具有附加的子服务维护并分发主密钥的 SSO 服务。 检索主密钥后，SSO 服务将其缓存。 每隔 60 秒，SSO 服务主密钥服务器与同步主密钥。  
  
 如果主密钥服务器失败，并且 SSO 服务检测到一个其刷新的时间间隔中的故障，SSO 服务和服务器失败，包括凭据解密之前运行的所有运行时操作已成功继续。 但是，无法加密新的凭据或端口配置数据。 因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境具有主密钥服务器的可用性的依赖关系。  
  
## <a name="making-the-master-secret-server-available"></a>提供对主密钥服务器  
 为 SSO 系统的可用性，因此的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，它是关键您备份主密钥，只要它生成。 如果您丢失主密钥，则会丢失 SSO 系统将通过使用该主密钥加密的数据。 有关备份主密钥的详细信息，请参阅[如何返回主密钥](http://go.microsoft.com/fwlink/?LinkID=151934)(<http://go.microsoft.com/fwlink/?LinkID=151934>) 在 BizTalk Server 帮助。  
  
 您可以进行主密钥服务器可通过两种方式：  
  
- **可用，但不是高度可用**。 可以创建要在主密钥服务器变得不可用，并且你可以手动升级另一台 SSO 服务器主密钥服务器和还原此服务器上的主密钥时通知你的 Microsoft System Center Operations Manager 事件。  
  
   尽管此配置不具有高可用性，但可能会令人满意，在大多数情况下，与扩展接收、 发送和处理主机保持一致。  
  
- **高度可用**。 若要为主密钥服务器提供冗余，在单独的主密钥服务器群集上使用 Windows 群集或现有数据库群集上配置主密钥服务器。 主密钥服务器提供的服务不会占用很多资源，并通常不会影响数据库的功能或数据库群集上安装时的性能。 下图显示了如何使在主密钥服务器高度可用。  
  
   ![高度可用的主密钥服务器](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
   虽然此配置是高度可用，但它需要额外的硬件资源。 有关 sso 的高可用性安装选项的详细信息，请参阅[高可用性 SSO 安装选项](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838) BizTalk Server 帮助中。  
  
   本部分包括有关在上将 SSO 主密钥服务器配置为高度可用群集资源的详细的信息[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集。  
  
  > [!NOTE]
  >  若要减少高度可用的解决方案的硬件资源，可以添加在主密钥服务器为群集资源中你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集。 请注意，您不需要购买其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]许可证安装的 SSO 服务在运行 SQL Server 的计算机上。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)  
  
-   [手动指定新主密钥服务器](../technical-guides/designating-a-new-master-secret-server-manually.md)  
  
## <a name="see-also"></a>请参阅  
 [规划高 Availability2](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk 主机的的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [数据库的高可用性](../technical-guides/high-availability-for-databases.md)