---
title: 使用 FTP 适配器的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 682e87e2cfca4906b0f9c582d5e33a235525e293
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329106"
---
# <a name="known-issues-with-the-ftp-adapter"></a>FTP 适配器的已知的问题
本部分包含可能帮助您避免错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a>数据可能会重复或丢失时通过使用 FTP 适配器，BizTalk Server 中接收数据  
  
##### <a name="problem"></a>问题  
 数据会重复或丢失时接收中的数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用 FTP 适配器。  
  
##### <a name="cause"></a>原因  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP 适配器使用 FTP 客户端协议轮询指定的 FTP 服务器，并从"按原样。"的服务器中检索数据 FTP 适配器不会验证它检索任何数据。 FTP 适配器将检索到的文档发送到 BizTalk 消息引擎进行处理，然后从 FTP 服务器中删除原始文档。 如果 FTP 适配器从 FTP 服务器仍被写入到主机应用程序检索文档，检索到的文档将不完整。 如果 FTP 适配器检索不完整的原始文档的副本，重复数据或数据丢失可能出现在以下方案中：  
  
-   如果原始文档仍正在由主机应用程序写入 FTP 服务器，FTP 适配器不能删除该文档，并将在下一个轮询间隔配置为接收位置检索文档的另一个副本。 此行为会导致出现文档重复。  
  
-   如果主机应用程序已完成将文档写入 FTP 服务器，将删除文档。 此行为将导致出现数据丢失。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请使用以下方法之一：  
  
- 配置主机应用程序要写入到临时文件夹与公共 FTP 文件夹位于同一硬盘上，并定期将临时文件夹的内容移动到 FTP 文件夹。 临时文件夹应与公共 FTP 文件夹，以确保移动操作为原子同一硬盘上。 以原子操作是功能上无法分割的操作。 如果您数据写入公共 FTP 文件夹使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]FTP 适配器，您可以执行此操作通过在 FTP 传输属性对话框中指定临时文件夹属性时，发送端口配置。 如果您指定的临时文件夹属性，请确保此文件夹与公共 FTP 文件夹位于同一个物理磁盘上。  
  
- 配置 FTP 接收位置主机应用程序不向 FTP 服务器写入数据时运行的服务时段。 在配置的接收位置属性时，可以指定服务时段。  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a>FTP 适配器不支持对服务器证书的吊销检查  
  
##### <a name="problem"></a>问题  
 FTP 适配器在 BizTalk Server 中的得到了增强，可支持安全文件传输到和从 FTPS 服务器使用 SSL/TLS。 证书吊销列表 (CRL) 包含一系列已被吊销，并且将不再有效的证书。 FTP 适配器不能查阅 CRL 进行身份验证服务器证书。  
  
##### <a name="cause"></a>原因  
 根据设计，FTP 适配器不能查阅 CRL 再接受服务器证书。  
  
##### <a name="resolution"></a>解决方法  
 必需的; 不不执行任何操作此行为是默认设置。  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a>FTP 适配器下载大于最大文件大小的文件  
  
##### <a name="problem"></a>问题  
 FTP 接收适配器的下载文件的大小大于指定的最大文件大小属性，从以下的 FTP 服务器：  
  
-   AIX  
  
-   MVS  
  
-   AS400  
  
-   GXS  
  
##### <a name="cause"></a>原因  
 按照设计，FTP 适配器不会接受的最大文件大小，如果从这些 FTP 服务器下载文件。  
  
##### <a name="resolution"></a>解决方法  
 必需的; 不不执行任何操作此行为是默认设置。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 FTP 接收位置](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3)   
 [FTP 适配器故障排除](../core/troubleshooting-the-ftp-adapter.md)