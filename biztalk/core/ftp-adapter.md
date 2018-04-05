---
title: FTP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FTP adapters
ms.assetid: 878dc0b0-d1d8-405a-a697-654dd18ba08e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc72b5166f8971392b41f275338bde593d325af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ftp-adapter"></a>FTP 适配器
FTP 适配器可在 FTP 服务器与 Microsoft BizTalk Server 之间交换数据，并可将存储在各种平台中的重要数据与业务流应用程序进行集成。 该适配器可以连接到 FTP 服务器通过 SOCKS4 或 SOCKS5 代理服务器。  
  
 FTP 适配器可将大量的文件从 FTP 服务器传输到 BizTalk Server。 它还可作为业务流程的一部分来传输文件。  
  
 FTP 适配器包含两个适配器-接收适配器和一个发送适配器。  

本部分将介绍 FTP 接收和发送适配器，以及有关安全性和最佳做法的信息。  
  
 ## <a name="receive-adapter"></a>接收适配器  
  
 使用 FTP 接收适配器，可以将数据从 FTP 服务器移至 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 主要功能包括：  
  
-   根据需要从 FTP 服务器请求文件  
  
-   根据可配置计划运行轮询  
  
-   对 FTP 服务器进行轮询并直接将数据发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   指定 FTP 服务器作为 IP 地址、端口、密码和主机名称  
  
-   确保文件送达  
  
     FTP 接收适配器还可与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台和 BizTalk 浏览器一起使用以配置和管理每个接收函数，这些接收函数由以下配置项组成：  
  
-   运行 FTP 命令的轮询间隔（例如，60 分钟）  
  
-   用于将文档路由到特定 BizTalk 发送端口或接收位置的信息  
  
> [!NOTE]
>  FTP 接收适配器不支持从已分区的数据集中接收文件。  
  
## <a name="send-adapter"></a>发送适配器  
  
 使用 FTP 发送适配器，可以将数据从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 移至 FTP 服务器。 主要功能包括：  
  
-   能够按需发送  
  
-   确保送达  
  
## <a name="supported-platforms"></a>支持的平台  
访问 FTP 服务器上的任何以下平台上存储的信息：  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)] 2016

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)] R2
  
-   [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
-   [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2008  
  
-   [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2000 Service Pack 3 (SP3) 和更高版本  
  
-   Sun Solaris 9.0  
  
-   HP-UX  
  
-   LINUX (Redhat 7.x)  
  
-   IBM z/OS v1.9 (MVS)  
  
-   运行 MVS 的 IBM O/S 390  
  
-   AS/400 OS/400 V5R1  
  
-   i5/OS V5R4 (AS400)  
  
-   i5/OS V6R1 (AS400)  
  
-   GXS ICS  
  
-   AIX  
  
 支持所有服务包，专门列出的服务包除外。  
  
## <a name="in-this-section"></a>本节内容  
  
[最佳做法和建议为 FTP 适配器](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[配置 FTP 适配器](../core/configuring-the-ftp-adapter.md)  

[FTP 适配器属性架构和属性](../core/ftp-adapter-property-schema-and-properties.md)