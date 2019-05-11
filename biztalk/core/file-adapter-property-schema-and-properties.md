---
title: 文件适配器属性架构和属性 |Microsoft Docs
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
ms.openlocfilehash: 5671243de2ec3d3f97c8edf80d0de94a547301fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388045"
---
# <a name="file-adapter-property-schema-and-properties"></a>文件适配器属性架构和属性
下表包含在文件适配器属性架构中的属性。  
  
 **Namespace**： http://schemas.microsoft.com/BizTalk/2003/file-properties  
  
|“属性”|类型|Description|  
|----------|----------|-----------------|  
|**CopyMode**|xs:unsignedInt|定义向文件中写入一条消息时要使用的复制模式。 有效值为<br /><br /> **追加 (0)。** 如果它存在并且文件的末尾追加一条消息，该文件发送处理程序打开一个文件。 如果文件不存在，则文件发送处理程序将创建一个新文件。<br /><br /> **创建新的 (1)。** 如果文件不存在，则文件发送处理程序创建一个新文件，并向其中写入。 如果该文件已存在，文件发送处理程序报告错误，然后按照发送端口的通用适配器重试逻辑。 这是文件发送处理程序的默认复制模式。<br /><br /> **覆盖 (2)。** 如果它存在并且覆盖其内容，该文件发送处理程序打开一个文件。 如果文件不存在，则文件发送处理程序将创建一个新文件。|  
|**AllowCacheOnWrite**|xs:Boolean|定义文件适配器是否使用文件系统缓存到文件中写入消息时。|  
|**ReceivedFileName**|xs:string|定义文件适配器从中读取消息的文件的完整名称。|  
|**FileCreationTime**|xs: datetime|定义写入该文件的时间到监视的文件的文件夹接收适配器。|  
|**用户名**|xs:string|定义用于指定替代凭据时访问网络共享的帐户的用户名。|  
|**密码**|xs:string|定义用于指定替代凭据时访问网络共享的帐户的密码。|  
  
## <a name="see-also"></a>请参阅  
 [配置文件适配器](../core/configure-the-file-adapter.md)