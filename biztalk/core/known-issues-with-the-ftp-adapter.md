---
title: 已知问题的 FTP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e58f2db-9ec5-41fe-af02-9a7d60a217db
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13ce12e8514eaa2b5843ba81eff4f505e65d9e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010086"
---
# <a name="known-issues-with-the-ftp-adapter"></a>与 FTP 适配器的已知的问题
本部分包含可帮助你避免出现错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a>数据可能重复或丢失时通过使用 FTP 适配器中的 BizTalk Server 中接收数据  
  
##### <a name="problem"></a>问题  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中使用 FTP 适配器接收数据时，数据会重复或丢失。  
  
##### <a name="cause"></a>原因  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP 适配器使用 FTP 客户端协议轮询指定的 FTP 服务器，并“按原样”从服务器检索数据。 FTP 适配器不会对所检索的任何数据执行验证。 FTP 适配器只是将检索到的文档发送到 BizTalk 消息引擎以进行处理，然后从 FTP 服务器中删除原始文档。 如果 FTP 适配器从 FTP 服务器检索的文档仍在由主机应用程序进行写入，则检索到的文档将不完整。 如果 FTP 适配器检索到原始文档的不完整副本，则可能会发生数据重复或数据丢失的情况，如下所述：  
  
-   如果原始文档仍在由主机应用程序写入 FTP 服务器，则 FTP 适配器将无法删除该文档，并将在为接收位置配置的下一轮询间隔期间检索到该文档的另一个副本。 这一行为将导致出现文档重复。  
  
-   如果主机应用程序已完成将文档写入 FTP 服务器的过程，则该文档将被删除。 这一行为将导致出现数据丢失。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请使用以下方法之一：  
  
-   将主机应用程序配置成向公共 FTP 文件夹所在硬盘上的一个临时文件夹中进行写入，然后定期将临时文件夹的内容移动到 FTP 文件夹中。 临时文件夹应与公共 FTP 文件夹位于同一硬盘上，以确保移动操作为原子操作。 原子操作是功能上无法分割的操作。 如果您通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP 适配器将数据写入公共 FTP 文件夹，则配置发送端口时，可以通过在“FTP 传输属性”对话框中指定“临时文件夹”属性来实现。 如果指定“临时文件夹”属性，请确保此文件夹与公共 FTP 文件夹位于同一物理磁盘上。  
  
-   将 FTP 接收位置配置为在主机应用程序不向 FTP 服务器写入数据的服务时段执行操作。 可以在配置接收位置属性时指定该服务时段。  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a>FTP 适配器不支持对服务器证书执行吊销检查。  
  
##### <a name="problem"></a>问题  
 BizTalk Server 中的 FTP 适配器可以增强，以支持安全文件传输到和从 FTPS 服务器使用 SSL/TLS。 证书吊销列表 (CRL) 包含已吊销的及不再有效的证书列表。 FTP 适配器不能查阅 CRL 来对服务器证书进行身份验证。  
  
##### <a name="cause"></a>原因  
 按照设计，FTP 适配器不参考 CRL 再接受服务器证书。  
  
##### <a name="resolution"></a>解决方法  
 不不需要; 任何操作此行为是设计使然。  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a>FTP 适配器下载大于最大文件大小的文件  
  
##### <a name="problem"></a>问题  
 FTP 接收其大小大于指定的最大文件大小属性，从以下的 FTP 服务器的适配器下载文件：  
  
-   AIX  
  
-   MVS  
  
-   AS400  
  
-   GXS  
  
##### <a name="cause"></a>原因  
 按照设计，FTP 适配器不遵从最大文件大小，如果从这些 FTP 服务器下载文件。  
  
##### <a name="resolution"></a>解决方法  
 不不需要; 任何操作此行为是设计使然。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 FTP 接收位置](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3)   
 [故障排除 FTP 适配器](../core/troubleshooting-the-ftp-adapter.md)