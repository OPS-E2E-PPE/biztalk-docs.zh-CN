---
title: "配置 FTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FTP adapters, configuring
- configuring [FTP adapters]
ms.assetid: 7e7d2e2d-142e-4459-be25-efd501b396d2
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203f6b7ce49dfba26c4883d5b26afee6bcc82f49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-ftp-adapter"></a>配置 FTP 适配器


## <a name="before-you-begin"></a>开始之前
- FTP 适配器支持从安全 FTP 服务器读取和写入数据。 该适配器提供了对使用安全套接字层 (SSL)/传输层安全性 (TLS) 从 FTP 服务器传输文件的支持。 
- FTP 适配器支持从只读的文件位置的文件下载。 
- FTP 适配器还支持为 ASCII 模式下的原子文件传输。

请参阅[最佳做法和建议为 FTP 适配器](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)。


## <a name="configure-the-receive-location"></a>配置接收位置

你可以设置 FTP 接收 BizTalk Server 管理控制台中的位置适配器属性。 如果不在接收位置设置属性，然后使用 BizTalk Server 管理控制台中的默认接收处理程序值。  
  
> [!NOTE]
>  之前完成以下过程，你必须已添加接收端口。 请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你要在其中创建接收位置的应用程序。  
  
2.  在左窗格中，单击**接收端口**节点。 在右窗格中，右键单击与现有的接收位置相关联的接收端口或你想要与新的接收位置，相关联，然后单击**属性**。  
  
3.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**。 在右窗格中，双击现有接收位置或单击**新建**创建一个新接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**FTP**从下拉列表和然后单击**配置**。  
  
5.  在**FTP 传输属性**，执行以下操作：  

    **批处理**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**最大文件数**|指定每个 BizTalk Server 批的最大文件数。<br /><br /> 零 (0) 表示没有限制。<br /><br /> **默认值：** 0|  
    |**最大大小**|指定每个 BizTalk Server 批的最大字节数。<br /><br /> 零 (0) 表示没有限制。<br /><br /> **默认值：** 0|  
    
    **防火墙**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|     
    |**Address**|指定的防火墙，DNS 名称或 IP 地址的地址。|  
    |**模式**|指定适配器连接到 FTP 服务器的模式。<br /><br /> **有效值：**被动并处于活动状态<br /><br /> 在主动模式中，FTP 服务器连接到由 FTP 适配器打开的端口。 在被动模式中，FTP 适配器连接到由 FTP 服务器打开的端口。<br /><br /> **默认值：** Active|  
    |**密码**|指定防火墙的密码。|  
    |**端口**|指定防火墙的端口。<br /><br /> **有效值：** 1 到 65535 之间 （含）<br /><br /> **默认值：** 21|  
    |**类型**|指定部署的防火墙的类型。<br /><br /> **有效值：** None、 Socks 4 和 Socks 5<br /><br /> **默认值：**无|  
    |**用户**|指定防火墙的用户名。|  
    
    **FTP**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|      
    |**帐户**|指定 FTP 服务器的帐户名。 此选项已弃用并建议不要使用此属性。|  
    |**Get 后**|指定在 GET 文件后要运行的 FTP 命令。 用分号 (;) 分隔命令。|  
    |**Get 之前**|指定在 GET 文件前要运行的 FTP 命令。 用分号 (;) 分隔命令。 **注意：** QUIT 命令文件 GET 之前不受支持。|  
    |**错误阈值**|指定 BizTalk Server 可能会遇到的错误数禁用该位置之前。<br /><br /> **默认值：** 10|  
    |**文件掩码**|指定传输文件时使用的文件掩码筛选器。|  
    |**文件夹**|指定 FTP 服务器上的轮询位置。|      
    |**FTP 服务器类型** | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 <br/><br/>此属性用于选择不需要 SYST 命令的 FTP 服务器。 选项为 None、 AIX、 检测、 GXS、 MVS、 OS400，和其他。 <br/><br/>如果设置为**无**，使用 SYST 命令。 **其他**的 OS 类型不适合的任何指定的类别时使用。 <br /><br /> **默认值：**无|    
    |**日志**|指定要保存日志文件的副本的位置。 此文件用于诊断发送或接收通过 FTP 文件时的错误条件。|  
    |**最大文件大小**|指定可下载文件的最大大小 (MB)。<br /><br /> 零 (0) 表示对文件大小没有限制。<br /><br /> **默认值：** 100|  
    |**密码**|指定登录 FTP 服务器所用的用户密码。|  
    |**端口**|指定此 FTP 服务器的端口地址。<br /><br /> **默认值：** 21|  
    |**表示形式**|选择 FTP 接收数据的方式。<br /><br /> **有效值：**二进制或 ASCII<br /><br /> **默认值：**二进制|  
    |**Server**|指定 FTP 服务器的服务器名称或 IP 地址。 **注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**SSO 关联**|指定企业单一登录关联应用程序。|  
    |**使用名称列表 (NLST)**|指定适配器如何列出文件。 若要访问文件名称，而不是系统定义的文件列表，请将此值设置为“是”。<br /><br /> **默认值：**否|  
    |**用户名**|指定登录 FTP 服务器所用的用户名。|  
    
    **轮询**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|         
    |**在下载后删除**|指定下载后适配器是否从 FTP 服务器中删除文件。<br /><br /> **默认值：**是**注意：**|  
    |**启用比较时间戳**|指定适配器是否根据其修改后的时间戳再次下载文件。 在情况下如果适配器不在 FTP 服务器上，具有删除权限 MDTM （修改时间） 命令将允许要知道自上次下载以来是否已修改一个文件的适配器。  根据此属性的值，将再次下载文件。<br /><br /> **默认值：**否**注意**： 以防 FTP 服务器不支持 MDTM，设置**重新下载间隔**属性。 **注意：**此属性是适用时，才**下载后删除**设置为 no。|  
    |**间隔**|指定轮询此位置的时间间隔。 若要持续轮询，请设置此值为零 (0)。<br /><br /> **默认值：** 60|  
    |**重新下载间隔**|指定的间隔后适配器文件将再次下载。 此属性是适用的仅当同时**下载后删除**和**启用比较时间戳**设置为 no。<br /><br /> **默认值：** -1<br /><br /> 为-1 指示该适配器将再次下载文件。<br /><br /> 0 表示适配器将在每个轮询周期中下载该文件。|  
    |**单元**|指定的单位类型**间隔**和**重新下载间隔**属性。<br /><br /> **有效值：**秒、 分钟、 小时和天<br /><br /> **默认值：**秒|  
    
    **SSL**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|
    |**客户端证书哈希**|指定安全套接字层 (SSL) 协商中必须使用的客户端证书的 SHA1 哈希。<br /><br /> 基于此哈希，从运行 BizTalk 主机实例的用户帐户的个人存储中提取客户端证书。|  
    |**FTPS 连接模式**|指定到 FTPS 服务器的 SSL 连接模式。<br /><br /> **有效值：**隐式或显式<br /><br /> **默认值：**显式|  
    |**使用数据保护**|如果适配器在从 FTPS 服务器发送和接收数据文件时必须使用 SSL 加密，则将此值指定为“是”。 如果适配器发送和接收纯文本的数据文件，则将此指定为“否”。 **注意：**此属性是适用才**使用 SSL**属性设置为是。 <br /><br /> **有效值：**是或否<br /><br /> **默认值：**是|  
    |**使用 SSL**|指定 FTP 适配器是否必须使用 SSL 与 FTPS 服务器通信。<br /><br /> **有效值：**是或否<br /><br /> **默认值：**否|  
    
    **优化参数**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|     
    |**接收数据超时**|指定接收调用将中止之前的时间（以毫秒为单位）。 使用此属性以防止慢速服务器导致接收位置停止响应。<br /><br /> **默认值：** 90000|  
    |**临时文件夹**|指定临时文件夹的位置。 可以使用此位置确保能够从传输失败中恢复。|  
  
6.  单击**确定**以保存设置。  
  
7.  在**接收位置属性**对话框框中，输入适当的值，以完成接收位置的配置，然后单击**确定**以保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
> [!NOTE]
>  不要将多个 FTP 接收位置配置为轮询同一 FTP URL。 如果多个 FTP 接收位置同时轮询同一 URL，则每个接收位置都可以接收该文件的副本，而这将会导致数据重复。 由于 FTP 协议在从目标 URL 中读取文件时无法将其锁定，因此会发生这种情况。  
>   
>  为了提供高可用性 FTP 接收适配器，则应配置 FTP 接收适配器的群集的 BizTalk 主机实例中运行。 请参阅[运行在群集主机内的适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  

## <a name="configure-the-send-port"></a>配置发送端口

在 BizTalk Server 管理控制台中，可以设置 FTP 发送端口适配器属性。 如果没有为发送端口设置属性，默认值将发送处理程序使用 BizTalk Server 管理控制台中的值。  
  
1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击现有的发送端口来对其进行修改。 请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项，然后在**传输**部分**常规**页上，指定**FTP**为**类型**选项。  
  
2.  上**常规**页上，在**传输**部分中，单击**配置**按钮旁边**类型**。  
  
3.  在**FTP 传输属性**，执行以下操作：  
  
    **防火墙**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|    
    |**Address**|指定的防火墙，DNS 名称或 IP 地址的地址。|  
    |**模式**|选择适配器连接到 FTP 服务器的模式。<br /><br /> **有效值：**被动并处于活动状态<br /><br /> 在主动模式中，FTP 服务器连接到由 FTP 适配器打开的端口。 在被动模式中，FTP 适配器连接到由 FTP 服务器打开的端口。<br /><br /> **默认值：** Active|  
    |**密码**|指定防火墙的密码。|  
    |**端口**|指定防火墙的端口。<br /><br /> **有效值：** 1 到 65535 之间 （含)<br /><br /> **默认值：** 21|  
    |**类型**|选择部署的防火墙的类型。<br /><br /> **有效值：** Socks 4、 Socks 5、 无<br /><br /> **默认值：**无|  
    |**用户**|指定防火墙的用户名。|  
    
    **FTP**
    
    |使用此选项|执行的操作|  
    |--------------|----------------| 
    |**帐户**|可选。 指定 FTP 服务器的帐户名。 不赞成使用此选项，建议不要使用此属性。|  
    |**Put 后**|指定在 PUT 文件后要运行的 FTP 命令。 用分号 (;) 分隔命令。|  
    |**将存储分配**|指定是否为旧式主机系统分配存储空间。 此属性可以向后兼容。<br /><br /> **有效值：**否和是<br /><br /> **默认值：**否|  
    |**在 Put 之前**|指定在 PUT 文件之前要运行的 FTP 命令，例如，用于在 FTP 服务器上更改默认值的命令。 用分号 (;) 分隔命令。 不需要 open 命令。 **注意：** QUIT 命令文件 PUT 之前不受支持。|  
    |**文件夹**|指定将文件移至 FTP 服务器上的位置。|      
    |**FTP 服务器类型** | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。 <br/><br/>此属性用于选择不需要 SYST 命令的 FTP 服务器。 选项为 None、 AIX、 检测、 GXS、 MVS、 OS400，和其他。 <br/><br/>如果设置为**无**，使用 SYST 命令。 **其他**的 OS 类型不适合的任何指定的类别时使用。 <br /><br /> **默认值：**无|  
    |**日志**|指定保存日志文件副本的位置。 此文件用于在通过 FTP 适配器发送或接收文件时诊断错误情况。|  
    |**密码**|指定登录 FTP 服务器所用的密码。|  
    |**端口**|指定 FTP 服务器的端口地址。<br /><br /> **默认值：** 21|  
    |**表示形式**|选择 FTP 适配器如何发送数据，“二进制”还是“ASCII”。<br /><br /> **有效值：**二进制或 ASCII<br /><br /> **默认值：**二进制|  
    |**Server**|指定 FTP 服务器的服务器名称或 IP 地址。|  
    |**SSO 关联**|指定企业单一登录关联应用程序。|  
    |**目标文件名**|指定文件的替换名称。 保留默认名称保证唯一的消息的发送每条消息的名称。<br /><br /> **默认值：** %MessageID%.xml|  
    |**用户名**|指定登录 FTP 服务器所用的用户名。|  
    
    **SSL**
    
    |使用此选项|执行的操作|  
    |--------------|----------------|
    |**客户端证书哈希**|指定安全套接字层 (SSL) 协商中必须使用的客户端证书的 SHA1 哈希。<br /><br /> 基于此哈希，从运行 BizTalk 主机实例的用户帐户的个人存储中提取客户端证书。|  
    |**FTPS 连接模式**|指定到 FTPS 服务器的 SSL 连接模式。<br /><br /> **有效值：**隐式或显式<br /><br /> **默认值：** Explicit|  
    |**使用数据保护**|如果适配器在从 FTPS 服务器发送和接收数据文件时必须使用 SSL 加密，则将此值指定为“是”。 如果适配器发送和接收纯文本的数据文件，则将此指定为“否”。 **注意：**此属性是适用才**使用 SSL**属性设置为是。 <br /><br /> **有效值：**是或否<br /><br /> **默认值：**是|  
    |**使用 SSL**|指定 FTP 适配器是否必须使用 SSL 与 FTPS 服务器通信。<br /><br /> **有效值：**是或否<br /><br /> **默认值：**否|  
    
    **优化参数**
    
    |使用此选项|执行的操作|  
    |--------------|----------------| 
    |**连接限制**|指定服务器允许的并行打开的最大 FTP 连接数。 0 表示无限制。<br /><br /> **默认值：** 0**注意：**此属性将替换的注册表条目，在早期版本的 BizTalk Server 中用于控制连接限制。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将忽略用于控制连接限制的注册表项。|  
    |**临时文件夹**|指定 FTP 服务器上的临时文件夹的位置。 在此处第一次上载文件，然后将其移动到目标 FTP 文件夹。 如果传输失败，适配器将以 ASCII 传输模式重新开始文件上载，并以二进制传输模式恢复。 **注意：**如果原子的临时位置和 FTP 服务器上的相关位置之间进行文件传输时，则文件上载为还原子性。|  
  
4.  单击**确定**和**确定**再次以保存设置。   


## <a name="ftp-commands-required-by-the-ftp-adapter"></a>FTP 适配器所需的 FTP 命令  
FTP 适配器受 FTP 协议的限制，并需要某些 FTP 命令在源或目标 FTP 服务器上可用。  

FTP 适配器作为 FTP 客户端操作，可能需要才能正常工作的 FTP 服务器上有下列命令： 
 
|Command  |需要由接收  |所需的发送  |
|---------|---------|---------|
|SYST | ✔ <br/><br/>可选开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] | ✔<br/><br/>可选开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] |
| 应用商店 | |✔|
| RETR | ✔ | |
| User |✔ | ✔ |
| PASS | ✔ | ✔ |
| CWD |✔ | ✔ |
| QUIT |✔ | ✔ |
| PORT | ✔ | ✔ |
| PASV | ✔ | ✔ |
| ABOR | ✔ | ✔ |
| TYPE | ✔ | ✔ |
| RNFR | ✔ | ✔ |
| RNTO | ✔ | ✔ |
| DELE | ✔ | ✔ | 
| PWD | ✔ | ✔ |
| LIST | ✔ | ✔ |
| NLST | ✔ | ✔ |
| NOOP | ✔ | ✔ |
| APPE |  | ✔ |
| ALLO | ✔ | ✔ |
| MDTM | ✔ | |
| AUTH TLS | ✔ | ✔ | 
| PBSZ | ✔ | ✔ | 
| PROT | ✔ | ✔ |

 有关这些 FTP 命令的详细信息，请参阅：  
  
-   [RFC 959-文件传输协议](http://go.microsoft.com/fwlink/p/?LinkId=119603)(http://go.microsoft.com/fwlink/p/?LinkId=119603)  
  
-   [RFC 4217-具有 TLS 的保护 FTP](http://go.microsoft.com/fwlink/p/?LinkId=183154) (http://go.microsoft.com/fwlink/p/?LinkId=183154)  
  
-   [RFC 3659-FTP 扩展](http://go.microsoft.com/fwlink/p/?LinkId=183155)(http://go.microsoft.com/fwlink/p/?LinkId=183155)  
  
## <a name="configuring-an-ftp-adapter-to-work-with-legacy-hosts"></a>配置 FTP 适配器可以使用旧主机

本部分介绍你需要知道便于 FTP 适配器和大型机计算机之间进行通信。   
> [!NOTE]
>  向 MVS 或 AS400 主机发送文件时，无法使用临时文件夹功能。 此字段中的输入不受支持，并将导致错误。  
  
> [!IMPORTANT]
>  以下信息仅供指导性参考，如有冲突，请以 AS400 或 IBM 文档中的信息为准。  
  
## <a name="mvs"></a>MVS  
 若要向大型机中的 FTP 服务器发送文件，该大型机必须支持 IBM Generation Data Group（GDG，世代数据组）。 在名称字段中，每个文件名都会向目标文件名（包含在引号中的完整路径）附加 (+1)。  
  
## <a name="as400"></a>AS400  
 与 AS400 系统之间传输文件时，可以使用三种方法对文件进行命名并定义其路径：  
  
-   **Filename 字段**： 时的文件发送到 FTP 服务器，输入中的文件名称**Filename**字段。 文件名必须符合 AS400 系统的文件命名约定，因为文件将存储在该库文件系统中。  
  
-   **Quote 命令**： 使用引号命令在远程计算机上运行脚本。 输入报价命令到**之前获取**，**之前将**，**后获取**，和**后放置**上的任何终结点的字段。 请按以下格式输入 Quote 命令：  
  
    ```  
    QUOTE RCMD <command to be run on the remote system>.  
    ```  
  
-   **集成文件系统 (IFS)**: IFS 是允许对存储的基于 PC 的文件，因此相同的命名约定为单 PC AS400 系统上的区域。 若要用 IFS 代替默认库文件系统，输入的第一个命令应为 `quote site namefmt 1`。 此命令将通知 AS400 系统使用 IFS 命名约定。    

   
## <a name="more-good-stuff"></a>更多有用内容
  
[FTP 适配器属性架构和属性](../core/ftp-adapter-property-schema-and-properties.md)  

[最佳做法和建议为 FTP 适配器](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[FTP 适配器](../core/ftp-adapter.md)