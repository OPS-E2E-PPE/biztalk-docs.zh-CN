---
title: 对 BRE DB 连接进行加密 |Microsoft Docs
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
ms.openlocfilehash: a51d2468f31b316a9ab9ac2d8a3fa8ee57f11320
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997694"
---
# <a name="encrypt-the-connection-to-the-bre-database"></a>加密与 BRE 数据库的连接
根据你的公司的安全策略，请考虑加密：  
  
- 在登录过程中传输的凭据。  
  
- 业务规则引擎 (BRE) 策略在其中运行的客户端计算机和规则引擎数据库之间的网络传输的数据。  
  
  本主题介绍如何为 SQL Server 上托管的 BRE 数据库的连接进行加密。  
  
## <a name="encrypt-the-connection-to-the-bre-database"></a>加密与 BRE 数据库的连接
 默认情况下，当客户端应用程序连接到 SQL Server 时在登录过程中传输的凭据进行加密。 如果没有设置证书的服务器上，在启动时，SQL Server 将生成自签名的证书用于加密登录包。  
  
 若要支持的 SQL Server 实例的 SQL Server 和客户端之间跨网络传输的数据进行加密，应设置**强制加密**到服务器上的选项**是**或设置**强制协议加密**选项设为**是**客户端上。  
  
 当**强制加密**选项设置为**是**在服务器端 SQL Server 使用 SSL 来加密所有通信*之间的所有客户端和数据库服务器*. 换而言之，加密到服务器的所有传入连接。 若要在服务器启用此选项，建议您使用 SQL Server 配置管理器在服务器上安装证书。 如果在服务器上未安装证书，服务器自动生成自签名的证书时该实例已启动。  
  
 此自我签署的证书可代替受信任证书颁发机构颁发的证书使用，但不能抵御身份欺骗威胁的侵袭。 在生产环境中或在连接到 Internet 的服务器上，不应依赖使用自签名证书的 SSL。 该选项设置好之后，不支持加密的客户端将被拒绝访问。 在设置后必须重新启动 SQL Server**强制加密**选项。 可以通过使用 SQL Server 配置管理器 （SQL Server 网络配置） 来设置此选项。  
  
 当**强制协议加密**在客户端，SQL Server 使用 SSL 以加密所有通信设置*该客户端和所有服务器之间*。 换而言之，从客户端的所有传出连接进行加密。 若要启用此选项在客户端上的，您应证书如果服务器上安装**信任服务器证书**客户端上的选项设置为**否**。 如果**信任服务器证书**客户端上的选项设置为**是**，客户端不会验证服务器证书，而是使用自签名证书。 您可通过使用 SQL Server 配置管理器（SQL Native Client 配置）来设置此选项。  
  
 SQL Server 还允许您启用加密*客户端到服务器的特定连接*通过设置**加密/为使用加密数据**标记，用于**是**中连接字符串中。 不过，BRE 将自动生成连接字符串而不加密选项设置为**是**。 因此，您不能加密的特定连接到规则引擎数据库服务器从客户端计算机。 相反，应设置**强制协议加密**选项在客户端上一段中所述。