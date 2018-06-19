---
title: 文件适配器属性架构和属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], properties
- schemas, File adapters
- File adapters, schemas
- Password property [File adapters]
- ReceivedFileName property [File adapters]
- configuring [File adapters], schemas
- CopyMode property [File adapters]
- AllowCacheOnWrite property [File adapters]
- FileCreationTime property [File adapters]
- UserName property, File adapters
- File adapters, properties
- UserName property
ms.assetid: c5ae5339-67bf-4fde-a721-5b1aa3b9caca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e1c6860b002b41555337a0bf7e8cb931f2c2bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245989"
---
# <a name="file-adapter-property-schema-and-properties"></a>文件适配器属性架构和属性
下表包含文件适配器属性架构中的属性。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|**CopyMode**|xs:unsignedInt|定义向文件中写入消息时使用的复制模式。 有效值为<br /><br /> **追加 (0)。** 文件发送处理程序打开一个文件（如果该文件存在）并在该文件末尾附加一个消息。 如果文件不存在，则文件发送处理程序将创建一个新文件。<br /><br /> **创建新的 (1)。** 如果文件不存在，则文件发送处理程序将创建一个新文件，并在该文件中写入消息。 如果该文件已存在，则文件发送处理程序将报告错误，然后按照发送端口的通用适配器重试逻辑操作。 此模式为文件发送处理程序的默认复制模式。<br /><br /> **覆盖 (2)。** 文件发送处理程序打开一个文件（如果该文件存在）并覆盖其内容。 如果文件不存在，则文件发送处理程序将创建一个新文件。|  
|**AllowCacheOnWrite**|xs:Boolean|定义文件适配器在向文件中写入消息时是否使用文件系统缓存。|  
|**ReceivedFileName**|xs:string|定义文件适配器从中读取消息的文件的全名。|  
|**FileCreationTime**|xs:datetime|定义将文件写入文件接收适配器所监视的文件夹的时间。|  
|**用户名**|xs:string|定义在指定用于访问网络共享位置的备用凭据时所用帐户的用户名。|  
|**密码**|xs:string|定义在指定用于访问网络共享位置的备用凭据时所用帐户的密码。|  
  
## <a name="see-also"></a>另请参阅  
 [配置文件适配器](../core/configure-the-file-adapter.md)