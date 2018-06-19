---
title: 错误 Messages3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: 10ea12bb-eacb-477a-bc88-28f999e60a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1b9dd41280593de1472cd6af57ae8d1eb9fc58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241773"
---
# <a name="error-messages"></a>错误消息
下表列出了 PeopleSoft Enterprise 系统的组件接口中的错误消息及其描述，以及可能的更正方法。  
  
 **错误消息**  
  
|错误 ID|可能的原因 / 错误说明|可能的更正|  
|--------------|-----------------------------------------|-------------------------|  
|E JNI0004|没有 psjoa.jar。<br /><br /> 出现 Java 异常。|验证 PeopleSoft psjoa.jar 文件的位置。|  
|E PSFT0030|没有 psjoa.jar。<br /><br /> 实例化组件接口 Bean 失败。|验证 PeopleSoft psjoa.jar 文件的位置。|  
|E PSFT0019|错误的服务器名称。<br /><br /> 连接到 PeopleSoft 应用程序服务器失败。|验证 PeopleSoft 主机和用户参数。|  
|E PSFT0024|错误的用户名和密码。<br /><br /> 连接失败。 错误消息： JavaClient 是无效的用户名称，或键入的密码错误。|必须输入 PeopleSoft 用户名和密码，并且区分大小写。 确保输入信息时使用正确的大小写形式。|  
  
## <a name="see-also"></a>另请参阅  
 [故障排除 PeopleSoft](../core/troubleshooting-peoplesoft.md)