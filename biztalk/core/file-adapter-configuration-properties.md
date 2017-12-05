---
title: "文件适配器配置属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- File adapters, code sample
- receive locations, adapters
- File adapters, send ports
- File adapters, receive locations
- File adapters, properties
- send ports, adapters
ms.assetid: 53f4fd17-95b9-4861-b433-772b619e90c7
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe578337d7137f3c9973ec4d57f195ead94ad908
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="file-adapter-configuration-properties"></a>文件适配器配置属性
下表列出可以为文件适配器设置的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|RemoveReceivedFileRetryCount|VT_UI4|指定文件适配器将尝试删除已读取并提交到 BizTalk Server 的文件的次数。|有效值为从 0 到 100。|默认值为 5。|  
|RemoveReceivedFileMaxInterval|VT_UI4|指定文件适配器在尝试删除已读取并提交到 BizTalk Server 的文件前等待的初始间隔（以毫秒计）。|有效值为 1 到 1000年。|默认值为 10。|  
|FileMask|VT_BSTR|指定文件的掩码。|无|默认值为 *.xml。|  
|BatchSizeInBytes|VT_UI4|指定一批发送到 BizTalk MessageBox 的文件的最大总字节数。|有效值为 1024年到 104857600。|默认值为 102400。|  
|PollingInterval|VT_UI4|指定文件适配器将轮询指定位置以查找新文件的时间间隔（以毫秒计）。|有效值从 1000年到 3600000。|设置为 1 可禁用轮询。|  
|BatchSize|VT_UI4|指定可在一批中提交的最多消息数。|有效值为从 1 到 256。|默认值为 20。|  
|FileNetFailRetryInt|VT_UI4|指定两次尝试访问网络共享上的接收位置（如果该位置暂时不可用）之间的重试间隔时间（分钟）。|有效的值是 0 到 4294967295。|默认值为 5。|  
|RemoveReceivedFileDelay|VT_UI4|指定文件适配器在尝试删除已读取并提交到 BizTalk Server 的文件前等待的初始间隔（以毫秒计）。|在每次重试间隔达到指定的重试间隔最大值后，此间隔时间将增为两倍。<br /><br /> 有效值为 1 到 1000年。|默认值为 10。|  
|RenameReceivedFiles|VT_BOOL|指定在提取文件进行处理前是否对其进行重命名。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0。|  
|FileNetFailRetryCount|VT_UI4|指定尝试访问网络共享上的接收位置（如果该位置暂时不可用）的次数。|有效的值是 0 到 4294967295。|默认值为 5。|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
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
  
 下表列出可以为文件适配器设置的配置属性发送端口：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|用户名|VT_BSTR|如果文件适配器的主机实例不具有所需的权限到网络共享，请指定替代凭据。|无|指定的用户名格式\<域\>\username。|  
|UseTempFileOnWrite|VT_BOOL|指定要写入到目标文件夹时使用的临时文件。 完成文件后将其写入已重命名为 Filename 属性指定的值。|如果 CopyMode 属性设置为值为 2 （新建），则仅可以为-1 (true) 设置此属性。<br /><br /> 有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|CopyMode|VT_UI4|定义要在一条消息写入到文件时使用的复制模式|有效值为<br /><br /> -0 （追加）<br />-1 （覆盖）<br />-2 （新建）|默认值为 2 （新建）。|  
|FileName|VT_BSTR|指定文件发送处理程序将消息写入其中的文件的名称。|此属性限制信息，请参阅[对文件掩码和文件名称属性的限制](http://msdn.microsoft.com/library/d8f5afd0-a61f-4c9b-8a57-4792e3054769)。|默认值为 %messageid%.xml。|  
|AllowCacheOnWrite|VT_BOOL|指定是否使用文件系统缓存时对文件进行写入一条消息。|有效值为<br /><br /> -0 （不使用缓存）<br />--1 (使用 caching)|默认值为的 0 （不使用缓存）。|  
|密码|VT_NULL|指定当文件适配器的主机实例没有所需的权限到网络共享时，与 Username 属性结合使用的密码。|此值在导出绑定文件时始终设置为空。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。|无|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
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