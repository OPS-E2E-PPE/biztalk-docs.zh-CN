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
ms.openlocfilehash: 9acc933df7b958ea6ae0f0651fd66ba14daad913
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019241"
---
# <a name="high-availability-for-enterprise-single-sign-on"></a>企业单一登录的高可用性
即使您不使用企业单一登录 (SSO) 功能来映射凭据和进行单一登录，SSO 也是整个 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 基础结构的重要部分，因为 BizTalk Server 使用 SSO 帮助确保接收位置信息的安全。  
  
 您必须将安装 SSO 服务的首台计算机配置为主密钥服务器。 主密钥服务器是存储主密钥（加密密钥）的 SSO 服务器。 主密钥是 SSO 系统用来对其存储在 SSO 数据库中的数据进行加密和解密的加密密钥。  
  
 在其中一台 SSO 服务器发生故障时，如果还有其他 BizTalk Server 计算机（因此也是 SSO 服务器）在运行同一主机实例，则这些 SSO 服务器仍可继续其工作。 这意味着主密钥服务器仍工作正常，因此 BizTalk Server 可继续进行处理。  
  
 如果主密钥服务器发生故障，则在发生故障前运行的所有运行时操作（包括凭据解密）仍可正常继续。 但您无法对新凭据进行加密。 因此，BizTalk Server 环境对主密钥服务器的可用性具有依存关系，如下图所示：  
  
 ![故障点](../core/media/tdi-highava-pointsfailure-mss.gif "TDI_HighAva_PointsFailure_MSS")  
  
> [!NOTE]
>  如果主密钥服务器变得不可用，通过使用主密钥的内存中缓存的副本，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机实例仍可以执行运行时操作，直到：  
> 
> - 重新启动主机实例。  
>   -   重新启动运行 BizTalk 主机实例的计算机上的 SSO 服务。  
>   -   SSO 主密钥发生更改。  
> 
>   如果重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上的 SSO 服务，或者如果 SSO 主密钥发生更改，将从内存中释放主密钥的缓存副本，并且 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须能够联系主密钥服务器，才可获取主密钥的另一个副本。 如果主密钥服务器不可用，则任何出于加密目的而需要访问主密钥服务器的管理操作都将失败。  
  
## <a name="making-the-master-secret-server-available"></a>确保主密钥服务器可用  
 为确保 SSO 系统的可用性（从而确保 BizTalk Server 环境可用），非常重要的一点是在生成主密钥后就对其进行备份。 如果您丢失主密钥，则会丢失 SSO 系统使用该主密钥加密的数据。 有关备份主密钥的详细信息，请参阅[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
 主密钥服务器有两种可用方式：  
  
-   **可用，但不是高度可用。** 所有 SSO 服务器都在内存中缓存有主密钥，即使主密钥服务器发生故障，运行时操作仍可继续进行。 但是，您不能更改端口配置或 SSO 配置。 BizTalk Server 运行时将继续正常工作，但您无法进行任何设计更改。  
  
     即使此配置并具备高可用性，但它还是可以满足大多数情况，而且与扩展接收、发送和处理主机的过程一致。  
  
-   **高度可用。** 若要为主密钥服务器提供冗余，请在单独的主密钥服务器群集上使用 Windows 群集，或者在现有数据库群集上配置主密钥服务器。 主密钥服务器提供的服务使用的资源不多，安装在数据库群集上时通常不会影响数据库的功能或性能。 下图显示了如何确保主密钥服务器高度可用：  
  
     ![高度可用的主密钥服务器](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
     尽管此配置具备高可用性，但它仍需要其他硬件资源。 有关高可用性 sso 安装选项的详细信息，请参阅[高可用性 SSO 安装选项](../core/high-availability-sso-installation-options.md)。 本部分包括有关将 SSO 主密钥服务器配置为 Windows Server 群集中高可用性群集资源的详细信息。  
  
    > [!NOTE]
    >  若要减少高可用性解决方案需要的硬件资源，则可将主密钥服务器添加为 SQL Server 群集中的群集资源。 不需要购买额外的 BizTalk Server 许可证，才能在另一台计算机上安装 SSO 服务。  
  
## <a name="see-also"></a>请参阅  
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)   
 [创建高度可用的 BizTalk Server 环境](../core/creating-a-highly-available-biztalk-server-environment.md)   
 [如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)