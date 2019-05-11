---
title: 最佳做法和 FTP 适配器的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, FTP adapters
- FTP adapters, best practices
ms.assetid: f73b2016-d48c-48d8-9ba0-96e26b694d1e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4e9667b71af44089bfa8bf84a2b5f78dcfb244d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358412"
---
# <a name="best-practices-and-recommendations-for-the-ftp-adapter"></a>最佳做法和 FTP 适配器的建议
阅读有关最佳实践、 安全建议和 FTP 适配器的增强功能。

## <a name="best-practices"></a>最佳做法  
  
-   定期从使用计算机资源，并可能会中断服务保留文件的临时文件夹中删除未完整接收的文件。  
  
-   在使用流式处理服务器，拒绝读取访问权限的新文件，直到 MessageBox 数据库接收了整个文件。 如果 FTP 适配器部分文件提交到 MessageBox 数据库，MessageBox 数据库已成功存储该消息，但 FTP 适配器将无法再从接收位置删除该部分的消息。  
  
-   若要确保高可用性，FTP 适配器的接收处理程序，FTP 适配器接收处理程序应将配置为运行在群集 BizTalk 主机实例中。 有关详细信息请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  

## <a name="security-recommendations-and-tips"></a>安全建议和提示

BizTalk Server 可以从文件传输协议 (FTP) 服务器接收文件并将文件发送到 FTP 服务器的其他应用程序。 BizTalk Server 并不作为 FTP 服务器。  
  
 FTP 是本质上不安全的：用户名、 密码和其他凭据遍历网络以明文形式。 同样，文件上传或下载以明文形式在之间移动，可轻松地查看或篡改此过程。 此外，攻击者可以欺骗 FTP 服务器本身，称为恶意服务器攻击。 在这种情况下无法判断特定的 FTP 服务器是否确实想进行通信的计算机。  
  
 若要解决这些问题，FTP 适配器支持 SSL/TLS 协议，以确保数据通过加密确保机密性。  
  
 有关使用 FTP 协议时的一般安全注意事项，请参阅[Internet 常见问题存档](http://go.microsoft.com/fwlink/p/?LinkId=24779)(http://go.microsoft.com/fwlink/p/?LinkId=24779)。   
  
 我们建议用于保护和部署你的环境中的 FTP 适配器的以下准则：  

- 保护你服务器和限制访问的数据。 由于 FTP 协议不安全的协议，它将始终为易受攻击。 您可以确保 FTP 服务器通过使用专用的连接，并限制服务器和 BizTalk Server 与 FTP 主机之间的连接的安全。 此外可以设置 FTP 服务器，以便用于与 FTP 客户端的安全连接的服务器的安全策略。  

- 配置 FTP 适配器在适配器和 FTP 服务器之间的通信使用安全套接字层 (SSL) 协议。 SSL 协议可确保通过加密的数据保密性。 这意味着用户 Id 和密码进行加密和不会以明文形式发送。 使用 FTP 适配器，您还可以选择 FTP 连接的数据通道进行加密。 请参阅**增强功能**（在本主题中）。
  
-   若要实现安全文件传输，配置 FTP 适配器提供的 SSL 特有的属性。 请参阅**增强功能**（在本主题中）。 
  
-   FTP 适配器支持 FTP 征求意见 (RFC) 959。 请参阅[万维网联合会 (W3C)](http://go.microsoft.com/fwlink/p/?LinkId=24781) (http://go.microsoft.com/fwlink/p/?LinkId=24781)。 FTP 适配器不支持安全 FTP (SFTP) 协议。 请参阅[SFTP 适配器](../core/sftp-adapter.md)。
  
-   你可以跨防火墙使用 FTP 适配器。 根据所使用的防火墙类型，您可能必须配置一个或多个以下的防火墙属性： 用户名、 密码、 计算机、 端口、 防火墙类型 （无、 socks 4，5），和模式。  
  
-   我们建议将远程 FTP 服务器放在安全的位置。 你必须确保物理和网络安全性的最大程度减少恶意服务器攻击此服务器。  
  
-   FTP 适配器支持使用的企业单一登录 (SSO)。 请参阅[实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)。  
  
-   默认情况下，FTP 接收适配器必须具有写入权限在 FTP 服务器中因为适配器从服务器下载后删除该文件。 但是，FTP 适配器支持从只读位置下载文件。 请参阅**增强功能**（在本主题中）。
  
- 当使用 FTP 发送端口时，必须指定并配置发送端口时存储用户 ID 和密码组合。 适配器使用此信息以连接到 FTP 服务器。 在 SQL Server 数据库以纯文本形式存储用户凭据。 在动态发送端口中，将凭据发送到 FTP 服务器。 如果生产环境要求较强的安全性，则使用匿名凭据到服务器。  
  
-   当系统提示您输入一个帐户时，我们建议你输入现有的用户帐户，而不是本地系统帐户。 这使您能够实现更佳的安全性，并允许适配器运行在无人参与模式下，无需登录。  

## <a name="enhancements"></a>增强功能

### <a name="transferring-data-to-and-from-a-secure-ftp-server"></a>将数据传入和从安全 FTP 服务器  
 FTP 适配器支持从 FTPS 服务器的文件传输通过安全套接字层 (SSL) / 传输层安全 (TLS)。 SSL/TLS 可确保通过加密的数据保密性。 通过配置适配器提供的 SSL 特有的属性，必须启用安全模式。 由于适配器允许读取和写入数据，从安全 FTP 服务器，SSL 特有的属性可配置发送处理程序/端口时，还可用于接收处理程序/位置。  

从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，FTP 适配器不再需要 SYST 命令： 

- **FTP 服务器类型**属性 – 设置此属性以使用不需要 SYST 命令的服务器。
   
  配置 SSL 特有的属性有以下选项：  

- **使用 SSL**属性 – 设置此属性，因此该 FTP 适配器必须为每个传输会话使用 SSL。  
  
- **启用数据保护**属性 – 设置此属性以启用数据加密。 FTPS 服务器的安全策略必须允许与使此设置，若要运行中的适配器的安全 SSL 连接。  
  
- **FTPS 连接模式**属性 – 设置此属性以确定何时激活安全性：  
  
  -   在中**隐式**模式下，安全将自动打开只要适配器连接到服务器。  
  
  -   在中**Explicit**模式下，适配器发送命令，以启动安全控制通道。  
  
> [!NOTE]
>  FTP 适配器不支持对服务器证书的吊销检查。  
  
### <a name="support-for-downloading-files-from-locations-marked-as-read-only"></a>支持，用于从位置下载文件标记为只读的  
FTP 适配器支持从只读文件位置的文件的下载。 适配器现在保留在数据库中的已下载文件的列表。 下一步的下载，FTP 服务器上的文件列表进行比较的适配器，保留的文件的列表并下载服务器上的新文件。 若要支持其中两个下载之间更新现有的文件的情况下，可以配置适配器设置，还检查文件时间戳**启用时间戳比较**属性 ftp 接收位置。 在这种情况下，即使文件名称相同但时间戳更新时，适配器将下载的文件。  
  
 有时在 FTP 服务器不支持将修改后的时间戳与文件相关联。 在这种情况下，该适配器，可指定的间隔之后将再次下载文件。 通过设置来配置此间隔**重新下载时间间隔**属性 ftp 接收位置。  
  
 下表列出了 FTP 适配器的预期的行为，不同的值设置为**下载后删除**，**启用时间戳比较**和**重新下载时间间隔**属性。  
  
|下载后删除|启用时间戳比较|重新下载时间间隔|适配器行为|  
|---|---|---|---|  
|是|不适用|不适用|适配器下载后从 FTP 服务器中删除的文件。 这是适配器的默认行为。|  
|否|是|不适用|适配器不会删除文件从 FTP 服务器下载后。 而是适配器比较文件的上次修改时间戳使用 MDTM 命令。 具体取决于时间戳，适配器会再次下载该文件。|  
|否|否|适用|FTP 适配器指定，而不考虑是否在文件已被修改或不的时间间隔后从 FTP 服务器上下载文件。|  
  
### <a name="support-for-atomic-file-transfer-in-ascii-mode"></a>对在 ASCII 模式下原子文件传输的支持  
 FTP 适配器支持 ASCII 模式的原子文件传输。 若要启用 ASCII 模式的原子文件传输，则适配器将使用**临时文件夹**属性。 此属性定义文件首先移至 FTP 服务器上的临时位置。 文件已完全传输到临时位置后，该文件然后移动到相关位置上 FTP 服务器。 此处的假设是，文件传输是原子的临时位置与 FTP 服务器上的相关位置之间。  
  
> [!NOTE]
>  使用 ASCII 文件临时文件夹的扩展名是仅适用于**发送**，并不适用于**接收**。 实现此功能的主要原因是，第三方应用程序将读取文件被完全写入之前。 对于 BizTalk 接收文件，适配器将提交到 BizTalk 文件只有在完全读取后。  
  
> [!NOTE]
>  在二进制模式下**临时文件夹**属性还可用于恢复文件传输，如果其间故障。 这不适用于 ASCII 模式。 对于 ASCII 模式**临时文件夹**属性仅用于原子文件传输。  
  
 
## <a name="next"></a>Next 
[配置 FTP 适配器](../core/configuring-the-ftp-adapter.md)  

## <a name="see-also"></a>请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)
