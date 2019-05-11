---
title: 文件适配器配置属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- File adapters, code sample
- receive locations, adapters
- File adapters, send ports
- File adapters, receive locations
- File adapters, properties
- send ports, adapters
ms.assetid: 53f4fd17-95b9-4861-b433-772b619e90c7
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d9319aa135e7e7dfbc6106f4103700e2822b5fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388052"
---
# <a name="file-adapter-configuration-properties"></a>文件适配器配置属性
下表列出了可以为文件适配器设置的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|RemoveReceivedFileRetryCount|VT_UI4|指定的文件适配器将尝试删除已读取并提交到 BizTalk Server 的文件的次数。|有效的值范围是从 0 到 100。|默认值为 5。|  
|RemoveReceivedFileMaxInterval|VT_UI4|指定文件适配器在尝试删除已读取并提交到 BizTalk Server 的文件前等待的毫秒数的初始时间间隔。|有效值为 1 到 1000年。|默认值为 10。|  
|FileMask|VT_BSTR|指定的文件掩码。|None|默认值为 *.xml。|  
|BatchSizeInBytes|VT_UI4|指定一批发送到 BizTalk MessageBox 的文件的最大总字节数。|有效的值为 1024年到 104857600。|默认值为 102400。|  
|PollingInterval|VT_UI4|指定以毫秒为单位的文件适配器将轮询新文件的指定的位置的间隔。|有效值从 1000年到 3600000。|设置为 1 将禁用轮询。|  
|BatchSize|VT_UI4|指定要在一批中提交的消息最大数量。|有效值为从 1 到 256。|默认值为 20。|  
|FileNetFailRetryInt|VT_UI4|指定两次尝试访问网络共享上的接收位置，如果暂时不可用之间的重试间隔时间 （以分钟为单位）。|有效值为从 0 到 4294967295。|默认值为 5。|  
|RemoveReceivedFileDelay|VT_UI4|指定文件适配器在尝试删除已读取并提交到 BizTalk Server 的文件前等待的毫秒数的初始时间间隔。|此时间间隔将增加一倍后每个重试间隔达到指定的最大重试间隔值。<br /><br /> 有效值为 1 到 1000年。|默认值为 10。|  
|RenameReceivedFiles|VT_BOOL|指定是否选择它们进行处理前，重命名文件。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0。|  
|FileNetFailRetryCount|VT_UI4|指定尝试访问网络共享上的接收位置，如果暂时不可用的次数。|有效值为从 0 到 4294967295。|默认值为 5。|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<RemoveReceivedFileRetryCount vt="19">5</RemoveReceivedFileRetryCount>  
<RemoveReceivedFileMaxInterval vt="19">300000</RemoveReceivedFileMaxInterval>  
<FileMask vt="8">*.xml</FileMask>  
<BatchSizeInBytes vt="19">102400</BatchSizeInBytes>  
<PollingInterval vt="19">60000</PollingInterval>  
<BatchSize vt="19">20</BatchSize>  
<FileNetFailRetryInt vt="19">5</FileNetFailRetryInt>  
<RemoveReceivedFileDelay vt="19">10</RemoveReceivedFileDelay>  
<RenameReceivedFiles vt="11">0</RenameReceivedFiles>  
<FileNetFailRetryCount vt="19">5</FileNetFailRetryCount>  
</CustomProps>  
```  
  
 下表列出了发送端口的文件适配器可以设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|用户名|VT_BSTR|如果文件适配器的主机实例不具有对网络共享所需的权限，请指定替代凭据。|None|指定的用户名的格式\<域\>\username。|  
|UseTempFileOnWrite|VT_BOOL|指定要写入到目标文件夹时使用临时文件。 完成文件写入已重命名为 Filename 属性指定的值。|此属性仅可以设置为-1 (true)，如果在 CopyMode 属性设置为值为 2 （新建）。<br /><br /> 有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|CopyMode|VT_UI4|定义向文件中写入一条消息时要使用的复制模式|有效值为<br /><br /> -0 （追加）<br />-1 （覆盖）<br />-2 （新建）|默认值为 2 （新建）。|  
|FileName|VT_BSTR|指定的文件发送处理程序写入消息的文件的名称。|有关限制对此属性的信息，请参阅[对文件掩码和文件名属性的限制](http://msdn.microsoft.com/library/d8f5afd0-a61f-4c9b-8a57-4792e3054769)。|默认值为 %messageid%.xml。|  
|AllowCacheOnWrite|VT_BOOL|指定是否使用文件系统缓存到文件中写入消息时。|有效值为<br /><br /> -0 （不使用缓存）<br />--1 (使用 caching)|默认值为的 0 （不使用缓存）。|  
|Password|VT_NULL|指定文件适配器的主机实例不包含所需的权限到网络共享时，与 Username 属性结合使用的密码。|此值始终设置为 null 时导出绑定文件。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|None|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<Username vt="8">Domainname\User</Username>  
<UseTempFileOnWrite vt="11">-1</UseTempFileOnWrite>  
<CopyMode vt="19">1</CopyMode>  
<FileName vt="8">%MessageID%.xml</FileName>  
<AllowCacheOnWrite vt="11">-1</AllowCacheOnWrite>  
<Password vt="1" />  
</CustomProps>  
```