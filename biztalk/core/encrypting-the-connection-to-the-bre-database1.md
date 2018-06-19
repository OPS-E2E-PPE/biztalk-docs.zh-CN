---
title: 加密 BRE DB 连接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63edd2bb-97f1-4b8b-8cdc-f4792909ca86
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b3891ef72b5b1aeba42bce1586ee9c73aa29408
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005654"
---
# <a name="encrypt-the-connection-to-the-bre-database"></a>加密 BRE 数据库的连接
根据你的公司的安全策略，请考虑加密：  
  
-   在登录过程中传输凭据。  
  
-   业务规则引擎 (BRE) 策略在其中运行的客户端计算机和规则引擎数据库之间跨网络传输的数据。  
  
 本主题介绍如何加密到 SQL Server 上托管的 BRE 数据库的连接。  
  
## <a name="encrypt-the-connection-to-the-bre-database"></a>加密 BRE 数据库的连接
 默认情况下，当客户端应用程序连接到 SQL Server 时，在登录过程中传输的凭据进行加密。 如果没有提供的证书的服务器上，启动时，SQL Server 会生成自签名的证书用于加密登录数据包。  
  
 若要启用加密的 SQL Server 和客户端之间跨网络传输的 SQL Server 实例的数据，应设置**强制加密**到服务器上的选项**是**或设置**强制协议加密**选项设为**是**客户端上。  
  
 当**强制加密**选项设置为**是**在服务器端中，SQL Server 使用 SSL 来加密所有的通信*所有客户端和数据库服务器之间*. 换而言之，到服务器的所有传入连接进行加密。 若要在服务器启用此选项，建议您使用 SQL Server 配置管理器在服务器上安装证书。 如果在服务器上未安装证书，服务器自动生成自签名的证书时该实例已启动。  
  
 此自我签署的证书可代替受信任证书颁发机构颁发的证书使用，但不能抵御身份欺骗威胁的侵袭。 在生产环境中或在连接到 Internet 的服务器上，不应依赖使用自签名证书的 SSL。 该选项设置好之后，不支持加密的客户端将被拒绝访问。 在设置后必须重新启动 SQL Server**强制加密**选项。 通过使用 SQL Server 配置管理器 （SQL Server 网络配置），可以设置此选项。  
  
 当**强制协议加密**在客户端一侧，SQL Server 使用 SSL 来加密所有的通信设置*该客户端和服务器之间*。 换而言之，从客户端的所有传出连接进行加密。 若要启用此选项在客户端，你应服务器上安装证书如果**信任服务器证书**客户端上的选项设置为**否**。 如果**信任服务器证书**客户端上的选项设置为**是**，客户端不会验证服务器证书，从而支持自签名证书的使用。 您可通过使用 SQL Server 配置管理器（SQL Native Client 配置）来设置此选项。  
  
 SQL Server 还允许你要启用对加密*从客户端到服务器的特定连接*通过设置**Encrypt/使用加密数据**标志切换为**是**中连接字符串中。 但是，bre 还会自动生成的连接字符串而无需将加密选项设置为**是**。 因此，您不能加密特定的连接到规则引擎的数据库服务器从客户端计算机。 相反，应设置**强制协议加密**选项客户端上一段中所述。