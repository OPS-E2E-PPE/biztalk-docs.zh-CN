---
title: 企业单一登录的高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 2016-02-29
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, availability
- high availability, SSO
- Master Secret server, high availability
- SSO, high availability
ms.assetid: 6c631b5c-7147-4cc0-b58a-6749e83df9d3
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fd572db5425b86a422fd1cca574ba7aba2e4262
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387583"
---
# <a name="high-availability-for-enterprise-single-sign-on"></a>企业单一登录的高可用性
即使您不使用企业单一登录 (SSO) 功能来映射凭据和单一登录，SSO 是整个 Microsoft 的关键部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基础结构，因为 BizTalk Server 使用 SSO 帮助确保信息的安全接收位置。  
  
 必须配置主密钥服务器为安装 SSO 服务的第一个计算机。 主密钥服务器是存储主密钥 （加密密钥） 的 SSO 服务器。 主密钥是 SSO 系统用来加密和解密的数据将存储在 SSO 数据库中的加密密钥。  
  
 如果 SSO 服务器出现故障，并且如果有其他 BizTalk Server 计算机 （并因此 SSO 服务器） 运行相同的主机实例，与其他 SSO 服务器将继续其工作。 这意味着，在主密钥服务器仍函数工作正常，因此 BizTalk Server 处理继续进行。  
  
 如果主服务器发生故障，包括凭据解密失败前, 运行的所有运行时操作仍可正常都继续。 但是，无法加密新的凭据。 因此，BizTalk Server 环境具有依赖项可用性的主密钥服务器，如下图中所示。  
  
 ![故障点](../core/media/tdi-highava-pointsfailure-mss.gif "TDI_HighAva_PointsFailure_MSS")  
  
> [!NOTE]
>  如果主密钥服务器变得不可用，然后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例仍可以通过使用直到主密钥的内存中缓存的副本执行运行时操作：  
> 
> - 重新启动主机实例。  
>   -   重新启动运行 BizTalk 主机实例的计算机上的 SSO 服务。  
>   -   SSO 主密钥发生更改。  
> 
>   如果在重新启动 SSO 服务，则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机或如果 SSO 主密钥已发生更改，将从内存中释放主密钥的缓存的副本和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须能够联系主密钥服务器获取的另一个副本主密钥。 如果主密钥服务器不可用的出于加密目的而需要访问主密钥服务器的任何管理操作将失败。  
  
## <a name="making-the-master-secret-server-available"></a>提供对主密钥服务器  
 有关可用的 SSO 系统中，并且因此 BizTalk Server 环境中，只要它生成备份主密钥。 如果您丢失主密钥，则会丢失 SSO 系统将通过使用该主密钥加密的数据。 有关备份主密钥的详细信息，请参阅[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
 您可以进行主密钥服务器可通过两种方式：  
  
-   **可用，但不是高度可用。** 所有 SSO 服务器都具有主密钥缓存在内存中，并将继续运行时操作，即使主密钥服务器发生故障。 但是，您将不能更改端口的配置或 SSO 配置。 BizTalk Server 运行时将继续正常工作，但不能进行任何设计更改。  
  
     即使此配置不具有高可用性，可能会令人满意，在大多数情况下，与扩展接收、 发送和处理主机保持一致。  
  
-   **高度可用。** 若要为主密钥服务器提供冗余，在单独的主密钥服务器群集上使用 Windows 群集或现有数据库群集上配置主密钥服务器。 主密钥服务器提供的服务不会占用很多资源，并通常不会影响数据库的功能或数据库群集上安装时的性能。 下图显示了如何使在主密钥服务器高度可用。  
  
     ![高度可用的主密钥服务器](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
     虽然此配置是高度可用，但它需要额外的硬件资源。 有关高可用性 sso 安装选项的详细信息，请参阅[高可用性 SSO 安装选项](../core/high-availability-sso-installation-options.md)。 本部分包括有关配置为高度可用群集资源在 Windows Server 群集上的 SSO 主密钥服务器详细的信息。  
  
    > [!NOTE]
    >  若要减少高度可用的解决方案的硬件资源，您可以在 SQL Server 群集中添加为群集资源在主密钥服务器。 不需要购买额外的 BizTalk Server 许可证，才能在另一台计算机上安装 SSO 服务。  
  
## <a name="see-also"></a>请参阅  
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)   
 [创建高度可用的 BizTalk Server 环境](../core/creating-a-highly-available-biztalk-server-environment.md)   
 [如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)