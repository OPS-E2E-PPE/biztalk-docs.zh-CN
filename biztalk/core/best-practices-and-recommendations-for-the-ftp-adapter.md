---
title: "最佳做法和建议为 FTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, FTP adapters
- FTP adapters, best practices
ms.assetid: f73b2016-d48c-48d8-9ba0-96e26b694d1e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85967756089be91939bf5b6f73b12d36ed8caa51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-and-recommendations-for-the-ftp-adapter"></a>最佳做法和建议为 FTP 适配器
阅读有关最佳实践、 安全建议，并增强功能的 FTP 适配器。

## <a name="best-practices"></a>最佳做法  
  
-   定期从临时文件夹中删除未完整接收的文件，以防止这些文件占用计算机资源以及可能造成的服务中断。  
  
-   如果使用流服务器，则在 MessageBox 数据库接收了整个文件后才允许对新文件进行读取访问。 如果使用 FTP 适配器向 MessageBox 数据库提交不完整的文件，则 MessageBox 数据库会成功存储该消息，但 FTP 适配器将无法从接收位置删除该不完整的消息。  
  
-   为确保 FTP 适配器接收处理程序的高可用性，FTP 适配器接收处理程序应配置为在群集 BizTalk 主机实例中运行。 有关详细信息请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  

## <a name="security-recommendations-and-tips"></a>安全建议和提示

BizTalk Server 可以从文件传输协议 (FTP) 服务器接收文件并将文件发送到 FTP 服务器的其他应用程序。 BizTalk Server 并不作为 FTP 服务器。  
  
 FTP 实际上并不安全：用户名、密码以及其他凭据均以明文形式在网络上传输。 同样，上载或下载的文件也是以明文形式传输的，并且可以在传输过程中轻易地查看和篡改。 此外，攻击者可以欺骗 FTP 服务器本身，称为恶意服务器攻击。 在这种情况下，您无法判断某特定的 FTP 服务器是否为您想进行通信的计算机。  
  
 若要解决这些问题，FTP 适配器支持 SSL/TLS 协议，以确保数据通过加密确保机密性。  
  
 有关使用 FTP 协议时的一般安全注意事项，请参阅[Internet 常见问题存档](http://go.microsoft.com/fwlink/p/?LinkId=24779)(http://go.microsoft.com/fwlink/p/?LinkId=24779)。   
  
 我们建议用于保护和部署你的环境中的 FTP 适配器使用以下准则：  

- 保护你服务器和限制访问的数据。 由于 FTP 协议不是安全协议，因此它易受攻击。 你可确保 FTP 服务器通过使用专用的连接，并将限制在服务器和 BizTalk Server 和 FTP 主机之间的连接的安全。 您也可以设置 FTP 服务器的安全策略以允许与 FTP 客户端的安全连接。  

- 将 FTP 适配器配置为使用安全套接字层 (SSL) 协议在适配器和 FTP 服务器之间进行通信。 SSL 协议通过加密可确保数据机密性。 这意味着会对用户 ID 和密码加密，而不以纯文本格式发送。 使用 FTP 适配器，您也可以加密 FTP 连接的数据通道。 请参阅**增强功能**（本主题中）。
  
-   若要实现安全的文件传输，配置 FTP 适配器所提供的 SSL 特定属性。 请参阅**增强功能**（本主题中）。 
  
-   FTP 适配器支持 FTP 请求 Comments (RFC) 959。 请参阅[World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?LinkId=24781) (http://go.microsoft.com/fwlink/p/?LinkId=24781)。 FTP 适配器不支持安全 FTP (SFTP) 协议。 请参阅[SFTP 适配器](../core/sftp-adapter.md)。
  
-   您可以跨防火墙使用 FTP 适配器。 根据你使用的防火墙的类型，你可能需要配置一个或多个以下的防火墙属性： 用户名、 密码、 计算机、 端口和防火墙类型 (无、 socks 4，socks 5)，和模式。  
  
-   我们建议你将远程 FTP 服务器放置在安全的位置。 您必须确保此服务器的物理安全和网络安全，以便将欺诈服务器攻击减到最少。  
  
-   FTP 适配器支持使用企业单一登录 (SSO)。 请参阅[实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)。  
  
-   默认情况下，FTP 接收适配器必须在 FTP 服务器中具有写入权限，因为适配器将在下载后从服务器中删除文件。 但是，FTP 适配器支持从只读位置的文件下载。 请参阅**增强功能**（本主题中）。
  
- 在使用 FTP 发送端口时，必须在配置发送端口时指定并存储用户 ID 和密码组合。 该适配器将使用此信息连接到 FTP 服务器。 用户凭据以纯文本格式存储在 SQL Server 数据库中。 在动态发送端口中，凭据将发送到 FTP 服务器。 如果生产环境要求较强的安全性，请对该服务器使用匿名凭据。  
  
-   当系统提示你的帐户时，我们建议你输入现有的用户帐户，而非本地系统帐户。 从而实现更好的安全性，并允许适配器以无人参与模式运行，而无需登录。  

## <a name="enhancements"></a>增强功能

### <a name="transferring-data-to-and-from-a-secure-ftp-server"></a>将数据和从安全的 FTP 服务器  
 FTP 适配器支持从 FTPS 服务器的文件传输，通过安全套接字层 (SSL) / 传输层安全 (TLS)。 SSL/TLS 可通过加密确保数据的保密性。 你必须通过配置适配器提供的 SSL 特有的属性来启用安全模式。 由于适配器允许从安全 FTP 服务器读取和写入数据，因此，SSL 特有的属性在配置发送处理程序/端口时可用，而且还可用于接收处理程序/位置。  

从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，FTP 适配器不再需要 SYST 命令： 

- **FTP 服务器类型**属性 – 设置此属性，以使用不需要 SYST 命令的服务器。
   
 以下选项可用于配置 SSL 特有的属性：  

-   **使用 SSL**属性 – 设置此属性，因此该 FTP 适配器必须为每个传输会话使用 SSL。  
  
-   **启用数据保护**属性 – 设置此属性以启用数据加密。 若要使此设置生效，FTPS 服务器的安全策略必须允许与适配器的安全 SSL 连接。  
  
-   **FTPS 连接模式**属性 – 将此属性来确定在激活安全设置：  
  
    -   在**隐式**模式下，安全将自动打开只要适配器连接到服务器。  
  
    -   在**Explicit**模式下，适配器发送命令以启动安全控制通道。  
  
> [!NOTE]
>  FTP 适配器不支持对服务器证书进行吊销检查。  
  
### <a name="support-for-downloading-files-from-locations-marked-as-read-only"></a>对从标记为只读的位置下载文件的支持  
FTP 适配器支持从只读的文件位置的文件的下载。 现在，适配器会在数据库中保留一个下载文件的列表。 对于下一次下载，会对 FTP 服务器上的文件列表与适配器保留的文件列表进行比较，仅下载服务器上的新文件。 若要支持其中的现有文件更新两个下载文件之间的方案，可以配置的适配器还通过设置来检查文件时间戳**启用比较时间戳**属性 FTP 接收位置。 在这种情况下，即使该文件将相同，但更新该时间戳，适配器将下载文件。  
  
 有时，FTP 服务器不支持将修改后的时间戳与文件关联。 在这种情况下，你可以通过适配器指定一个时间间隔，此间隔过后会再次下载该文件。 通过设置来配置此时间间隔**重新下载间隔**属性 FTP 接收位置。  
  
 下表列出了 FTP 适配器的预期的行为不同的值设置为**下载后删除**，**启用比较时间戳**和**重新下载间隔**属性。  
  
|下载后删除|启用时间戳比较|重新下载间隔|适配器行为|  
|---|---|---|---|  
|是|不适用|不适用|适配器在下载完某个文件后会从 FTP 服务器中将其删除。 这是适配器的默认行为。|  
|是|是|不适用|适配器不会在下载完某个文件后从 FTP 服务器中将其删除。 适配器会使用 MDTM 命令比较该文件的上次修改的时间戳。 适配器会再次下载该文件（具体取决于该时间戳）。|  
|是|是|适用|在指定的时间间隔过后，无论文件是否已修改，FTP 适配器都会从 FTP 服务器下载该文件。|  
  
### <a name="support-for-atomic-file-transfer-in-ascii-mode"></a>对 ASCII 模式下原子文件传输的支持  
 FTP 适配器支持 ASCII 模式下原子文件传输。 若要启用原子文件传输 ASCII 模式下的，适配器使用**临时文件夹**属性。 此属性定义 FTP 服务器上的一个临时位置，文件首先移至此位置。 在完全传输至该临时位置之后，文件会移动至 FTP 服务器上的相关位置。 此处的假设是，该临时位置与 FTP 服务器上的相关位置之间的文件传输是原子文件传输。  
  
> [!NOTE]
>  使用临时文件夹 ASCII 文件的扩展名是仅适用于**发送**，并不适用于**接收**。 实施此功能的主要原因在于，在某个文件被完全写入之前，第三方应用程序将无法读取该文件。 在 BizTalk 接收文件的情况下，适配器仅在该文件已完全读取后才会将其提交到 BizTalk。  
  
> [!NOTE]
>  在二进制模式下，**临时文件夹**属性还可以用于恢复文件传输，如果在此期间失败。 这不适用于 ASCII 模式。 对于 ASCII 模式，**临时文件夹**属性仅用于原子文件传输。  
  
 
## <a name="next"></a>Next 
[配置 FTP 适配器](../core/configuring-the-ftp-adapter.md)  

## <a name="see-also"></a>另请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)
